# ALU_retrofeCustomCores

Update 4/27/2020
- Includes new RetroFE release 4/27/2020
- New script file added and removed all the [console].sh. It will automatically copy over the file
  defined in the conf file to make it easier to use.
- If you are using CoinOPS next download the /retrofe/collections folder as well. For Arcadia 6 low spec, you just
  need to add the customlauncher per game.
  
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
----------------------------------------------------------------------------------------------------------------------------
Conf call			Emulator						Filename
----------------------------------------------------------------------------------------------------------------------------
Amiga				Amiga							puae_libretro_alu_alpha-2.so
AtariLynx			AtariLynx						handy_libretro.so
C64				Commodore 64						vice_x64_libretro_alu_alpha-1.so
Coleco				Colecovision						cv_libretro.so
fbalpha2012			Final burn alpha 2012 (various consoles)		fbalpha2012_libretro.so
fbalpha2012_neogo		Final burn alpha 2012 neogeo				fbalpha2012_neogeo_libretro.so
gba				Gameboy Advance / Gameboy / Gameboy Color		mednafen_gba_libretro.so
genesis				Sega genesis / Master system				genesis_plus_gx_libretro.so
Mame2003Plus_lg			Mame2003Plus light gun update				mame2003_plus_libretro_lg.so
Mame2010			Mame2010 (built-in)
Mame2010_lg			Mame2010 light gun update				mame2010_libretro_LightGunUpdate.so
nes				Nestopia						nestopia_libretro.so
nesBI				Quicknes (built-in)					
Odyssey2			Odyssey 2						o2em_libretro_alu_alpha1.so			
snes				Super Nintendo (snes9x)					snes9x_libretro.so




Adding new emulators
------------------------------------------------------------------------------------------------------------------------
The shell script will look for the emulator name and copy it to the temp folder automatically
------------------------------------------------------------------------------------------------------------------------
1. Copy the emulator to [drive]/customcores folder
2. Create a new [emulator].conf file in the /retrofe/launchers folder
3. Edit the file and insert the following. Replace [filename] with the emulator filename [for example: emulator.so]

executable = runCustomCore.sh
arguments = /emulator/retroplayer /tmp/[filename] "%ITEM_FILEPATH%"

4. Save the file.
5. Now you can reference this file [without the conf] in the custom launcher for the game.



