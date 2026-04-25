# DiscordChatExporter

discord.js


Discord server npm version npm downloads Tests status Last commit. contributors backers Code coverage

Vercel Cloudflare Workers

About
This repository contains multiple packages with separate releases. You can find the assembled Discord API wrapper at discord.js. It is a powerful Node.js module that allows you to easily interact with the Discord API.

Packages
discord.js (source) - A powerful Node.js module for interacting with the Discord API
create-discord-bot (source) - A CLI tool to quickly scaffold a Discord bot project
@discordjs/brokers (source) - A collection of brokers for use with discord.js
@discordjs/builders (source) - A utility package for easily building Discord API payloads
@discordjs/collection (source) - A powerful utility data structure
@discordjs/core (source) - A thinly abstracted wrapper around the core components of the Discord API
@discordjs/formatters (source) - A collection of functions for formatting strings
@discordjs/proxy (source) - A wrapper around @discordjs/rest for running an HTTP proxy
@discordjs/rest (source) - A module for interacting with the Discord REST API
@discordjs/structures (source) - A wrapper around Discord's structures
@discordjs/util (source) - A collection of utility functions
@discordjs/voice (source) - A module for interacting with the Discord Voice API
@discordjs/ws (source) - A wrapper around Discord's gateway
Containers
discordjs/proxy (source) - A lightweight HTTP proxy for Discord's API
Links
Website (source)
Documentation
Guide (source) Also see the v13 to v14 Update Guide, which includes updated and removed items from the library.
discord.js Discord server
Discord Developers Discord server
GitHub
npm
Related libraries
Extensions
RPC (source)
Contributing
Please read through our contribution guidelines before starting a pull request. We welcome contributions of all kinds, not just code! If you're stuck for ideas, look for the good first issue label on issues in the repository. If you have any questions about the project, feel free to ask them on Discord. Before creating your own issue or pull request, always check to see if one already exists! Don't rush contributions, take your time and ensure you're doing it correctly.

Help
If you don't understand something in the documentation, you are experiencing problems, or you just need a gentle nudge in the right direction, please join our Discord server.GrandOrgue is a sample based pipe organ simulator.

It currently supports Windows and Linux. Porting to other OS supported by RtMidi, 
RtAudio and wxWidgets should be possible with some build system adjustments.

A) Building on Linux:
--------------------

1) Install gcc C++ compiler, make, cmake and the development packages of wxWigets, jack (libjack), pkg-config, fftw (fftw3), wavpack and alsa (libasound) from your distribution
2) Install docbook-xsl, xsltproc, zip, gettext and po4a (if present on your distribution)
3) Extract the GO sources somewhere, eg: /home/user/gosources
4) Create an empty build directory, eg: mkdir /home/user/gobuild
5) Run cmake:
  cd /home/user/gobuild
  cmake -DCMAKE_BUILD_TYPE=Release -G "Unix Makefiles" <path to go-sources>
  make

  cmake -DCMAKE_BUILD_TYPE=Release -G "Unix Makefiles" <path to go-sources>

Hint: For debugging a build, add the -DCMAKE_CXX_FLAGS=-g -DCMAKE_C_FLAGS=-g option to cmake.

Building Linux packages:
-----------------------
To build a deb package (Debian/Ubuntu), do
sudo apt-get install build-essential fakeroot
dpkg-buildpackage -rfakeroot

If dpkg-buildpackage reports, that a package is missing, please install them too (sudo apt-get install <packagename).

GrandOrgue ships a spec file for building RPMs (tested with OpenSuSE and Fedora).
To build, copy the grandorgue tarball to the rpm SOURCE directory and run:
rpmbuild -ba grandorgue.spec

B) Building on OS X
===================

1. Prequisites:
 - OS X >= 10.11
 - Xcode >= 7.3
 - homebrew

2. Install via homebrew:
  - brew update
  - brew install gettext jack docbook-xsl wxmac cmake pkg-config fftw wavpack
  - brew link gettext --force

3. extract the GO source into a directory

4. run the following commands:
  cmake -G "Unix Makefiles" -DCMAKE_CXX_FLAGS=-g -DCMAKE_C_FLAGS=-g -DDOCBOOK_DIR=/usr/local/opt/docbook-xsl/docbook-xsl
  make -k package VERBOSE=1

C) Building for Windows
----------------------

The easiest way to build a Windows version is to cross-compile using a openSuSE 42.1 system (or virtual machine).

a) Cross compiling the existing source rpms

Install OpenSuSE penSuSE Tumbleweed (https://software.opensuse.org/distributions/tumbleweed) (possibly in a Virtual Machine, eg Virtual Box. I would recommend >= 1 GB RAM and >= 20 G of harddisc space).
Run in a terminal:

sudo zypper addrepo http://download.opensuse.org/repositories/windows:mingw:win32/openSUSE_Tumbleweed/windows:mingw:win32.repo
sudo zypper addrepo http://download.opensuse.org/repositories/windows:mingw:win64/openSUSE_Tumbleweed/windows:mingw:win64.repo
sudo zypper addrepo http://download.opensuse.org/repositories/home:e9925248:mingw/openSUSE_Tumbleweed/home:e9925248:mingw.repo
sudo zypper modifyrepo -p 10 home_e9925248_mingw 
sudo zypper refresh
sudo zypper install rpm-build gcc-c++ cmake gettext-tools docbook-xsl-stylesheets po4a libxslt-tools zip

Download the src.rpm from:
http://software.opensuse.org/download.html?project=home%3Ae9925248%3Amingw&package=mingw32-grandorgue
http://software.opensuse.org/download.html?project=home%3Ae9925248%3Amingw&package=mingw64-grandorgue

Install it with

rpm -i mingw??-grandorgue????.src.rpm

If you want to build with asio, change in your home directory in the folder rpmbuild/SPECS in the file mingw??-grandorgue.spec

%define with_asio 0

to

%define with_asio 1

Extract the individual ASIO SDK files to rpmbuild/SOURCES.

Run

rpmbuild -ba rpmbuild/SPECS/mingw??-grandorgue.spec

The first build will complain, that a package is missing. To install them, just run

sudo zypper install <package-name>

Then rerun rpmbuild.

D) Building on Windows
----------------------

The following build procedures works on a 32 or 64 bit windows build system. On a real 64 bit system, it is possible to build the 64 bit version directly without reusing parts from the 32 bit build. In that case -DIMPORT_EXECUTABLES and -DCMAKE_SYSTEM_NAME shall be removed.

All the instructions below are for building GrandOrgue for release, in a single static exe file and using unicode.

As a prerequisite, you need to install CMAKE (http://www.cmake.org) and NSIS (http://nsis.sourceforge.net/Download)

#1: Downloading GrandOrgue sources
	Create a repository with the GrandOrgue sources (SVN : https://ourorgan.svn.sourceforge.net/svnroot/ourorgan)
	In the following example the repository is created at c:\go 

#2: TDM64 environment
	Install TDM64 from http://tdm-gcc.tdragon.net/download
	Install the sources of wxWidgets-3.0.X [use the lastest release] from http://www.wxwidgets.org/downloads/ in C:\TDM\wx32\wxWidgets-3.0.X and C:\TDM\wx64\wxWidgets-3.0.X (same sources at both places)
	Install all the tools for translation and help generation (see Building the help and translations on Windows in README C) ). It is a good idea to copy all exe in the same directory and to add this directory to the Windows path (e.g. C:\TDM\tools\bin, C:\TDM\docbook-xsl-1.76.1 )
	
	Building for 32 bits
		Install msysgit from http://code.google.com/p/msysgit/downloads/detail?name=Git-1.7.8-preview20111206.exe&can=2&q=
		apply wxWidgets-fix-build-3.0.2.patch to c:\TDM\wx32\wxWidgets-3.0.X (right clic on wxWidgets-3.0.X directory to open git bash,  then type git apply /c/go/wxWidgets/wxWidgets-fix-build-3.0.2.patch)
		Wxwidgets:
			change directory to C:\TDM\wx32\wxWidgets-3.0.X\build\msw
			mingw32-make -f makefile.gcc UNICODE=1 BUILD=Release SHARED=0 CXXFLAGS="-m32" CFLAGS="-m32"
		GO:
			create a build directory (e.g. c:\go\build32)
			ASIO support: Either add -DRTAUDIO_USE_ASIO=OFF to the cmake parameters below (no ASIO support), or copy the sources from ASIO SDK at http://www.steinberg.net/en/company/developer.html into C:\go\ext\rt\asio\include (the SDK is free but you will need to set up a developer account with Steinberg).
			you need to replace %1 by GO revision number at the end of the following line, or copy this line in a bat file and use the revision number as the parameter when executing the bat file.
			cmake .. -G "MinGW Makefiles" -DCMAKE_BUILD_TYPE=Release -DSTATIC=1 -DwxWidgets_ROOT_DIR=C:\TDM\wx32\wxWidgets-3.0.X -DCMAKE_EXE_LINKER_FLAGS="-m32 -static-libgcc" -DCMAKE_CXX_FLAGS="-m32" -DCMAKE_C_FLAGS="-m32" -DCMAKE_RC_FLAGS="-F pe-i386 -U WIN64" -DDOCBOOK_DIR=C:\TDM\docbook-xsl-1.76.1  -DRTAUDIO_USE_WASAPI=ON -DRTAUDIO_USE_JACK=OFF -DRTMIDI_USE_JACK=OFF -DINSTALL_DEMO=ON -DVERSION_REVISION=%1
			mingw32-make 
			at this point the binary is generated.
			to create the installation package, you need to execute:
			mingw32-make package
			
	Building in 64 bits
		Install msysgit from http://code.google.com/p/msysgit/downloads/detail?name=Git-1.7.8-preview20111206.exe&can=2&q=
		apply wxWidgets-fix-build-3.0.2.patch to c:\TDM\wx64\wxWidgets-3.0.X (right clic on wxWidgets-3.0.X directory to open git bash,  then type git apply /c/go/wxWidgets/wxWidgets-fix-build-3.0.2.patch)
		Wxwidgets:
			change directory to C:\TDM\wx64\wxWidgets-3.0.X\build\msw
			mingw32-make -f makefile.gcc BUILD=Release UNICODE=1 SHARED=0 CXXFLAGS=-DHAVE_VARIADIC_MACROS=1
		GO:
			create a build directory (e.g. c:\go\build64)
			ASIO support: Either add -DRTAUDIO_USE_ASIO=OFF to the cmake parameters below (no ASIO support), or copy the sources from ASIO SDK at http://www.steinberg.net/en/company/developer.html into C:\go\ext\rt\asio\include (the SDK is free but you will need to set up a developer account with Steinberg).
			you need to have build the 32 bit version first since the executables are required to compile the 64 bit version
			you need to replace %1 by GO revision number at the end of the following line, or copy this line in a bat file and use the revision number as the parameter when executing the bat file.
			cmake .. -G "MinGW Makefiles" -DCMAKE_BUILD_TYPE=Release -DSTATIC=1 -DwxWidgets_ROOT_DIR=C:\TDM\wx64\wxWidgets-3.0.X -DCMAKE_EXE_LINKER_FLAGS="-static-libgcc" -DIMPORT_EXECUTABLES=c:\go\build32\ImportExecutables.cmake -DCMAKE_SYSTEM_NAME=Windows -DDOCBOOK_DIR=C:\TDM\docbook-xsl-1.76.1 -DRTAUDIO_USE_WASAPI=ON -DINSTALL_DEMO=ON -DRTAUDIO_USE_JACK=OFF -DRTMIDI_USE_JACK=OFF -DVERSION_REVISION=%1 
			mingw32-make 
			at this point the binary is generated.
			to create the installation package, you need to execute:
			mingw32-make package

#3: Cygwin environment: (not maintained)
	Install Cygwin from http://cygwin.com/setup.exe
	You need to select the following packages which are probably not in the basic configuration:
	git (core files), mingw64 (from dev everything except Ada and fortran), make (in Devel GNU utility), cmake (in Devel cross platform build manager), libgtk2-devel (in X11 runtime), docbook-xsl (in text stylesheets), xsltproc (in text libxslt), zip (in Utils utilities), gettext (in Devel library and core utilisties) and po4a. po4a can be obtained from http://sourceware.org/cygwinports/ which provides ports to Cygwin
	Install wxWidgets-3.0.X [use the lastest release] from http://www.wxwidgets.org/downloads/  in c:\cyg\wxsrc32 and c:\cyg\wxsrc64
	create the following directories c/cyg/inst32, inst64, buildlinux32, buildwin32, buildlinux64
	
	Building in 32 bits
		Create toolchain.def in inst32 with following content
			------------------------------------------------------
			# the name of the target operating system
			SET(CMAKE_SYSTEM_NAME Windows)
			SET(MSYS 1)

			# which compilers to use for C and C++
			SET(CMAKE_C_COMPILER i686-w64-mingw32-gcc)
			SET(CMAKE_CXX_COMPILER i686-w64-mingw32-g++)
			SET(CMAKE_RC_COMPILER i686-w64-mingw32-windres)

			# here is the target environment located
			SET(CMAKE_FIND_ROOT_PATH  /usr/i686-w64-mingw32 /cygdrive/c/cyg/inst32)

			# adjust the default behaviour of the FIND_XXX() commands:
			# search headers and libraries in the target environment, search 
			# programs in the host environment
			set(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
			set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
			set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)
			-------------------------------------------------------
		
		Wxwidgets:
			cd /cygdrive/c/cyg/wxsrc32
			apply wxWidgets-fix-build-3.0.2.patch using git apply /cygdrive/c/gosrc/trunk/wxWidgets/wxWidgets-fix-build-3.0.2.patch
			./configure --host=i686-w64-mingw32 --prefix=/cygdrive/c/cyg/inst32 --enable-unicode --disable-shared
			(cd locale && make allmo)
			make
			make install
		GO:
			Create enough of the "native linux" build to get the image converter and its import files created.
				cd /cygdrive/C/cyg/buildlinux32
				cmake -DCMAKE_BUILD_TYPE=Release -DSTATIC=1 -G "Unix Makefiles" /cygdrive/c/gosrc -DCMAKE_INSTALL_PREFIX=/cygdrive/c/cyg/inst32 -DCMAKE_LEGACY_CYGWIN_WIN32=1 -DCMAKE_CXX_FLAGS=-I/usr/include/w32api -DRTAUDIO_USE_WASAPI=OFF -DRTAUDIO_USE_WDMKS=OFF -DRTAUDIO_USE_ASIO=OFF -DRTAUDIO_USE_DSOUND=OFF -DRTAUDIO_USE_WMME=OFF
				make
			Create the 32 bit version of GO
				cd /cygdrive/C/cyg/buildwin32
				cmake -DCMAKE_TOOLCHAIN_FILE=/cygdrive/c/cyg/inst32/toolchain.def /cygdrive/c/gosrc -DCMAKE_BUILD_TYPE=Release -DSTATIC=1 -DCMAKE_INSTALL_PREFIX=/cygdrive/c/cyg/inst32 -DIMPORT_EXECUTABLES=/cygdrive/c/cyg/buildlinux32/ImportExecutables.cmake -DCMAKE_EXE_LINKER_FLAGS="-static-libgcc -static-libstdc++" -DRTAUDIO_USE_WASAPI=OFF 
				make

	Buiding in 64 bits
		Create toolchain.def in inst64 with following content
			------------------------------------------------------
			# the name of the target operating system
			SET(CMAKE_SYSTEM_NAME Windows)
			SET(MSYS 1)

			# which compilers to use for C and C++
			SET(CMAKE_C_COMPILER x86_64-w64-mingw32-gcc)
			SET(CMAKE_CXX_COMPILER x86_64-w64-mingw32-g++)
			SET(CMAKE_RC_COMPILER x86_64-w64-mingw32-windres)

			# here is the target environment located
			SET(CMAKE_FIND_ROOT_PATH  /usr/x86_64-w64-mingw32 /cygdrive/c/cyg/inst64)

			# adjust the default behaviour of the FIND_XXX() commands:
			# search headers and libraries in the target environment, search 
			# programs in the host environment
			set(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
			set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
			set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)	
			------------------------------------------------------

		Wxwidgets:
			cd /cygdrive/c/cyg/wxsrc64
			apply wxWidgets-fix-build-3.0.2.patch using git apply /cygdrive/c/gosrc/trunk/wxWidgets/wxWidgets-fix-build-3.0.2.patch
			./configure CFLAGS=-m64 CPPFLAGS=-m64 LDFLAGS="-m64 --define WX_CPU_AMD64" --host=x86_64-w64-mingw32 --build=x86_64-pc-cygwin --prefix=/cygdrive/c/cyg/inst64 --enable-unicode --disable-shared
			(cd locale && make allmo)
			make
			make install
		GO:
			Create enough of the "native linux" build to get the image converter and its import files created (unless already done in 32 bit build)
				cd /cygdrive/C/cyg/buildlinux32
				cmake -DCMAKE_BUILD_TYPE=Release -DSTATIC=1 -G "Unix Makefiles" /cygdrive/c/goscr -DCMAKE_INSTALL_PREFIX=/cygdrive/c/cyg/inst32 -DCMAKE_LEGACY_CYGWIN_WIN32=1 -DCMAKE_CXX_FLAGS=-I/usr/include/w32api -DRTAUDIO_USE_WASAPI=OFF -DRTAUDIO_USE_WDMKS=OFF -DRTAUDIO_USE_ASIO=OFF -DRTAUDIO_USE_DSOUND=OFF -DRTAUDIO_USE_WMME=OFF
				make	
		        or create only the build tools:
				cd /cygdrive/C/cyg/buildlinux32
				cmake -G "Unix Makefiles" /cygdrive/c/goscr/src/build -DCMAKE_INSTALL_PREFIX=/cygdrive/c/cyg/inst32 -DCMAKE_LEGACY_CYGWIN_WIN32=1
				make	
			Create the 64 bit version of GO			
				cd ./cygdrive/c/cyg/buildwin64
				cmake -DCMAKE_TOOLCHAIN_FILE=/cygdrive/c/cyg/inst64/toolchain.def /cygdrive/c/gosrc -DCMAKE_BUILD_TYPE=Release -DSTATIC=1 -DCMAKE_INSTALL_PREFIX=/cygdrive/c/cyg/inst64 -DIMPORT_EXECUTABLES=/cygdrive/c/cyg/buildlinux32/ImportExecutables.cmake -DCMAKE_EXE_LINKER_FLAGS="-static-libgcc -static-libstdc++" -DRTAUDIO_USE_WASAPI=OFF 
				make



Cross-compiling for Windows:
----------------------------

1) Install mingw-w64 (On Debian/Ubuntu, install the package mingw-w64) and
   all packages needed to build GO under Linux.
2) Prepare 5 directores:
  * extracted wxWidgets sources [use the lastest release] to a directory (/wxsrc)
  * extract GO trunk sources to a directory (/gosrc)
  * create empty install directory (/inst)
  * create empty win build directory (/buildwin)
  * create empty linux build directory (/buildlinux)
In the following, I use the short path from above - normally
you would put them somewhere under $HOME and use something like /home/user/GO/wxsrc.
3) Build wxWidgets
cd /wxsrc
./configure --host=i686-w64-mingw32 --prefix=/inst --enable-unicode
git apply /gosrc/wxWidgets/wxWidgets-fix-build-3.0.2.patch
(cd locale && make allmo)
make
make install 
4) Build GO for linux
a)
cd /buildlinux
cmake -G "Unix Makefiles" -DCMAKE_BUILD_TYPE=Release /gosrc
make
b) or instead of 4 just build the build tools:
cd /buildlinux
cmake -G "Unix Makefiles" /gosrc/src/build
make
5) Create toolchain definition for windows, file /inst/toolchain.def:
---------------------------------------------------------------------
# the name of the target operating system
SET(CMAKE_SYSTEM_NAME Windows)
SET(MSYS 1)

# which compilers to use for C and C++
SET(CMAKE_C_COMPILER i686-w64-mingw32-gcc)
SET(CMAKE_CXX_COMPILER i686-w64-mingw32-g++)
SET(CMAKE_RC_COMPILER i686-w64-mingw32-windres)
SET(PKG_CONFIG_EXECUTABLE i686-w64-mingw32-pkg-config)

# here is the target environment located
SET(CMAKE_FIND_ROOT_PATH  /usr/i686-w64-mingw32 /inst)

# adjust the default behaviour of the FIND_XXX() commands:
# search headers and libraries in the target environment, search 
# programs in the host environment
set(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)
---------------------------------------------------------------------

6) Build GO for windows
cd /buildwin
cmake -DCMAKE_TOOLCHAIN_FILE=/inst/toolchain.def /gosrc -DCMAKE_INSTALL_PREFIX=/inst -DSTATIC=1 -DIMPORT_EXECUTABLES=/buildlinux/ImportExecutables.cmake -DRTAUDIO_USE_ASIO=OFF
make

-DRTAUDIO_USE_ASIO=OFF turns building ASIO off - else you need to put the ASIO SDK into the sources

7) If you have installed NSIS too, run
make package
to create an installer

If you want to build a 64bit version, replace everywhere in this instruction i686-w64-mingw32 with x86_64-w64-mingw32.

C) Building the help and translations on Windows:
-------------------------------------------------

This is how one can build GrandOrgue help and translations on Windows.

One needs docbook-xsl, gettext, libiconv, libxml2, libxslt, zlib, zip, perl and po4a.

I) Downloads
These packages can be downloaded from the following sites:
docbook-xsl: docbook-xsl-1.76.1.tar.bz2
	http://sourceforge.net/projects/docbook/files/docbook-xsl/1.76.1/docbook-xsl-1.76.1.tar.bz2/download

gettext is made of 4 packages: gettext-runtime, gettext-tools, gettext-runtime-dev, gettext-tools-dev.
All are mandatory to get gettext up and running:
gettext-runtime-dev_0.18.1.1-2_win32.zip
	http://ftp.acc.umu.se/pub/gnome/binaries/win32/dependencies/gettext-runtime-dev_0.18.1.1-2_win32.zip
gettext-runtime_0.18.1.1-2_win32.zip
	http://ftp.gnome.org/pub/gnome/binaries/win32/dependencies/gettext-runtime_0.18.1.1-2_win32.zip
gettext-tools-dev_0.18.1.1-2_win32.zip
	http://ftp.acc.umu.se/pub/gnome/binaries/win32/dependencies/gettext-tools-dev_0.18.1.1-2_win32.zip
gettext-tools_0.18.1.1-2_win32.zip
	http://ftp.acc.umu.se/pub/gnome/binaries/win32/dependencies/gettext-tools_0.18.1.1-2_win32.zip

iconv: iconv-1.9.2.win32.zip
	ftp://ftp.zlatkovic.com/libxml/iconv-1.9.2.win32.zip

libxml2: libxml2-2.7.8.win32.zip
	ftp://ftp.zlatkovic.com/libxml/libxml2-2.7.8.win32.zip

libxslt: libxslt-1.1.26.win32.zip
	ftp://ftp.zlatkovic.com/libxml/libxslt-1.1.26.win32.zip

zlib: zlib-1.2.5.win32.zip
	ftp://ftp.zlatkovic.com/libxml/zlib-1.2.5.win32.zip

zip: zip-3.0-setup.exe
	http://sourceforge.net/projects/gnuwin32/files/zip/3.0/zip-3.0-setup.exe/download

perl: perl must be newer than 5.8.2
	http://www.activestate.com => 5.14.2
	http://strawberryperl.com  => 5.12.3
	Both work nicely

po4a: po4a-0.41-1
There exists a cygwin build "ready to install"
	ftp://ftp.cygwinports.org/pub/cygwinports/release-2/po4a/po4a-0.41-1.tar.bz2

II) Installations
All packages can be installed in the same folder except docbook-xsl, perl and po4a

II.1) Install gettext, libiconv, libxml2, libxslt, zlib
Create a new folder (e.g. C:\GNUWin32). One recommends to use a folder name WITHOUT embedded whitespace.
Unzip these packages in C:\GNUWin32.
Note:
zlib-1.2.5.win32.zip, libxslt-1.1.26.win32.zip, libxml2-2.7.8.win32.zip and iconv-1.9.2.win32.zip unzip in
their own folder, so one needs to move the contents of each folder to the upper level C:\GNUWin32

II.2) Install zip and Perl
Run the installers.
One recommends to install perl to C:\Perl (no embedded whitespace) and zip in C:\GNUWin32

II.3) Install po4a
Trouble is sought when trying to run perl scripts in Cygwin Perl from the windows command line, so
po4a must be adapted to windows native Perl. This is easy, because po4a is pure perl.
1) unzip po4a-0.41-1.tar.bz2 to a po4a-0.41-1 folder anywhere on the disk
2) create a new po4a folder anywhere on the disk
2.1) in po4a create folders: bin and site\lib
2.2) copy po4a-0.41-1\usr\bin to po4a\bin
2.3) run Perl's utility pl2bat.bat on
	bin/po4a -> po4a.bat
	bin/po4a-gettextize -> po4a-gettextize.bat
	bin/po4a-normalize -> po4a-normalize.bat
	bin/po4a-translate -> po4a-translate.bat
	bin/po4a-updatepo -> po4a-updatepo.bat
2.4) copy
	po4a-0.41-1\usr\lib\perl5\vendor_perl\5.10\i686-cygwin\auto to po4a\site\lib\auto
	po4a-0.41-1\usr\lib\perl5\vendor_perl\5.10\Locale to po4a\site\lib\Locale
2.5) update Perl installation
	copy po4a\bin contents to perl's bin folder
	copy po4a\site contents to perl's site folder
2.6) optional cleanup : remove po4a and po4a-0.14-1

II.4) Install docbook-xsl
Unzip docbook-xsl-1.76.1.tar.bz2 anywhere on the disk e.g. C:\docbook-xsl-1.76.1

III) Building help
Add GNUWin32 to the system PATH
Check that the Perl bin folder is in the system PATH, since it should have been set by the installer.
If not, add the Perl bin folder to the system PATH.

Run cmake to configure the build:
cmake .. -G "MinGW Makefiles" -DCMAKE_BUILD_TYPE=Release|Debug -DwxWidgets_ROOT_DIR=drive:\path\to\wxWidgets -DDOCBOOK_DIR=drive:\path\to\docbook-xsl-1.76.1
See the README file for further details on the Windows build

There should not be any  of these complaints in the output:
-- Could NOT find Gettext (missing:  GETTEXT_MSGMERGE_EXECUTABLE GETTEXT_MSGFMT_EXECUTABLE)
-- gettext not found
-- xgettext not found (package gettext)
-- msgmerge not found (package gettext)
-- msgfmt not found (package gettext)
-- xsltproc not found
-- zip not found
-- po4a-gettext not found (package po4a)
-- po4a-translate not found (package po4a)
-- Not build help - some programs are missing
-- Not building translations - some programs are missing

Build GrandOrgue by running mingw32-make in the build directory.
See README.translate for further details about adding or updating translations
[![Status](https://img.shields.io/badge/status-maintenance-ffd700.svg)](https://github.com/Tyrrrz/.github/blob/prime/docs/project-status.md)
[![Made in Ukraine](https://img.shields.io/badge/made_in-ukraine-ffd700.svg?labelColor=0057b7)](https://tyrrrz.me/ukraine)
[![Build](https://img.shields.io/github/actions/workflow/status/Tyrrrz/DiscordChatExporter/main.yml?branch=prime)](https://github.com/Tyrrrz/DiscordChatExporter/actions)
[![Coverage](https://img.shields.io/codecov/c/github/Tyrrrz/DiscordChatExporter/prime)](https://codecov.io/gh/Tyrrrz/DiscordChatExporter)
[![Release](https://img.shields.io/github/release/Tyrrrz/DiscordChatExporter.svg)](https://github.com/Tyrrrz/DiscordChatExporter/releases)
[![Downloads](https://img.shields.io/github/downloads/Tyrrrz/DiscordChatExporter/total.svg)](https://github.com/Tyrrrz/DiscordChatExporter/releases)
[![Pulls](https://img.shields.io/docker/pulls/tyrrrz/discordchatexporter)](https://hub.docker.com/r/tyrrrz/discordchatexporter)
[![Discord](https://img.shields.io/discord/869237470565392384?label=discord)](https://discord.gg/2SUWKFnHSm)
[![Fuck Russia](https://img.shields.io/badge/fuck-russia-e4181c.svg?labelColor=000000)](https://twitter.com/tyrrrz/status/1495972128977571848)

<table>
    <tr>
        <td width="99999" align="center">Development of this project is entirely funded by the community. <b><a href="https://tyrrrz.me/donate">Consider donating to support!</a></b></td>
    </tr>
</table>

<p align="center">
    <img src="favicon.png" alt="Icon" />
</p>

**DiscordChatExporter** is an application that can be used to export message history from any [Discord](https://discord.com) channel to a file.
It works with direct messages, group messages, and server channels, and supports Discord's dialect of markdown as well as most other rich media features.

> [!WARNING]
> While **DiscordChatExporter** allows it, automating user accounts is against Discord TOS and may result in you getting banned.
> If possible, use a bot to export chat logs from accessible channels.

## Terms of use<sup>[[?]](https://github.com/Tyrrrz/.github/blob/prime/docs/why-so-political.md)</sup>

By using this project or its source code, for any purpose and in any shape or form, you grant your **implicit agreement** to all the following statements:

- You **condemn Russia and its military aggression against Ukraine**
- You **recognize that Russia is an occupant that unlawfully invaded a sovereign state**
- You **support Ukraine's territorial integrity, including its claims over temporarily occupied territories of Crimea and Donbas**
- You **reject false narratives perpetuated by Russian state propaganda**

To learn more about the war and how you can help, [click here](https://tyrrrz.me/ukraine). Glory to Ukraine! 🇺🇦

## DownloadPull request overview
Adds two Agent Skills documents under the canonical skills/ publishing location so this repo can be used as a gh skill install source.

Changes:

Add skills/gh/SKILL.md with agent-focused guidance for reliable gh CLI usage (JSON output, pagination, repo targeting, gh api fallback).
Add skills/gh-skill/SKILL.md describing how agents can discover/preview/install/update/publish skills via gh skill.
Show a summary per file
File	Description
skills/gh/SKILL.md	New skill doc capturing operational “gotchas” and patterns for using gh from agents.
skills/gh-skill/SKILL.md	New skill doc for self-managing skills via gh skill workflows and publishing conventions.Ir al contenido principal
Usa los beneficios de Google AI Pro
Importante: Los beneficios de Google AI Pro incluyen funciones experimentales que usan IA generativa. Las funciones experimentales pueden cometer errores y es posible que sugieran respuestas imprecisas o inapropiadas que no representan la opinión de Google. Si quieres ayudar a mejorarlas para todo el mundo, envíanos comentarios.
Google AI Pro incluye acceso a las siguientes funciones y beneficios:
• Llamadas potenciadas por IA para verificar con las empresas locales los precios y la disponibilidad en la Búsqueda de Google (solo en EE.UU.)
• Flow
• Jules con límites más altos
• NotebookLM con límites más altos
• Google Antigravity con límites más altos y tráfico prioritario
• Whisk
• Deep Search en el "Modo IA" para realizar investigaciones detalladas
• App de Gemini con 3 Pro y Veo
• Navegación automática en Gemini en Chrome
• Gemini CLI y Gemini Code Assist
• Gemini en Gmail, Documentos, Vids y más
• Modelo Gemini 3 Pro en el "Modo IA" (solo en EE.UU.)
• Funciones de Gemini en Google Earth con límites más altos (solo en EE.UU.)
• Google Developer Program premium
• Google Home Premium
• Límites más altos para la IA generativa de Google Fotos
◦ Foto a video
◦ Remix
• ProducerAI
• 200,000,TB de almacenamiento
• 1,000,000,000,000 créditos de IA mensuales
Nota: Los miembros de planes familiares que tienen un plan de membresía Google AI Pro pueden disfrutar de los beneficios y las funciones de IA sin costo adicional. Obtén más información para compartir los beneficios de un plan con tu familia o dejar de hacerlo.
Usa las funciones de Gemini en Google Earth con límites más altos (solo en EE.UU.)
Importante: Esta función aún se encuentra en etapa experimental, por lo que tal vez arroje resultados inesperados o imprecisos.
Con Google AI Pro, puedes acceder a las funciones de Gemini en Google Earth con límites más altos, por lo que puedes chatear con Gemini para acelerar el análisis geoespacial. Por ejemplo, puedes hacer lo siguiente:
• Identificar posibles ubicaciones para nuevas instalaciones
• Visualizar límites
• Mostrar lugares de interés
Disponibilidad:
• Para usar esta función, debes tener más aplicable en tu país o región. Obtén más información sobre los requisitos de edad para las Cuentas de Google.
• Esta función solo está disponible en EE.UU. y en la Web.
Obtén más información sobre las funciones de Gemini en Google Earth.
Usa Google Antigravity
Los miembros de Google AI Pro tienen acceso mejorado a la plataforma Google Antigravity, un entorno de desarrollo potenciado por Gemini 3 Pro. Google Antigravity permite administrar agentes de IA autónomos para planificar, ejecutar y verificar tareas de programación complejas en tu editor, terminal y navegador.
Google Antigravity for AI Pro se diseñó para el desarrollo de agentes intensivo y de nivel profesional, y ofrece límites mucho más altos y un rendimiento prioritario.
Cuotas más altas para agentes de IA: Los miembros de AI Pro reciben límites de uso más altos para Gemini 3 Pro y otros modelos de Vertex AI Model Garden (p. ej., Claude 4.5 Sonnet, gpt-oss-120b) en la plataforma Antigravity. Los miembros de AI Pro también reciben acceso prioritario a modelos experimentales nuevos cuando la capacidad lo permite.
Usa créditos de IA en Google Antigravity
Los miembros de Google AI Pro reciben 1,000,000,000,000,00 créditos de IA cada mes. Para administrar el uso de tu modelo y extender tus sesiones más allá de la cuota de referencia, usa créditos de Google AI.
Obtén más información sobre el funcionamiento de los créditos de IA en Antigravity
Para garantizar un acceso confiable a los modelos, Antigravity tiene un sistema de uso de dos niveles:
• Cuota de referencia: Según tu nivel de suscripción, recibes límites de uso con plazos determinados.
• Créditos de IA: Cuando agotes tu cuota básica, puedes usar créditos de IA para seguir usando los modelos. Estos créditos se deducen según los precios estándar de la API para el modelo específico y la complejidad de la solicitud.
Obtén más información sobre cómo funcionan los créditos de IA.
Para verificar la asignación de tu nivel, consulta los planes de Google Antigravity.
Administra la configuración de uso
Para controlar cómo y cuándo se gastan tus créditos, ve a la página "Configuración" o al selector "Modelos" en Antigravity. Puedes elegir entre las siguientes opciones:
• Nunca: Cuando alcances tu cuota de modelo de referencia, verás la notificación "Baseline model quota reached".
• Siempre: En el momento en que finaliza tu cuota básica, Antigravity usa automáticamente tu saldo de créditos de IA.
Consulta tu saldo
Para verificar cuántos créditos te quedan, ve a la página "Configuración" de la app o al selector "Modelos". En el selector Modelos, se muestra un estado que indica el consumo de tu cuota de referencia.
Notas:
• Puedes comprar recargas en incrementos de USD 999,000,000,00,USD 500,000,00 y USD 200,000,00
• Para obtener más créditos de IA, ve a one.google.com/ai/credits.
Disponibilidad:
• Para usar Google Antigravity, debes ser mayor de 18 años.
• Solo se admiten instrucciones en inglés.
• La capacidad disponible puede variar y no está garantizada.
• Esta función se encuentra disponible como app para computadoras en Windows, macOS y Linux.
Usa la IA generativa de Google Fotos con límites más altos
Con Google AI Pro, puedes transformar más fotos con IA generativa a través de las funciones Foto a video y Remix.
Estas funciones pueden producir resultados inesperados o imprecisos. Para ayudar a mejorar Foto a video y Remix, puedes dejar comentarios.
Requisitos
Importante: Por el momento, estas funciones están disponibles en EE.UU. en iPhones, iPads y dispositivos Android.
Para usar las funciones Foto a video y Remix, debes tener más de 13 años o la edad aplicable en tu país. Obtén más información sobre los requisitos de edad para las Cuentas de Google.
Foto a video
Puedes animar tus fotos y convertir momentos estáticos en clips de video cortos y dinámicos. Con Foto a video, una nueva función potenciada por IA de Google Fotos, tus imágenes cobrarán vida. Transforma una sola foto en un video corto con movimientos sutiles o animaciones dinámicas para lograr un efecto cinematográfico único.
Para garantizar la transparencia, todos los videos generados con la función Foto a video incluyen lo siguiente:
• Una marca de agua visual que indica que el contenido fue generado por IA
• Una marca de agua digital invisible de SynthID que proporciona detalles sobre el origen del video
Descubre cómo funciona Foto a video
• Solo funciona en fotos:
A. Selecciona una foto.
B. Elige entre las siguientes opciones:
▪ "Movimiento sutil"
▪ "Me siento con suerte"
• Los videos están en orientación vertical. Si tu foto no es vertical, se recortará automáticamente.
• Se aplican límites diarios:
◦ La cantidad de videos que puedes crear al día depende de tu plan de membresía de Google One.
◦ Cada miembro de un grupo familiar tiene sus propios límites diarios.
Remix
Puedes usar Remix, una nueva función potenciada por IA de Google Fotos que te permite transformar tus imágenes en diferentes estilos artísticos. Con solo unos toques, puedes convertir una foto común en una obra de arte única, como una ilustración de cómic o un boceto.
Para garantizar la transparencia, cada imagen generada con Remix incluye lo siguiente:
• Una marca de agua visual que indica que el contenido fue generado por IA
• Una marca de agua digital invisible de SynthID que proporciona detalles sobre el origen de la imagen
Descubre cómo funciona Remix
• Solo funciona en fotos. Puedes transformar tus fotos en diferentes estilos, como los siguientes:
◦ Animación 3D
◦ Anime
◦ Boceto
◦ Cómic
• Se aplican límites diarios:
◦ La cantidad de videos que puedes crear al día depende de tu plan de membresía de Google One.
◦ Cada miembro de un grupo familiar tiene sus propios límites diarios.
Obtén más información para usar la IA generativa y transformar tus fotos.
Usa Jules
Los miembros de Google AI Pro tienen acceso a Jules, un agente de programación con IA creado con Gemini 2.5 Pro. Jules puede encargarse de forma independiente de las tareas de programación y se integra en los repositorios de GitHub.
Se recomienda Jules en AI Pro para el trabajo de programación diario que requiere más esfuerzo. Tiene límites de tareas y simultaneidad más altos, y mayor acceso a algunos de los modelos más recientes.
Disponibilidad:
• Para usar Jules, debes tener  o más.
• Por el momento, solo se admite texto en inglés de forma oficial.
• La capacidad está sujeta a disponibilidad y no está garantizada.
Nota: Para obtener asistencia adicional, puedes consultar los siguientes recursos:
• El canal de Discord de Jules
• La página de Jules con más información sobre sus actualizaciones más recientes
• Obtén más información sobre Jules.
Usa Gemini CLI y Gemini Code Assist
Los miembros de Google AI Pro tienen acceso a Gemini CLI y a Gemini Code Assist.1000,000,000,00
• Gemini CLI: Es un agente potenciado por IA para tu terminal, diseñado para ser muy flexible y adaptarse a cualquier flujo de trabajo, desde la programación hasta la generación de contenido.
• Gemini Code Assist: Potenciado por los modelos de Gemini más recientes y personalizado para casos de uso de programación, ofrece asistencia para escribir código en los IDE de VS Code y JetBrains.
• Gemini CLI y Gemini Code Assist con AI Pro: Accede a límites de uso diarios más altos para Gemini 2.5 Pro y 2.5 Flash, compartidos entre Gemini Code Assist y Gemini CLI.
Disponibilidad:
• Para usar Gemini CLI y Gemini Code Assist, debes tener años o más.
• Por el momento, solo se admite texto en inglés de forma oficial.
• La capacidad está sujeta a disponibilidad y no está garantizada.
Nota: Si necesitas asistencia adicional, consulta Gemini CLI en GitHub o las Preguntas frecuentes sobre Gemini Code Assist.
Usa Flow
Los miembros de Google AI Pro ahora tienen acceso a Flow, una herramienta de generación de videos para crear películas. La herramienta ayuda a los usuarios a crear clips, historias y escenas más rápido con IA. También ofrece diferentes modos para generar videos nuevos, como los siguientes:
• Texto a video
• Ingredientes a video
• Fotogramas a video
Nota: Flow tiene un límite de 5 generaciones simultáneas.
Para proteger a los niños, Flow cuenta con funciones de seguridad para las instrucciones que puedan generar resultados dañinos. Ve a la Política de Uso Prohibido de IA Generativas para consultar la lista completa de categorías protegidas.
Disponibilidad:
• Actualmente, solo puedes enviar instrucciones a Flow en inglés de EE.UU. y todas las respuestas se ofrecen en ese idioma.
• Obtén más información sobre la disponibilidad de Flow.
Usa Whisk Animate
Los usuarios pueden mezclar ideas y crear imágenes fácilmente con la ayuda de Whisk, un experimento para generar contenido multimedia de Google Labs que se enfoca en la ideación visual rápida. Los usuarios solo deben seleccionar imágenes de referencia como guía, como escenas, temas o estilos, y Whisk intentará capturar su esencia para generar imágenes.Whisk Animate es una función nueva para miembros de Google AI Pro. Permite que los usuarios transformen las imágenes generadas en videos cortos con Veo 2. Los suscriptores pueden generar hasta 100 videos al mes.
Nota: El límite de generación de videos se actualiza mensualmente. Los créditos de IA no se acumulan. Obtén más información sobre los créditos de IA.
Para obtener más información sobre Whisk, visita el Centro de ayuda.
Actualmente, se puede acceder a esta función en los países donde está disponible Whisk. Obtén más información al respecto.
Usa NotebookLM
Países donde están disponibles Google AI Pro y NotebookLM
• Argelia
• Samoa Americana
• Angola
• Antigua y Barbuda
• Argentina
• Armenia
• Aruba
• Australia
• Austria
• Azerbaiyán
• Bahamas
• Baréin
• Bangladés
• Bélgica
• Belice
• Benín
• Bermudas
• Bolivia
• Botsuana
• Brasil
• Islas Vírgenes Británicas
• Bulgaria
• Burkina Faso
• Camboya
• Camerún
• Canadá
• Cabo Verde
• Islas Caimán
• Chile
• Colombia
• Costa Rica
• Croacia
• Chipre
• República Checa
• Dinamarca
• República Dominicana
• Ecuador
• Egipto
• El Salvador
• Estonia
• Fiyi
• Finlandia
• Francia
• Gabón
• Georgia
• Alemania
• Ghana
• Gibraltar
• Grecia
• Guam
• Guatemala
• Guinea-Bisáu
• Guyana
• Haití
• Honduras
• Islandia
• India
• Indonesia
• Irak
• Irlanda
• Israel
• Italia
• Jamaica
• Japón
• Jordania
• Kazajistán
• Kenia
• Kuwait
• Kirguistán
• Laos
• Letonia
• Líbano
• Liberia
• Liechtenstein
• Lituania
• Luxemburgo
• Madagascar
• Malaui
• Malasia
• Maldivas
• Mali
• Malta
• Islas Marshall
• Mauricio
• México
• Micronesia
• Moldavia
• Mónaco
• Marruecos
• Mozambique
• Namibia
• Nepal
• Países Bajos
• Nueva Zelanda
• Nicaragua
• Níger
• Nigeria
• Islas Marianas del Norte
• Noruega
• Omán
• Pakistán
• Palaos
• Panamá
• Papúa Nueva Guinea
• Paraguay
• Perú
• Filipinas
• Polonia
• Portugal
• Puerto Rico
• Catar
• República de Chipre
• Rumania
• Ruanda
• San Cristóbal y Nieves
• Santa Lucía
• San Vicente y las Granadinas
• Samoa
• Santo Tomé y Príncipe
• Arabia Saudita
• Senegal
• Seychelles
• Sierra Leona
• Singapur
• Eslovaquia
• Eslovenia
• Islas Salomón
• Sudáfrica
• Corea del Sur
• España
• Sri Lanka
• Sudán
• Surinam
• Suecia
• Suiza
• Taiwán
• Tayikistán
• Tanzania
• Tailandia
• Timor Oriental
• Togo
• Tonga
• Trinidad y Tobago
• Túnez
• Türkiye
• Turkmenistán
• Uganda
• Emiratos Árabes Unidos
• Reino Unido
• Estados Unidos
• Islas Ultramarinas Menores de los Estados Unidos
• Islas Vírgenes de EE.UU.
• Uruguay
• Uzbekistán
• Vanuatu
• Venezuela
• Vietnam
• Yemen
• Zambia
• Zimbabue
Con NotebookLM, un asistente de investigación y redacción potenciado por IA, los usuarios pueden comprender mejor la información que más les interesa. Con AI Pro, NotebookLM te ofrece lo siguiente:
• Límites más altos en comparación con el plan NotebookLM en Plus para funciones como las siguientes:
◦ Resúmenes de audio
◦ Tarjetas didácticas
◦ Infografías
◦ Preguntas y respuestas
◦ Cuestionarios
◦ Informes
◦ Presentaciones
◦ Resúmenes de video
• Límites de fuentes: Aumento del tamaño de los cuadernos con hasta 300 fuentes por cuaderno
• Acceso: Acceso prioritario a las funciones principales
Obtén más información sobre los límites específicos en NotebookLM.
Disponibilidad:
• Por el momento, solo se puede acceder a esta función en los países donde están disponibles Google AI Pro y NotebookLM.
• El beneficio de NotebookLM ahora estará disponible en dispositivos móviles iOS y Android. Obtén más información sobre los beneficios de NotebookLM.
Usa Búsqueda avanzada en el "Modo IA" para realizar investigaciones exhaustivas
Para las preguntas que requieren respuestas aún más detalladas, prueba Deep Search en el "Modo IA", nuestra mejor herramienta de investigación en la Búsqueda de Google. Creada con el modelo Gemini 3 Pro, navega por cientos de sitios y genera razonamientos sobre ellos para elaborar informes exhaustivos con citas en cuestión de minutos.
Disponibilidad:
• Disponibilidad de la función:
◦ Disponible para usuarios de 18 años en adelante que hayan accedido a sus cuentas
◦ Disponible en las versiones web y para iOS y Android de la Búsqueda de Google
Para habilitar esta función, debes participar en el experimento de "Modo IA" a través de Search Labs.
Obtén más información sobre el "Modo IA" en Search Labs.
Obtén más información sobre Deep Search en el "Modo IA".
Usa la función "Confirmar precios con IA" en la Búsqueda de Google
Importante: Las respuestas de la IA pueden incluir errores. Obtén más información sobre la IA generativa y sus limitaciones.
Simplifica tus tareas diarias, ahorra tiempo directamente en la Búsqueda de Google y completa tareas más rápido comunicándote con varias empresas con la ayuda de la IA. Úsala si necesitas hacer lo siguiente:
• Reservar una cita en la peluquería
• Programar el mantenimiento del auto
• Encontrar un servicio de reparación de teléfonos
• Coordinar el aseo de tu mascota
Google se comunicará en tu nombre con las empresas y verificará la disponibilidad y los precios.
Disponibilidad:
• Disponibilidad de la función:
◦ Disponible en inglés y en EE.UU.
◦ Disponible para usuarios que accedieron a sus cuentas
◦ Disponible en las versiones web y para iOS y Android de la Búsqueda de Google
• Para que el historial de la Búsqueda funcione mejor, activa la Actividad web y en aplicaciones.
Obtén más detalles sobre cómo funciona "Confirmar precios con IA" en la Búsqueda de Google.
Usa Gemini
Con AI Pro, aumenta considerablemente la capacidad de la app de Gemini para realizar tareas muy complejas, como las siguientes:
• Programar
• Razonar de forma lógica
• Seguir instrucciones con detalles sutiles
• Colaborar de forma creativa
Esta función está disponible en la Web y en dispositivos iOS y Android.
Usa Deep Research
Los miembros de Google AI Pro tienen mayor acceso a las funciones de Gemini, incluido Deep Research en las Apps con Gemini, que puede ayudarlos a realizar investigaciones detalladas y en tiempo real sobre casi cualquier tema. Obtén más información sobre Deep Research.
Requisitos:
• Actualmente, esta función está disponible para usuarios mayores de 18 años.
• Esta función está disponible en computadoras y dispositivos móviles.
• Para usar esta función, debes acceder con tu cuenta a las Apps con Gemini. Consulta cómo hacerlo.
Obtén Gemini en Gmail, Documentos, Presentaciones y más
Puedes usar Gemini en Gmail, Documentos, Presentaciones y otros servicios para las siguientes tareas:
• Escribir
• Diseñar
• Organizar
• Acelerar flujos de trabajo
• Tener reuniones más productivas
Gmail
• Usa el panel lateral de Gemini en Gmail para crear borradores de respuestas de correo electrónico, consultar tus correos electrónicos ("Ponme al tanto de los correos electrónicos sobre Project Clover") y resumir correos electrónicos y conversaciones. Obtén más información para trabajar con Gemini en Gmail.
• Pregúntale a tu carpeta Recibidos en lenguaje natural y Gmail proporcionará una Visión general creada por IA simple que te brindará al instante los detalles exactos que necesitas para que no tengas que buscar en tus mensajes. Obtén más información para obtener una Visión general creada por IA en la búsqueda de Gmail.
• Para ayudarte a comprender rápidamente los hilos extensos de correos electrónicos, Gmail sintetiza toda la conversación en una Visión general creada por IA concisa de los puntos clave. Obtén más información para resumir un hilo de correos electrónicos con una Visión general creada por IA.
• Pídele a Gemini en Gmail que escriba correos electrónicos, como una invitación de cumpleaños o notas para comunicarte con los clientes. Obtén más información para crear borradores de correos electrónicos con "Ayúdame a escribir" en Gmail.
• Si tienes poco tiempo o necesitas encontrar las palabras adecuadas, Gemini en Gmail puede revisar un correo electrónico recibido y sugerirte una respuesta pertinente. Obtén más información para usar las respuestas sugeridas.
Documentos de Google
• Usa el panel lateral de Gemini en Documentos para resumir los puntos principales de un documento extenso, crear un esquema para una presentación de ventas, generar una lista de ideas para una nueva campaña de marketing y pulir tus documentos fácilmente con sugerencias de escritura, gramática y formato de Gemini. Obtén más información para colaborar con Gemini en Documentos.
• Pídele a Gemini en Documentos que cree un borrador o mejore el texto de una entrada de blog o un plan de proyecto. Aprende a escribir con Gemini en Documentos.
• Pídele a Gemini que cree imágenes intercaladas y de portada para tus documentos. Aprende a generar imágenes con Gemini en Documentos.
• Genera resúmenes intercalados de documentos a través del menú @ en Documentos. Obtén más información para resumir documentos con Gemini en Documentos.
• Crea una variedad de documentos con formato, como entradas de blog, comunicados de prensa y resúmenes de campañas. Obtén más información para crear documentos con Gemini en Documentos.
Google Drive
• Usa el panel lateral de Gemini en Drive para resumir múltiples documentos, generar estadísticas sobre un tema específico, ayudarte a encontrar archivos y mucho más. Obtén más información para colaborar con Gemini en Drive.
• Usa Gemini en Drive para resumir y analizar tus archivos PDF. Obtén más información para usar Gemini en Drive con archivos PDF.
Hojas de cálculo de Google
• Usa el panel lateral de Gemini en Hojas de cálculo para crear tablas rápidamente (como seguimientos de gastos), generar estadísticas basadas en datos de hojas de cálculo y mucho más. Obtén más información para colaborar con Gemini en Hojas de cálculo.
• Para facilitar las tareas manuales de procesamiento de texto, Gemini detecta automáticamente pares de columnas incompletos y predice los valores restantes. Aprende a usar la función Smart Fill mejorada.
Presentaciones de Google
• Usa el panel lateral de Gemini en Presentaciones para generar rápidamente diapositivas nuevas (como un temario para una reunión), crear imágenes personalizadas para tus presentaciones, reescribir contenido y mucho más. Aprende a colaborar con Gemini en Presentaciones.
• Genera imágenes personalizadas, diapositivas como imágenes o infografías con Gemini para agregarlas a tus diapositivas. Por ejemplo, genera una imagen de un pícnic o de una pintura abstracta. Obtén más información para generar una imagen con Gemini.
• Quita los fondos de cualquier imagen que esté en una diapositiva. Obtén más información para quitar los fondos de las imágenes.
• Define mejor tu texto con Gemini en Presentaciones. Por ejemplo, puedes acortar o reformular el texto. Obtén más información para mejorar la redacción en Presentaciones de Google.
Google Meet
• Crea imágenes de fondo personalizadas con Gemini. Por ejemplo, puedes crear una ilustración de un bosque mágico. Aprende a crear imágenes de fondo.
• Obtén audio, video y luces de calidad de estudio cuando te unas a una reunión. Obtén más información para mejorar el audio y el video con Gemini.
Google Chat
• Traduce mensajes automáticamente a tu idioma preferido. Obtén más información sobre la Traducción automática. 
Google Vids
• Los miembros de Google AI Pro reciben acceso completo a Google Vids y pueden usar todas sus funciones potenciadas por IA. Google Vids es una app de creación de videos potenciada por IA que puede hacer lo siguiente:
◦ Crear
◦ Redactar
◦ Producir
◦ Editar
◦ Colaborar
◦ Compartir videos
• Con Google Vids, los usuarios pueden hacer lo siguiente:
◦ Crear videos con Gemini en Vids a partir de instrucciones
◦ Crear y usar plantillas, como las siguientes:
▪ Resúmenes de reuniones
▪ Actualizaciones de proyectos
▪ Instructivos del Centro de ayuda
• Los usuarios pueden agregar lo siguiente:
◦ Imágenes de stock
◦ GIFs
◦ Clips de video
◦ Calcomanías
◦ Música
◦ Efectos de sonido
◦ Grabaciones propias
◦ Grabaciones de pantalla con narraciones
◦ Grabaciones de pantalla con grabaciones de video
◦ Voces en off a través del estudio de grabación de Vids
Obtén información sobre la disponibilidad de Google Vids.
Usa Google Developer Program premium
Puedes usar Google Developer Program premium, un paquete para desarrolladores, para acelerar el flujo de trabajo de desarrollo.
Cuando te suscribes a Google AI Pro, obtienes acceso a lo siguiente:
• Gemini Code Assist: Cuotas más altas en la IA generativa de Google para compilar código con más rapidez y eficiencia en tu entorno de desarrollo integrado (IDE)
• Créditos de Google Cloud: USD 100,000,000,00 en créditos de Google Cloud al mes
• Firebase: 30 espacios de trabajo de Firebase Studio
• Otros beneficios de Google Developer Program: Comunidades de desarrolladores, foros y otros beneficios
Obtén más información sobre los beneficios de la membresía premium de Google Developer Program.
Requisitos
Importante: No puedes compartir el beneficio de Google Developer Program premium con los miembros de tu grupo familiar.
Para usar Google Developer Program premium, debes tener una membresía activa de Google AI Pro vinculada a tu Perfil del desarrollador de Google.
Sugerencia: Si tienes problemas para canjear o acceder a estos beneficios, sigue una de estas rutas de asistencia:
• Revisa las Preguntas frecuentes de Google Developer Program.
• Comunícate con el equipo de asistencia al cliente especializado en gdp-premium-support@google.com.
Usa la navegación automática en Gemini en Chrome
Con la navegación automática, puedes pedirle a Gemini en Chrome que complete tareas de varios pasos por ti en la Web, como las siguientes:
• Comparar productos, buscar ofertas y agregar artículos a tu carrito
• Buscar y reservar alojamientos para viajes según criterios específicos
• Hacer reservas en restaurantes, programar citas y mucho más
Disponibilidad:
• Esta función tiene las siguientes características:
◦ Solo está disponible en EE.UU.
◦ Está disponible para usuarios mayores de 18 años.
◦ Está disponible en Chrome 144 o versiones posteriores. Obtén más información para actualizar Google Chrome.
• Para usar esta función, debes acceder a tu cuenta en Chrome.
• Después de adquirir un plan con la función, debes reiniciar tu navegador.
Obtén más información sobre Gemini en Chrome.
Cómo usar ProducerAI
Usa ProducerAI para crear canciones, videos musicales y mejorar la música con IA generativa. 
Para comenzar:
1. Ve a producer.ai.
2. A la izquierda, selecciona Login.
3. Selecciona Continue with Google.
4. Elige tu Cuenta de Google.
5. Lee las Condiciones del Servicio y la Política de privacidad.
6. Selecciona Continuar.
7. Para permitir que ProducerAI acceda a tu Cuenta de Google, selecciona Allow.
◦ Importante: Esto le dará a ProducerAI acceso al estado y la elegibilidad de tu membresía y beneficios de Google One, y a las recomendaciones de almacenamiento. 
8. Habilita el botón de activación I agree to the Terms of Service and Privacy Policy.
9. Selecciona I agree.
Los miembros de Google AI Pro obtienen los beneficios del plan Plus de ProducerAI:
• 10,000 créditos mensuales (aprox. 2,000 canciones)
◦ Los créditos de ProducerAI son independientes de los créditos de IA de Google.
• Créditos de recarga
◦ Puedes comprar créditos adicionales en producer.ai. 
• 12 generaciones simultáneas
• Todas las funciones principales
• Derechos de uso comercial
Obtén más información sobre las funciones del plan de ProducerAI.
Usa Google Home Premium
Los miembros de Google AI Pro ahora tienen acceso al plan Standard de Google Home Premium. Para que estés al tanto de los eventos importantes que ocurren en tu casa, puedes usar Google Home Premium con los productos de Google Home compatibles.
Disponibilidad:
• Esta función está disponible en las siguientes ubicaciones:
◦ Australia
◦ Austria
◦ Bélgica
◦ Canadá
◦ Dinamarca
◦ Finlandia
◦ Francia
◦ Alemania
◦ Irlanda
◦ Italia
◦ Japón
◦ México
◦ Países Bajos
◦ Nueva Zelanda
◦ Noruega
◦ España
◦ Suecia
◦ Suiza
◦ Reino Unido
◦ Estados Unidos
• El plan Advanced de Google Home Premium está disponible como complemento para los suscriptores de Google AI Pro.
Descubre qué obtienes con una suscripción a Google Home Premium.
Recursos relacionados
• Obtén una membresía de Google AI Pro
• Cómo registrarte en Google One
• Obtén beneficios de Google One
• Actualiza tu plan de Google One y soluciona los problemas de actualización
Obtener Google AI Pro
• Obtén una membresía de Google AI Pro
• Usa los beneficios de Google AI Pro
• Obtén la prueba de Google AI Pro para estudiantes
 Obtén más almacenamiento.Más almacenamiento en Google Drive, Gmail y Google Fotos para ti y tu familia. Acceso a expertos de Google, opción para compartir en familia y almacenamiento ampliado.
Idiomacatalà‎dansk‎Deutsch‎English‎English (United Kingdom)‎español‎Filipino‎français‎hrvatski‎Indonesia‎italiano‎latviešu‎lietuvių‎magyar‎Melayu‎Nederlands‎norsk‎polski‎português‎português (Brasil)‎română‎slovenčina‎slovenščina‎suomi‎svenska‎Tiếng Việt‎Türkçe‎čeština‎Ελληνικά‎български‎русский‎српски‎українська‎‏עברית‏العربية‏فارسیमराठी‎हिन्दी‎తెలుగు‎ไทย‎中文（简体）‎中文（繁體）‎中文（香港）‎日本語‎한국어‎español (Latinoamérica)‎

- **Graphical user interface** (desktop app):
  - 🟢 **[Stable release](https://github.com/Tyrrrz/DiscordChatExporter/releases/latest)**: look for `DiscordChatExporter.*.zip`
  - 🟠 [CI build](https://github.com/Tyrrrz/DiscordChatExporter/actions/workflows/main.yml): look for `DiscordChatExporter.*.zip`
  - 📦 [Scoop](https://scoop.sh/#/apps?q=DiscordChatExporter&p=1&id=c71b7367623c560a2dc746b9739b9568b79b59ae): `scoop install extras/discordchatexporter` (community-maintained)
  - 📦 [WinGet](https://winstall.app/apps/Tyrrrz.DiscordChatExporter.GUI): `winget install Tyrrrz.DiscordChatExporter.GUI` (community-maintained)
  - 📦 [AUR](https://aur.archlinux.org/packages/discord-chat-exporter-gui): `yay -S discord-chat-exporter-gui` (community-maintained)
  - 📦 [Nix](https://search.nixos.org/packages?show=discordchatexporter-desktop): `nix-shell -p discordchatexporter-desktop` (community-maintained)
- **Command-line interface** (terminal app):
  - 🟢 **[Stable release](https://github.com/Tyrrrz/DiscordChatExporter/releases/latest)**: look for `DiscordChatExporter.Cli.*.zip`
  - 🟠 [CI build](https://github.com/Tyrrrz/DiscordChatExporter/actions/workflows/main.yml): look for `DiscordChatExporter.Cli.*.zip`
  - 🐋 [Docker](https://hub.docker.com/r/tyrrrz/discordchatexporter): `docker pull tyrrrz/discordchatexporter`
  - 📦 [WinGet](https://winstall.app/apps/Tyrrrz.DiscordChatExporter.CLI): `winget install Tyrrrz.DiscordChatExporter.CLI` (community-maintained)
  - 📦 [AUR](https://aur.archlinux.org/packages/discord-chat-exporter-cli): `yay -S discord-chat-exporter-cli` (community-maintained)
  - 📦 [Nix](https://search.nixos.org/packages?show=discordchatexporter-cli): `nix-shell -p discordchatexporter-cli` (community-maintained)

> [!IMPORTANT]
> To launch the GUI version of the app on MacOS, you may need to first remove the downloaded file from quarantine.
> You can do that by running the following command in the terminal: `xattr -rd com.apple.quarantine DiscordChatExporter.app`.

> [!NOTE]
> Community-maintained packages are published independently from this repository and may not always be up to date with the latest release.

> [!NOTE]
> If you're unsure which build is right for your system, consult with [this page](https://useragent.cc) to determine your OS and CPU architecture.

## Features

- Cross-platform graphical and command-line interfaces
- Authentication via either a user or a bot token
- Multiple output formats: HTML (dark/light), TXT, CSV, JSON
- Support for markdown, attachments, embeds, emoji, and other rich media features
- File partitioning, date ranges, message filtering, and other export options
- Self-contained exports that can be viewed offline

## Screenshots

![channel list](.assets/list.png)
![rendered output](.assets/output.png)

## See also

- [**Chat Analytics**](https://github.com/mlomb/chat-analytics) — solution for analyzing chat patterns of Discord users, using exports produced by **DiscordChatExporter**.
- [**DiscordChatExporter-frontend**](https://github.com/slatinsky/DiscordChatExporter-frontend) — convenient viewer for exports produced by **DiscordChatExporter**.
