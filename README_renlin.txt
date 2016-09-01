
ubuntu:
sudo apt-get install autoconf automake libtool
sudo apt-get install libpng12-dev
sudo apt-get install libjpeg62-dev
sudo apt-get install libtiff4-dev
sudo apt-get install zlib1g-dev
sudo apt-get install libicu-dev      # (if you plan to make the training tools)
sudo apt-get install libpango1.0-dev # (if you plan to make the training tools)
sudo apt-get install libcairo2-dev   # (if you plan to make the training tools)

#virtualbox
sudo apt-get install linux-headers-$(uname -r)


Fedora:
	cd build
	chmod a+x ../configure
	../configure --prefix=/home/rdlin/local/leptonica
	make
	make install
	
Ubuntu:
       LDFLAGS="-Wl,-rpath -Wl,/opt/leptonica-1.71/lib" ../configure --prefix=/opt/leptonica-1.71
       sudo make install
       sudo ldconfig

Build dependent lib on windows:
zlib, libjpeg, libpng, libtiff:
  cmake 3.3.0; 
    need to copy the files failed to create symbolic link
    in MSys, libpng16.a->libpng.a
    
  $ ../configure CC=C:/MinGW/bin/gcc.exe CXX=C:/MinGW/bin/g++.exe CFLAGS=-g3 -gdwarf-2 CXXFLAGS=-g3 -gdwarf-2 LDFLAGS=-L/d/git/share/lib --prefix=/d/git/share

+Windows: MINGW+OCV3.1.0:
+ $ Start netbean -> Create New Project from existing source
+ $ CC=${IDE_CC} CXX=${IDE_CXX} CFLAGS="-g3 -gdwarf-2" CXXFLAGS="-g3 -gdwarf-2" \
+    LDFLAGS=-L/c/opt/ocv3.1.0/x86/mingw/lib --prefix=/c/opt/leptonica-1.71
+ $ NB-project setting when created: double check "include/lib" files

