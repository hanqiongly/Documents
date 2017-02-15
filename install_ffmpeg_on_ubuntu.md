#Install ffmpeg at ubuntu 16.0.4:

#1. Prepare the environment

$ sudo apt-get install libsdl1.2-dev libtheora-dev librtmp-dev libx264-dev libxvidcore-dev libopencore-amrwb-dev libopencore-amrnb-dev libfaad-dev libfaac-dev libmp3lame-dev libtwolame-dev liba52-0.7.4-dev libcddb2-dev libcdaudio-dev libcdio-cdda-dev libvorbis-dev libopenjpeg-dev libxfixes-dev libxext-dev libxvidcore-dev libvorbis-dev libfaac-dev

#2.install lame 3.99.5

$ tar -zxvf lame-3.99.5.tar.gz

$ cd lame-3.99.5

$ ./configure

$ make

$ make install -version=3.99.5

3.install yasm 1.2.0

$ wget  http://www.tortall.net/projects/yasm/releases/yasm-1.2.0.tar.gz

$ tar -zxvf yasm-1.2.0.tar.gz

$ cd yasm-1.2.0/

$ ./configure

$ make

$ make install 

4.install x264

$ git clone --depth 1 git://git.videolan.org/x264

$ cd x264

$ ./configure ../configure --prefix=/usr --enable-shared --disable-static

$ make 

$ sudo make install 

5.source install libvpx into ubuntu

$ tar -zxvf libvpx-1.6.1.tar.bz2

$ cd libvpx-1.6.1/

$ mkdir libvpx-build && cd libvpx-build

$ ../configure --prefix=/usr --enable-shared --disable-static

$ make

$ sudo make install 



#6.Install ffmpeg :

$ make clean

$ ./configure --enable-gpl --enable-libfaac --enable-libmp3lame --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-librtmp --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-nonfree --enable-version3 --enable-nonfree --enable-postproc --enable-pthreads --enable-libfaac --enable-libtheora --enable-libxvid --enable-x11grab --enable-libvorbis

$ make -j2

$ sudo make install

$ hash ffplay ffmpeg ffprobe x264
