GBT PLAYER  v2.1.0
==================

A music player library and converter kit for Game Boy that can be used with RGBDS or GBDK:

RGBDS: [https://github.com/bentley/rgbds](https://github.com/bentley/rgbds)

GBDK: [http://gbdk.sourceforge.net/](http://gbdk.sourceforge.net/)

Licensed under the BSD license.

Copyright (C) 2009-2014 Antonio Niño Díaz.

All rights reserved.

Email: antonio_nd@outlook.com

Web:

[http://antoniond_blog.drunkencoders.com/](http://antoniond_blog.drunkencoders.com/)

[http://antoniond.drunkencoders.com/](http://antoniond.drunkencoders.com/)

Latest version:

[https://github.com/AntonioND/gbt-player](https://github.com/AntonioND/gbt-player)

Introduction
------------

GBT Player is a music creation environment for GB and GBC. It is composed by mod2gbt, which converts a mod file into a gbt (GameBoy Tracker) file, and gbt player, which will be used to play that song in the GB.

mod2gbt is writen in C, and should compile in every machine where you can code in C. Only a windows binary is included.

GBT Player is writen in 100% assembler. That means that it is FAST, it won't need a lot of CPU time (around 7%?), and you will have a lot of time for your game logic. There is source code for GBDK and RGBDS, the main free alternatives for GameBoy developement (in my opinion).

GBT Player is open source, and it is licensed under the BSD license. That means that you can use and modify it but you have to give credit for the original work. It would be nice to you tell me if you use it, anyway. :)

IMPORTANT NOTE: Version 1.x.x converted songs won't work with player version 2.0.0 or higher. They have to be converted again.

How to compile examples
-----------------------

- RGBDS: Put rgbasm, rgbfix and rgblink in the source folder and double clic the bat file. Compiled binary included.

- GBDK: Open the bat file, change it to set the correct path to your lcc binary and double clic the bat.

Notes
-----

A nice tracker to modify the mod file is OpenMPT. You can download it here:

[http://openmpt.org/](http://openmpt.org/)

I don't use bat files in my projects, I use makefiles, but I thought that the examples would be too simple for a makefile to be useful.

instr_test.gb is a sample of the default sounds.

range_test.gb is just a test of what notes the GB can reach (C3 - B8).

effects_test.gb tests arpeggio and "cut note" effects.

The mod file isn't 100% accurate. Sounds are a bit different from the real ones, so you should make roms and test them in emulators or real GB often.

Changelog
---------

- Version 2.1.0 (2014/5/24)
 - Fixed arpeggio effect. Now it keeps looping until tick = 0 (previously it only looped once). Loops 3 steps, not 4.
 - Added "Cut Note" effect.
 - Effects optimizations.

- Version 2.0.1 (2014/5/23)
 - Fixed effects in channels 1, 2 and 3 in GBDK version.

- Version 2.0.0 (2014/5/22)
 - Rewritten library and converter.
 - Arpeggio effect added.
 - Song size should be reduced to about 60-75% (but it can go as high as 150% if it uses effects all time in all channels).
 - Old converted song data won't work, songs have to be converted again.

- Version 1.2.1 (2014/5/15)
 - Fixed Bnn command.

- Version 1.2 (2014/5/1)
 - Fixed lots of things regarding the mod file template and mod2gbt, the converter. Old songs won't be converted right with this new version. You should copy pattern data into the new mod template and transpose it 17 semitones to make it work again.
 - Fixed a typo in a variable name.

- Version 1.1 (2013)
 - Fixed definitions for enabling and disabling channels.
 - Changed email address.

- Version 1.0 (2009)
 - Initial release

To Do
-----

- Store channel 3 samples in RAM to be able to change them in execution time by the user?
- End song callback? Special effect for callback? To synchronize game events or things like that.
- WLA-DX version.

Known bugs
----------

- Effect Dxx, when used the last step of a pattern, will jump 2 patterns instead of 1.
