# ALU_retrofeCustomCores To be Used Directly from the AtGames Legends Ultimate through USB Non-Root

Update 5/2/2020
 - Minor Updates

Update 5/1/2020
 - Added update retrofe core (5/1/2020)
 - Added support for FCEUMM, Mame2010 Samples and sounds, Atari 800, Mame2016, Mame2003 Dual joysticks, Sega CD, Turbo Grafx CD
 - Added support for ScummVM

Update 4/30/2020
 - Added update retrofe core (4/29/2020)
 - Optimized code for runCustomCore.sh and runlauncher.sh

Update 4/29/2020
 - Added support for bezels
 - place bezels in /retrofe/bezels folder

Update 4/27/2020
- Includes new RetroFE release 4/27/2020
- New script file added and removed all the [console].sh. It will automatically copy over the file
  defined in the conf file to make it easier to use.
- If you are using CoinOPS next download the /retrofe/collections folder as well. For Arcadia 6 low spec (you do not need that folder), you just need to add the customlauncher per game.
  
How to use:
-----------------------------------------------------------------------------------------------------------------

1. Extract the files to the root of your usb drive
2. Download the custom cores you need and place them into the /customcores folder
3. Copy your games and required files (i.e. roms, covers, logos, videos, etc)
4. In the collection you copied your games to go into the launchers folder and add a [name of the game].conf
5. Add the name of the emulator it will require (ie, nes, snes, mame2010_lg, etc)




Example of adding a game
------------------------------------------------------------------------------------------------------------------
If we add a game for the nes like Castlevania and we are using CoinOPS Arcadia 6 low spec as an example
We would copy the required files to their respective folders.

customcores/
	[ place your cores in here ]
retrofe/
	/ collections
		/- Arcade
			/launchers
				Castlevania.conf		[we create a file titled this]
										"nes" would be the only text inside the Castlevania.conf file (without the quotes)
			/medium_artwork
				/cover
					Castlevania.png
				/logo
					Castlevania.png
				/marquee
					Castlevania.png
				/video
					Castlevania.png
			/playlists
				2 Beat em Ups.txt		we would add "Castlevania" to the bottom of this file without the quotes
			/roms
				Castlevania.nes
			settings.conf				Add "nes" to list.extensions if not there (without the quotes)




Reference names to use in [name of game].conf depending on emulator
| Conf Call            | Emulator                                 | Filename                                       |
|----------------------|------------------------------------------|------------------------------------------------|
| Mame2003Plus         | Mame 2003 Plus (built-in)                |                                                |
| Amiga                | Amiga                                    | puae_libretro_alu_alpha-2.so                   |
| AtariLynx            | Atari Lynx                               | handy_libretro.so                              |
| C64                  | Commodore 64                             | vice_x64_libretro_alu_alpha-1.so               |
| Coleco               | Colecovision                             | cv_libretro.so                                 |
| fbalpha2012          | Final burn alpah 2012 (various consoles) | fbalpha2012_libretro.so                        |
| fbalpha_neogeo       | Final burn alpha 2012 neogeo             | fbalpha2012_neogeo_libretro.so                 |
| gba                  | Gameboy Advance                          | mednafen_gba_libretro.so                       |
| genesis              | Sega Genesis / Master System             | genesis_plus_gx_libretro.so                    |
| Mame2003Plus_lg      | Mame 2003 Plus Light Gun Update          | mame2003_plus_libretro_lg.so                   |
| TG16                 | Turbo Grafx 16                           | mednafen_supergrafx_libretro.so                |
| Mame2010             | Mame 2010 (built-in)                     |                                                |
| Mame2010_lg          | Mame 2010 Light gun                      | mame2010_libretro_LightGunUpdate.so            |
| nes                  | Nestopia                                 | nestopia_libretro.so                           |
| nesBI                | Quicknes (built-in) NES                  |                                                |
| Odyssey2             | Odyssey 2                                | o2em_libretro_alu_alpha1.so                    |
| snes                 | snes9x Super Nintendo                    | snes9x_libretro.so                             |
| fceumm               | FCEUMM (Nes)                             | fceumm_libretro.so                             |
| Mame2010SamplesSaves | Mame 2010 Samples and Saves              | mame2010_libretro_samplesandsaves.so           |
| Atari 800            | Atari 800                                | atari800_libretro.so                           |
| Mame2016             | Mame 2016                                | mame2016_libretro.so                           |
| Mame2003DualJoy      | Mame 2003 Dual Joysticks                 | mame2003_plus_libretro_custom_Dual_Joystick.so |
| SegaCD               | Picodrive (SegaCD)                       | picodrive_libretro.so                          |
| TGCD                 | PCE Fast (Turbo GrafxCD)                 | mednafen_pce_fast_libretro.so                  |
| ScummVM              | ScummVM (Dos)                            | scummvm_libretro.so, libm.so.6                 |
| PC Engine            | PC Engine                                | mednafen_supergrafx_libretro.so                |
|                      |                                          |                                                |
|                      |                                          |                                                |



Adding new emulators
------------------------------------------------------------------------------------------------------------------------
The shell script will look for the emulator name and copy it to the temp folder automatically
------------------------------------------------------------------------------------------------------------------------
1. Copy the emulator to [drive]/customcores folder
2. Create a new [emulator].conf file in the /retrofe/launchers folder
3. Edit the file and insert the following. Replace [filename] with the emulator filename [for example: emulator.so] located in the customcore folder.

executable = runCustomCore.sh
arguments = /emulator/retroplayer /tmp/[filename] "%ITEM_FILEPATH%"

4. Save the file.
5. Now you can reference this file [without the conf] in the custom launcher for the game.

*Note Some emulators may require require a separate executable to launch as it requires specific definitions that aren't in runCustomCore.sh
ScummVM has it's own executable as it requires extra definitions. It can be called using the runScummVM.sh


Bezels
-------------------------------------------------------------------------------------------------------------------------
Adding Bezels (Scripts will check bezels folder for matching title)
-------------------------------------------------------------------------------------------------------------------------
Make sure the file naming schema follows your rom and images. It is also case sensitive. Place png bezel into the /retrofe/bezels folder.



ScummVM
-------------------------------------------------------------------------------------------------------------------------
Important notes
-------------------------------------------------------------------------------------------------------------------------
To get ScummVM working follow the standard steps needed to add a game. In the roms section add the title of the game with the bat ending.
Place data files in /content/ports/ScummVM

IE. Space Quest 1.bat

That's it, have fun.



Sega CD
-------------------------------------------------------------------------------------------------------------------------
Important notes
-------------------------------------------------------------------------------------------------------------------------
To get Sega CD working follow the standard steps needed to add a game. In the roms sections copy the .cue file into there.
Place data files in /content/consoles/Sega - Sega CD


PC Engine CD
-------------------------------------------------------------------------------------------------------------------------
Important notes
-------------------------------------------------------------------------------------------------------------------------
To get PC Engine working follow the standard steps needed to add a game. In the roms sections copy the .cue file into there.
Place data files in /content/consoles/NEC - PC Engine CD


Turbografx CD
-------------------------------------------------------------------------------------------------------------------------
Important notes
-------------------------------------------------------------------------------------------------------------------------
To get Turbografx CD working follow the standard steps needed to add a game. In the roms sections copy the .cue file into there.
Place data files in /content/consoles/


