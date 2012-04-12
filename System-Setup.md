Ubuntu Setup

    Install ubuntu-11.10-desktop-amd64.iso (64-bit Ubuntu) or ubuntu-11.10-desktop-i386.iso (32-bit Ubuntu) on system or appropriate vm (i.e. Virtual Box).
    Run Update Manager 

Setup Development Environment

    Build Tools: sudo apt-get install build-essential checkinstall git yasm
    MPlayer: sudo apt-get install mplayer
    Log4CPP: sudo apt-get install liblog4cpp5-dev liblog4cpp5
    Cairo: sudo apt-get install libcairo2-dev
    Pango: sudo apt-get install libpango1.0-dev
    LibJPEG: sudo apt-get install libjpeg-dev
    QT: sudo apt-get -y install libqt4-dev libqt4-designer libqt4-gui
    KDev:
        Install using Ubuntu Software Center
        Create a .gdbinit in your home directory containing this text: (for 64-bit Ubuntu)
        set env LD_PRELOAD /lib/x86_64-linux-gnu/libpthread.so.0 (for 32-bit Ubuntu)
        set env LD_PRELOAD /lib/i386-linux-gnu/libpthread.so.0 This is a fix for the debugger hanging on dlopen) 

LibAV

    Get source code of Libav 0.7.4 (http://libav.org/releases/libav-0.7.4.tar.xz)
    Compile and install
        ./configure --enable-gpl --enable-nonfree --enable-version3 --enable-shared
        make
        sudo checkinstall --pkgname=ffmpeg --pkgversion="0.7.4" --backup=no --deldoc=yes --fstrans=no --default 

FFMPEG Source

    Get source code of FFMS-2.17 (http://code.google.com/p/ffmpegsource/downloads/list?can=1&q=&colspec=Filename+Summary+Uploaded+ReleaseDate+Size+DownloadCount)
    Compile and install
        ./configure --enable-shared
        make
        sudo checkinstall --pkgname=ffms2 --pkgversion="2.17" --backup=no --deldoc=yes --fstrans=no --default 

Setup AvxSynth Source

    Setup source folder with AvxSynth source code (avx_root)
    Create a directory $HOME$/.AVXSynth/plugins/
    To build using master Makefile from console, goto avx_root, and enter 'make' or 'make clean' followed by 'make'. This will build in the proper order. 

KDev Setup

    In KDevelop, Project-> Open/Import Project the following Makefiles
        avx_root/avxcommon/Makefile
        avx_root/avxsynth/core/Makefile
        avx_root/avxsynth/builtinfunctions/Makefile
        avx_root/plugins/autocrop/Makefile
        avx_root/plugins/avxframecapture/Makefile
        avx_root/plugins/avxsubtitle/Makefile
        avx_root/plugins/ffms2avs/Makefile 
    For each of the projects above, right click project -> Open Configuration -> Default make target -> set to "deploy"
    In Kdevelop, Project-> Open/Import Project the following Makefiles
        avx_root/apps/avxframeserver/frameserverlib/MakeFile
        avx_root/apps/avxframeserver/frameserverapp/Makefile
        avx_root/apps/AVXEdit/Makefile 
    Right click the frameserverapp project, Open Configuration -> Default make target -> set to "rebuild"
    Right click the AVXEdit project, Open Configuration -> Default make target -> set to "rebuild" 

Build AvxSynth

    For each of the projects, right-click and build. Must build in this order:
        avxcommon
        builtinfunctions
        core
        frameserverlib
        frameserverapp and AVXEdit
        autocrop, avxframecapture, avxsubtitle, ffms2avs 

Basic Test

    in KDev configure AVXEdit launch configuration Run-Configure Launches...
    Click 'Execute' to launch AVXEdit
    In the AVXEdit window, type 'Version()' and click the run button
    you should see MPlayer window with AviSynth version video 