Kdevelop can be used as an IDE to build and debug AvxSynth.

##Install KDevelop
  1. Install Kdevelop using Ubuntu Software Center

  1. Create a .gdbinit in your home directory containing this text (This is a fix for the debugger hanging on dlopen): 
        * (for 64-bit Ubuntu) 
`set env LD_PRELOAD /lib/x86_64-linux-gnu/libpthread.so.0` 
        * (for 32-bit Ubuntu) 
`set env LD_PRELOAD /lib/i386-linux-gnu/libpthread.so.0` 

## Import and build AvxSynth

  1. Get AvxSynth source code from github

         git clone git@github.com:avxsynth/avxsynth.git

  1. Let $avxsynthroot$ be the root directory of the avxsynth source code.

