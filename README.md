﻿PPSSPP - a fast and portable PSP emulator
=========================================

Created by Henrik Rydgård

Additional code by many contributors, see the Credits screen

Originally released under the GPL 2.0 (and later) in November 2012

Official website:
http://www.ppsspp.org/

No BIOS file required to play, PPSSPP is in many ways a "HLE" emulator.

To contribute, see [the development page](http://www.ppsspp.org/development.html).

For the latest source code, see [our github page](https://github.com/hrydgard/ppsspp).

For build instructions and other development tutorials, see the [wiki](https://github.com/hrydgard/ppsspp/wiki).


What's new in 1.0
-----------------
* Many, many bug fixes in JIT and elsewhere, improving compatibility
* Proper fix for Zenfone and related devices
* Direct3D 9 supported as a rendering backend on Windows, helps on old GPUs and can be faster than OpenGL in many cases
* You can now create specific configs per game
* FPU rounding modes much better supported, fixes the Peace Walker boss that was undefeatable. NOTE: This breaks saves in Gods Eater - you must turn off the better rounding, load your save game, turn it on and save.
* The JIT now uses SSE on x86, improving speed considerably. This does not affect ARM devices, that's for the next version or two.
* Improved audio output code on both Windows and Android, reducing audio latency on Windows and on some Android systems
* FFMPEG upgraded, fixed some music hangs ("GHA phase shifts")
* Some Ad Hoc improvements, coldbird.net is now default adhoc server. Ad Hoc still unfinished and hard to use.
* Graphics fixes: Bezier/spline drawing fixes, vertex position fixes, DanganRonpa on Adreno fixed, flat shading fixed, vertex cache improved, some PowerVR blockiness issues fixed, screen scaling filter added, Google Cardboard support
* Simulate UMD speed better, fixing hangs in several games
* More Atrac3 fixes, fixing hangs
* Somewhat better disk full handling
* Fixes to dynamic unloading of code, fixing problems in GEB and TRM 2/3
* Updated to SDL2 where applicable (Linux, Mac)
* Some new features, like analog/dpad-swap hotkey, graphics hack for Phantasy Star, show last bit of debug log in dev tools, etc

What's new in 0.9.9.1
-------------------
A few issues have been discovered in the release that need fixing, the Star Ocean fix had a bug and there are some unexpected slowdowns.

Improved sceMpegRingbufferAvailableSize -  UFC© Undisputed​™ 2010 now playable

Improved ISO File System - Bleach Soul Carnival 2 now in-game (but freeze when in menu)

What's new in 0.9.9
-------------------
* CLUT (paletted) texturing from framebuffers supported, fixing many graphical issues
  like the shadows in Final Fantasy: Type-0
* More types of framebuffer copies are now handled correctly, fixing a variety of graphical
  issues, like the sun in Burnout and many more
* Better savedata compatibility with the real PSP
* Support for more codecs used by "Custom BGM" and sometimes regular music in games: MP3, AAC
* PMP video format support
* Implemented some strange blending modes like ABSDIFF as shaders, fixing the outlines in DBZ Tag Team and more.
* Emulation of the vrot CPU instruction improved - it caused cracks in FF3 graphics before
* Many bugfixes around the UI, touch D-pad now works better when scaled large
* Workaround implemented to support Star Ocean's stencil trickery as efficiently as possible on all platforms
* Major corrections to module loading and memory management, fixing further games
* Bulgarian and Thai language translations were contributed
* Many, many more game fixes and bug fixes

What's new in 0.9.8
-------------------
* OpenGL ES 3 detection bug on Xperia devices fixed, graphics work again.
* More accurate audio mixing and emulation
* Software rendering and display list performance improvements
* Workaround for timing issue hanging Crash Tag Team Racing
* Galician language
* Built-in ARM disassembler improvements (dev feature)
* Fix for immersive mode volume key issue on Android Kitkat
* And more minor tweaks and fixes as always.

What's new in 0.9.7.1
---------------------
* Some critical bugfixes (rotation, haptic feedback on Android, etc)

What's new in 0.9.7
-------------------
* Several scheduling and audio fixes, fixing black screens in Yu Gi Oh games among other things.
* Screen rotation and immersive mode support on Android
* Large improvements to the software renderer (still not really playable, but looks right more
  often than not)
* New VPL allocator and bugfixes, fixing Pangya Golf performance problems.
* Some mpeg/video playback fixes, fixing Parappa The Rapper and others. Some issues remain.
* Fix save state bugs causing incompatibility between 32 and 64-bit platforms.
* Symbol map/debugger improvements
* Depth buffer copy, fixing Jeanne D'arc. May cause minor slowdowns though, this will be worked
  around in the future.
* MsgDialog fixes. Saving fixed in numerous games.
* Initial multitouch support on Windows 8 for on-screen controls.

What's new in 0.9.6
-------------------
* Large general speed improvements and assorted bug fixes
* "Software Skinning" option which speeds up many games with animated 3D characters
  (but may slow down a few, like Monster Hunter games - experiment with turning it off)
* Various fixes around stencil/alpha, reducing glow problems in Wipeout and Gods Eater Burst.
* Timing improvements making more games run at the correct FPS, also fixing some audio issues
* More debugger features
* Option for four-way touch dpad, avoiding diagonal dpad issues
* Better looking and individually resizable touch controls
* Add ability to switch UMD in multi-disc games (works for most)
* Emulate PSP-2000 rather than the 1000 model by default. Not much different in practice.
* Automatic install of games from ZIP files, like demos and many homebrew.
* VERY basic ad-hoc online play support, to be improved in future versions. See below.
* Software renderer improvements

What's new in 0.9.5
-------------------
* Many, many emulation fixes:
  - bezier/spline curve support, fixing LocoRoco and others
  - stencil clear emulation, fixing Final Fantasy IV text
* Performance improvements in some games
* Post-processing shaders like FXAA, scanlines, vignette
* More solid save states (we will try to keep them working from now on. Save states only upgrade forward,
  not backward to older versions though).
* Change render resolution independently of window size
* Massive debugger improvements
* Win32 menu bar is now translatable
* Multiple UI bugs were fixed, and the UI instantly changes when a new language is selected
* Win32: Ability to store PPSSPP's config files and memory stick files in places other than the same directory
* Android-x86 support
* Unofficial port for modified Xbox 360 consoles
* Atrac3+ plugin no longer required. Symbian now supports Atrac3+ audio.
* Symbian audio and ffmpeg is now threaded for more consistent media processing.
* Haptic feedback support for mobile devices.
* Accurate system information for mobile devices.
* Qt audio has been fixed.
* Analog controller support for Blackberry.


ADHOC SUPPORT (by Igor Calabria)
================================
This is based on coldbird's code: http://code.google.com/p/aemu/
All credit goes to him!

Status
------
Code is a bit of a mess and it's not fully functional yet, I still need to implement
some functions and add a upnp lib(really important for people with routers).

I did test it with some games(emulator <-> real psp with the server running locally)
and it's looking good:

* Worms Open Warfare: Ran just fine, I was able to play a whole match without problems
* Monster Hunter Freedom Unite: Runs fine too. Gathering Hall and embarking on quests works
* Dissidia Duodecim 012: Doesn't work. It requires some functions that I haven't implemented
yet. Also, it uses a port < 1000 and thats reserved for admin apps on linux, running the emu
as sudo "solves" it, but it's far from ideal.
* Pacman World Rally: Works too.

Update (Kyhel) :
---------------
* Now compiles on both Mac OSX and Windows. For more details on how to play and build
go to see there http://forums.ppsspp.org/showthread.php?tid=3595&pid=59241#pid59241
* Got it tested windows <-> mac osx <-> psp, it works
* Monster Hunter 3rd HD works too, as well as God Eater Burst.
