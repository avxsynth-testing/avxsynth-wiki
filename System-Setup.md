Step-by-step guide to setting-up an Ubuntu system for AvxSynth 

##Ubuntu Setup
  1. Install ubuntu-12.04-desktop-amd64.iso (64-bit Ubuntu) or ubuntu-12.04-desktop-i386.iso (32-bit Ubuntu) on system or appropriate vm (i.e. Virtual Box).
  1. Run Update Manager

##Install Dependencies

  1. **Build Tools**  `sudo apt-get install build-essential checkinstall git pkg-config yasm autoconf automake libtool`
  1. **MPlayer** `sudo apt-get install  mplayer`
  1. **Log4CPP** `sudo apt-get install liblog4cpp5-dev liblog4cpp5`
  1. **Cairo** `sudo apt-get install libcairo2-dev`
  1. **Pango** `sudo apt-get install libpango1.0-dev`
  1. **LibJPEG** `sudo apt-get install libjpeg-dev` (required to build the frame capture plugin)
  1. **QT** `sudo apt-get -y install libqt4-dev`(required if you want to build the GUI app AvxEdit).
  1. **ffms2** `sudo apt-get install libffms2-dev libavcodec-dev libavformat-dev libavutil-dev libpostproc-dev libswscale-dev` (required to build the ffms2 plugin)

NOTE: Users of Ubuntu 11.04 and 11.10 have an old, unsupported version of ffms2 in their repositories. They need to recompile ffms2 as described below.

Alternatively to installing ffms2 and ffmpeg from repository, you may build them as follows:

##ffmpeg
 1. Get source code of ffmpeg 0.11.1 (http://ffmpeg.org/releases/ffmpeg-0.11.1.tar.bz2)
 1. Compile and install

        ./configure --enable-gpl --enable-nonfree --enable-version3 --enable-shared --enable-postproc
        make
        sudo checkinstall --pkgname=ffmpeg --pkgversion="0.11.1" --backup=no --deldoc=yes --fstrans=no --default

(The --enable-postproc option must be set, otherwise the ffms2 plugin won't build)

Note: libav (http://libav.org) 0.8 series is also compatible.

##FFMPEGSource
 1. Get source code of FFMS-2.17 (http://code.google.com/p/ffmpegsource/downloads/detail?name=ffms-2.17-src.tar.bz2)
 1. Open "configure" in a text editor and replace all occurrences of "avcodec_init();" with "avcodec_register_all();"
 1. Compile and install

        ./configure --enable-shared
        make
        sudo checkinstall --pkgname=ffms2 --pkgversion="2.17" --backup=no --deldoc=yes --fstrans=no --default

##AvxSynth Build
  1. Get AvxSynth source code from github

         git clone https://github.com/avxsynth/avxsynth.git

     (or via ssh)

         git clone git@github.com:avxsynth/avxsynth.git

  1. Generate build system from autotools templates. This must be done only the first time the project is checked out.

         autoreconf -i

  1. In avxsynth root directory (to see other options, call ./configure --help)

         ./configure && make

  Note: If you would like silent rules (less verbose output), either use "./configure --enable-silent-rules" or "make V=0"

  1. To install

         sudo make install

  1. Alternatively, you can compile and debug using KDevelop. Click [here](https://github.com/avxsynth/avxsynth/wiki/Using-KDevelop) for instructions. Make sure you run configure before following these instructions.


##Basic Test
  1. Launch AVXEdit. In $avxsynthroot$/apps/AVXEdit/

         ./AVXEdit

  1. In the AVXEdit window, type 'Version()' and click the run button. This will launch an MPlayer window with the AviSynth Version video

  1. For instructions on using the AvxSynth Frame Server, check out [this](https://github.com/avxsynth/avxsynth/wiki/AvxSynth-Frame-Server) page.