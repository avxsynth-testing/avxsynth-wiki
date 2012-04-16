This page discusses the AvxSynth porting effort.


## Introduction 

We use AviSynth as a frame server in our encoding pipeline, a cloud-based highly-scalable encoding system.  Because of our dependence on AviSynth, we have been locked into Windows EC2 instances.  By porting AviSynth, we will save a significant amount of money on EC2 hosts, and will also benefit from the stability and pervasiveness of Linux.

## AviSynth 3.0

When we began the port, we evaluated the AviSynth 3.0, Linux port.  However, we determined that this project was overly ambitious, and the code did not seem to be in a usable state.  Further, we determined that attempting to complete the AviSynth 3.0 port was a rathole from which we did not expect to emerge.  Rather than try to stabilize AviSynth 3.0, we chose to fork from AviSynth 2.5.8

## Porting AviSynth - Divide and Conquer

After studying AviSynth, we divided the project up into its major architectural components: scripting engine, plugin-in model, built-in functions, built-in sources, TCP deliver, and the Video For Windows (VFW) layer.  This is illustrated in the image below.

http://avxsynth.googlecode.com/svn/wiki/images/AviSynthArchOverview.png

Of these modules, we decided that the VFW layer, TCP Deliver, and the built-in sources were not of interest.  In particular, the built-in DirectShow Source filter was not easily portable.  This left us with the scripting engine, plug-in model, and built-in functions as shown in the image below.

http://avxsynth.googlecode.com/svn/wiki/images/AviSynthArchOverview2.png

At this point, we felt that we had a manageable project.  

Because the bulk of the remaining code was in the built-in functions, we decided to take one additional step.  The separation of the built-in functions from the AviSynth core (the plugin model, and script engine).  The rational for this was as follows:

  * By separating the built-in functions from the AviSynth core, the port of the core would be very simple.
  * All of the built-in functions could be commented out, and then ported one at a time.  Thus minimizing risk.

##Practical Milestones

Having established a low-risk plan of attack, we then established a set of porting milestones so that we could track the progress, and bail early if the work went badly (avoid a career-ending tar pit).

###Milestone 1: Re-architecture
  * Remove all code from core except scripting and plugin management
  * Set up separate dll for built-in functions
  * Compile and run in Windows
  * Demonstrate 2 functions (Version, and Text Overlay) 

###Milestone 2: Initial Port
  * Port core and built-in functions
  * Build simple frame server application 
  * Demonstrate two functions on Linux (Version, and Text Overlay)
 
###Milestone 3: Make it work
  * Port AviSynth ffmpeg source
  * Port some basic functions: re-size, colorspace conversions, etc.
  * Begin porting of low-fruit built-in functions.

###Productize
After completing milestone 3, we were convinced that the port was successful, and so we moved forward very aggressively.  In addition to porting many built-in functions, we also added some new stuff:

  * AvxSubtitle plugin that parses SRT captions files, and does subtitle burn-in.
  * AvxFrameCapture plugin that can capture frames to jpeg at specified intervals.
  * AVXEdit: A simple tool to develop and test scripts (like AvsEdit).
  * Log4CPP logging
  * namespace: We put the entire AviSynth code under the namespace avxsynth.  This resolves some name collisions with ffmpeg.
  * Improved error handling.  Added a second mode of error handling:
    * Default is AviSynth error handling of generating error video
    * Added a Script command to specify that the engine should throw exception on error.  This is preferred for automated transocding systems.

##Some Porting Headaches

There are many unresolved porting issues.

  * The resize function uses SoftWire for just-in-time compilation of assembly.  We did not port Softwire and thus did not port the resize function.  The built-in resize is chained to the ffmpeg resize plugin.
  * Many of the built-in functions use inline assembly.  We did not port any inline assembly.  Rather, we commented the code out, and used the less-efficient C code.  
  * We did not port any built-in functions for which there was no C code implementation.
  * Our port currently does not compile or run on Windows.  We feel that this is an issue that must be resolved.