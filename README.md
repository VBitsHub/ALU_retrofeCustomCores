# ALU_retrofeCustomCores

Update 4/27/2020
- Includes new RetroFE release 4/27/2020
- New script file added and removed all the [console].sh. It will automatically copy over the file
  defined in the conf file to make it easier to use.
  

How to use:
-----------------------------------------------------------------------------------------------------------------

1. Extract the files to the root of your usb drive
2. Copy your games and required files (i.e. roms, covers, logos, videos, etc)
3. In the collection you copied your games to go into the launchers folder and add a [name of the game].conf
4. Add the name of the emulator it will require (ie, nes, snes, mame2010_lg, etc)




Example of adding a game
------------------------------------------------------------------------------------------------------------------
If we add a game for the nes like Castlevania and we are using CoinOPS Arcadia 6 low spec as an example
We would copy the required files to their respective folders.

retrofe/
	/ collections
		/- Arcade
			/launchers
				Castlevania.conf		 [we create a file titled this]
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
				2 Beat em Ups.txt     we would add "Castlevania" to the bottom of this file without the quotes
			/roms
				Castlevania.nes
			settings.conf				    Add "nes" to list.extensions if not there (without the quotes)




Reference names to use in [name of game].conf depending on emulator
--------------------------------------------------
Conf call			        Emulator
--------------------------------------------------
Amiga				          Amiga
AtariLynx			        AtariLynx
C64					          Commodore 64
Coleco				        Colecovision
fbalpha2012		        Final burn alpha 2012 (various consoles)
fbalpha2012_neogo	    Final burn alpha 2012 neogeo
gba					          Gameboy Advance / Gameboy / Gameboy Color
genesis				        Sega genesis / Master system
Mame2003Plus_lg		    Mame2003Plus light gun update
Mame2010			        Mame2010 (built-in)
Mame2010_lg			      Mame2010 light gun update
nes					          Nestopia
nesBI				          Quicknes (built-in)
Odyssey2			        Odyssey 2
snes				          Super Nintendo (snes9x)




