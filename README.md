
-------------------------------------------------------------------------
dab-cmdline-2: dab-cmdline with pictures 
-------------------------------------------------------------------------

![dab-cmdline](/dab-cmdline.png?raw=true)

For quite some time, the "dab-cmdline" library and example programs are
functioning. While originally set up as a library feature,
most use turned out to be as cmdline interface for DAB decoding..

While there are several variations of the command line examples
(i.e. there were examples 1 .. many), the most basic example,
example 2 was used most. This is no surprise, it implements just a simple
command line driven dab decoder.

Recently, while experimenting  with the Adalm Pluto,
I derived a simplified version of the combination "library and example 2",
by just removing lots of superfluous stuff from the sources of dab-cmdline.

Since the program is intended to be solely used as DAB audio decoder from
the command line, I removed lots of code dealing with packet data
and since there was no need for a separate "library", code could
be further simplified.

New is a configuration option to implement showing the slide(s), transmitted
as part of the service, on the screen. 

---------------------------------------------------------------------------
Building an executable
--------------------------------------------------------------------------

Libraries needed (both the libraries and the development packages):

 a. FFTWf
 b. Faad
 c. sndFile
 d. libsamplerate

For showing slides one has to install

  e. opencv

Of course, the support library for the device of choice need to
be installed as well.

if all libraries are installed, the process is simple,

	mkdir build
	cd build
	cmake .. -DXXX=ON -DYYY=ON -DZZZ=ON
	make

Note that if no device is selected, the SDRplay is selected as default.

When compiling on/for Linux on an X64, one might use

	-DX64_DEFINED=ON

The default in the CMakeLists.txt file is that "Pictures" are compiled in.
Switching it off by the command line is

	-DPICTURES=OFF

-------------------------------------------------------------------------
Copyrights
-------------------------------------------------------------------------
	
	Copyright (C)  2020
	Jan van Katwijk (J.vanKatwijk@gmail.com)
	Lazy Chair Computing

The dab-cmdline software is made available under the GPL-2.0. The dab-cmdline program uses a number of GPL-ed libraries, all rights gratefully acknowledged.
dab-cmdline is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
See the GNU General Public License for more details.

