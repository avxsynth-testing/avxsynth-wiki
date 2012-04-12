Step-by-step guide to setting-up an Ubuntu system for AvxSynth 

##Ubuntu Setup
  1. Install ubuntu-11.10-desktop-amd64.iso (64-bit Ubuntu) or ubuntu-11.10-desktop-i386.iso (32-bit Ubuntu) on system or appropriate vm (i.e. Virtual Box).
  1. Run Update Manager

##Setup Development Environment

  1. **Build Tools**  `sudo apt-get install build-essential checkinstall git yasm`
  1. **MPlayer** `sudo apt-get install  mplayer`
  1. **Log4CPP** `sudo apt-get install liblog4cpp5-dev liblog4cpp5`
  1. **Cairo** `sudo apt-get install libcairo2-dev`
  1. **Pango** `sudo apt-get install libpango1.0-dev`
  1. **LibJPEG** `sudo apt-get install libjpeg-dev`
  1. **QT** `sudo apt-get -y install libqt4-dev libqt4-designer libqt4-gui`
  1. **KDev**
    * Install using Ubuntu Software Center
    * Create a .gdbinit in your home directory containing this text (This is a fix for the debugger hanging on dlopen): 
        * (for 64-bit Ubuntu) `set env LD_PRELOAD /lib/x86_64-linux-gnu/libpthread.so.0` 
        * (for 32-bit Ubuntu) `set env LD_PRELOAD /lib/i386-linux-gnu/libpthread.so.0` 


##LibAV
 1. Get source code of Libav 0.7.4 (http://libav.org/releases/libav-0.7.4.tar.xz)
 1. Compile and install

        ./configure --enable-gpl --enable-nonfree --enable-version3 --enable-shared
        make
        sudo checkinstall --pkgname=ffmpeg --pkgversion="0.7.4" --backup=no --deldoc=yes --fstrans=no --default

##FFMPEGSource
 1. Get source code of FFMS-2.17 (http://code.google.com/p/ffmpegsource/downloads/list?can=1&q=&colspec=Filename+Summary+Uploaded+ReleaseDate+Size+DownloadCount)
 1. Compile and install

        ./configure --enable-shared
        make
        sudo checkinstall --pkgname=ffms2 --pkgversion="2.17" --backup=no --deldoc=yes --fstrans=no --default

##AvxSynth Build
  1. Get AvxSynth source code (avx_root)
         git clone git@github.com:avxsynth/avxsynth.git
  1. In avxsynth root directory, 
         make

##KDev Setup
  1. In KDevelop, Project-> Open/Import Project the following Makefiles
    * avx_root/avxcommon/Makefile
    * avx_root/avxsynth/core/Makefile
    * avx_root/avxsynth/builtinfunctions/Makefile
    * avx_root/plugins/autocrop/Makefile
    * avx_root/plugins/avxframecapture/Makefile
    * avx_root/plugins/avxsubtitle/Makefile
    * avx_root/plugins/ffms2avs/Makefile
  1. For each of the projects above, right click project -> Open Configuration -> Default make target -> set to "deploy"
  1. In Kdevelop, Project-> Open/Import Project the following Makefiles
    * avx_root/apps/avxframeserver/frameserverlib/MakeFile
    * avx_root/apps/avxframeserver/frameserverapp/Makefile
    * avx_root/apps/AVXEdit/Makefile
  1. Right click the frameserverapp project, Open Configuration -> Default make target -> set to "rebuild"
  1. Right click the AVXEdit project, Open Configuration -> Default make target -> set to "rebuild"

##Build AvxSynth
  1. For each of the projects, right-click and build.  Must build in this order:
    * avxcommon
    * builtinfunctions 
    * core
    * frameserverlib
    * frameserverapp and AVXEdit
    * autocrop, avxframecapture, avxsubtitle, ffms2avs

##Basic Test
  1. in KDev configure AVXEdit launch configuration Run-Configure Launches...
  1. Click 'Execute' to launch AVXEdit
  1. In the AVXEdit window, type 'Version()' and click the run button
  1. you should see MPlayer window with AviSynth version video