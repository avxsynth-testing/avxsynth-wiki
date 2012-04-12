Kdevelop can be used as an IDE to build and debug AvxSynth. Be sure to set-up the dependencies as described [here](https://github.com/avxsynth/avxsynth/wiki/System-Setup) before building AvxSynth.

##Install KDevelop
  1. Install Kdevelop using Ubuntu Software Center

  1. Create a .gdbinit file in your home directory containing the following text.  This is a fix for the debugger hanging on dlopen.
   * for 64-bit Ubuntu 
          `set env LD_PRELOAD /lib/x86_64-linux-gnu/libpthread.so.0`
   * for 32-bit Ubuntu 
          `set env LD_PRELOAD /lib/i386-linux-gnu/libpthread.so.0`

## Get AvxSynth

  1. Get AvxSynth source code from github

         git clone git@github.com:avxsynth/avxsynth.git

  1. Let $avxsynthroot$ be the root directory of the avxsynth source code.


## Import projects
  1. In KDevelop, Project-> Open/Import Project the following Makefiles
    * $avxsynthroot$/avxcommon/Makefile
    * $avxsynthroot$/avxsynth/core/Makefile
    * $avxsynthroot$/avxsynth/builtinfunctions/Makefile
    * $avxsynthroot$/plugins/autocrop/Makefile
    * $avxsynthroot$/plugins/avxframecapture/Makefile
    * $avxsynthroot$/plugins/avxsubtitle/Makefile
    * $avxsynthroot$/plugins/avsffms2/Makefile
  1. For each of the projects above, right click project -> Open Configuration -> Default make target -> set to "deploy"
  1. In Kdevelop, Project-> Open/Import Project the following Makefiles
    * $avxsynthroot$/apps/avxframeserver/frameserverlib/MakeFile
    * $avxsynthroot$/apps/avxframeserver/frameserverapp/Makefile
    * $avxsynthroot$/apps/AVXEdit/Makefile
  1. Right click the frameserverapp project, Open Configuration -> Default make target -> set to "rebuild"
  1. Right click the AVXEdit project, Open Configuration -> Default make target -> set to "rebuild"

## Build AvxSynth projects
For each of the projects, right-click and build.  Must build in this order:
    * avxcommon
    * builtinfunctions 
    * core
    * frameserverlib
    * frameserverapp, AVXEdit
    * autocrop, avxframecapture, avxsubtitle, avsffms2


