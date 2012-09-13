##Introduction
This page talks about the possible usage of _avxSynthFrameServer_ with mplayer and x264 encoder.

AvxSynth frame server application (_avxSynthFrameServer_) is a frame server that dumps the raw frame data to _stdout_. By default it launches the mplayer that reads the frame from stdout. AvxSynth frame server application allows user to control whether mplayer launch is required or not (Note: by default it launches mplayer). 

##Location
The source code for AvxSynthFrameServer is located @ _[AvxSynthFrameServer](https://github.com/avxsynth/avxsynth/tree/master/apps/avxframeserver/frameserverapp)_

##Usage
The usage of the AvxSynth frame server application (_avxSynthFrameServer_) is shown below,

Usage

        ./avxSynthFrameServer <avxsynth script.avs> [mplayer launch flag (default=(Y)es)]

##AvxSynthFrameServer with mplayer
As described AvxSynthFrameServer launches mplayer by default. It dumps the decoded raw frame to stdout and also forks mplayer that reads frames through stdout pipe of AvxSynthFrameServer. Here is typical example how to play a decoded frames with mplayer.

Ex.

        ./avxSynthFrameServer testavxsynthscript.avs

##AvxSynthFrameServer with x264
It is required to disable the mplayer launch to pass the decoded raw frames to x264 encoder. There is a switch to AvxSynthFrameServer that controls whether to launch mplayer or not. It is called "mplayer launch flag". Pass "false" to this flag and it won't launch mplayer. That means, it would dump the raw frames to stdout. x264 can read the frame from stdout and encode based on provided parameters. A typical one pass x264 encode using AvxSynthFrameServer is shown in below example,

Ex.

         ./avxSynthFrameServer testavxsynthscript.avs false | x264 

The required parameters for piping the decoded raw frame data is highlighted in above example. Notice the 
-" at the end that indicates x264 to read the input from stdout.

##AvxSynthFrameServer with x264 (2-pass encoder)
x264 parameter "--pass" indicates the pass number for encoding. First pass determines it's properties, second ensures the selected output file size is reached with maximum efficiency. In 2 pass x264 encoding, x264 needs to executed in 2 steps as shown in below example,

###Pass 1
Determines the properties of the input raw frames. 

pass = 1 : indicates the 1st pass

stats : captured properties are stored in this file that gets used in 2nd pass for encoding.

output = NUL : indicates no need to write the output into file

Ex.

         ./avxSynthFrameServer testavxsynthscript.avs false | x264 

###Pass 2
Uses stats file created in the 1st pass and ensures the selected output file size is reached with maximum efficiency.

pass = 1 : indicates the 2nd pass

stats : properties file that gets used during encoding, properties file is generally created in the 1st pass x264 encoding.

output : output file where encoded frames get appended. output video file.

Ex.

         ./avxSynthFrameServer testavxsynthscript.avs 

The parameters that changes and are important to indicate the pass are highlighted in above example.