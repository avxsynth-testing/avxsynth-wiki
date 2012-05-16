Step-by-step guide to setting-up an Ubuntu system for AvxSynth 

##Ubuntu Setup
  1. Install ubuntu-12.04-desktop-amd64.iso (64-bit Ubuntu) or ubuntu-12.04-desktop-i386.iso (32-bit Ubuntu) on system or appropriate vm (i.e. Virtual Box).
  1. Run Update Manager

##Install Dependencies

  1. **Build Tools**  `sudo apt-get install build-essential checkinstall git yasm`
  1. **MPlayer** `sudo apt-get install  mplayer`
  1. **Log4CPP** `sudo apt-get install liblog4cpp5-dev liblog4cpp5`
  1. **Cairo** `sudo apt-get install libcairo2-dev`
  1. **Pango** `sudo apt-get install libpango1.0-dev`
  1. **LibJPEG** `sudo apt-get install libjpeg-dev` (required to build the frame capture plugin)
  1. **QT** `sudo apt-get -y install libqt4-dev libqt4-designer libqt4-gui`(required if you want to build the GUI app AvxEdit).
  1. **ffms2** `sudo apt-get install libffms2-dev libavcodec-dev libavformat-dev libavutil-dev libpostproc-dev libswscale-dev` (required to build the ffms2 plugin)

Alternatively to installing ffms and ffmpeg from repository, you may build them as follows:

##LibAV
 1. Get source code of Libav 0.8.1 (http://libav.org/releases/libav-0.8.1.tar.xz)
 1. Compile and install

        ./configure --enable-gpl --enable-nonfree --enable-version3 --enable-shared --enable-postproc
        make
        sudo checkinstall --pkgname=ffmpeg --pkgversion="0.8.1" --backup=no --deldoc=yes --fstrans=no --default

(The --enable-postproc option must be set, otherwise the ffms2 plugin won't build)

##FFMPEGSource
 1. Get source code of FFMS-2.17 (http://code.google.com/p/ffmpegsource/downloads/list?can=1&q=&colspec=Filename+Summary+Uploaded+ReleaseDate+Size+DownloadCount)
 1. Compile and install

        ./configure --enable-shared
        make
        sudo checkinstall --pkgname=ffms2 --pkgversion="2.17" --backup=no --deldoc=yes --fstrans=no --default

##AvxSynth Build
  1. Get AvxSynth source code from github

         git clone https://github.com/avxsynth/avxsynth.git

     (or via ssh)

         git clone git@github.com:avxsynth/avxsynth.git

  1. In avxsynth root directory (to see other options, call ./configure --help)

         ./configure && make

  1. To install

         make install

  1. Alternatively, you can compile and debug using KDevelop. Click [here](https://github.com/avxsynth/avxsynth/wiki/Using-KDevelop) for instructions. Make sure you run configure before following these instructions.


##Basic Test
  1. Launch AVXEdit. In $avxsynthroot$/apps/AVXEdit/

         ./AVXEdit

  1. In the AVXEdit window, type 'Version()' and click the run button. This will launch an MPlayer window with the AviSynth Version video

  1. For instructions on using the AvxSynth Frame Server, check out [this](https://github.com/avxsynth/avxsynth/wiki/AvxSynth-Frame-Server) page.