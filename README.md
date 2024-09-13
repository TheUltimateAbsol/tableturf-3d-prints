# [Link to Play Guide](tableturfguideupdatedriptide.pdf)

Inspired by the original print from joeharrison9696 https://www.thingiverse.com/thing:5500927 https://www.reddit.com/r/splatoon/comments/x88b2s/splatoon_3_table_turf_board_paint_tiles_3d_print/

(His print was nice, but the pieces had way too much overhang geometry on the fillet to be mass-printable -- pieces would just melt into goo before being finished -- and the board needed to be sliced to allow magnets)

(Only needed if printing old boards) Link to magnets used to connect pieces https://www.aliexpress.us/item/3256805893053415.html?spm=a2g0o.order_list.order_list_main.131.35241802AD3XiC&gatewayAdapt=glo2usa

Link to BBs to fill pieces: https://www.amazon.com/dp/B000HKKY7M?ref=nb_sb_ss_w_as-reorder_k0_1_3&amp=&crid=1QRWH0OMD10BC&amp=&sprefix=bbs

Filaments
- Yellow https://www.amazon.com/dp/B0991Y913J/ref=twister_B07ZJPCQBN?_encoding=UTF8&psc=1
- Blue https://www.amazon.com/dp/B07PDW6X99/ref=twister_B07ZJPCQBN?_encoding=UTF8&th=1
- Black https://www.amazon.com/dp/B07PGY2JP1/ref=twister_B07ZJPCQBN?_encoding=UTF8&th=1 (but you can use anything really)
- Gold https://www.amazon.com/dp/B087RP8NNZ/ref=twister_B07ZJPCQBN?_encoding=UTF8&th=1
- Light Blue https://www.amazon.com/dp/B0BKFKGQKK/ref=twister_B07ZJPCQBN?_encoding=UTF8&th=1
- Grey https://www.amazon.com/dp/B07PDW8QWJ/ref=twister_B07ZJPCQBN?_encoding=UTF8&th=1

I dumped the files here but I'm too lazy to make an in-depth guide just yet. The real project involved creating a guide piece to mass-dump bbs into 121 pieces all at the same time, but such a guide piece was not printable as a single object and I had to set it up to print 121 open-top open-bottom pieces on top of a base layer guide piece and there's no way for me to export the parts while keeping the correct infil pattern.

If you actually want help 3d printing this, please message me on discord @_bae_

Any filament works for any of these components. I reccomend buying the cheapest PLA or PLA+ from amazon as these can be very material hungry, especially if you print a lot.

# 1x1 Pieces

See [CUSTOM_1x1_SET](CUSTOM_1x1_SET).

This is a 1x1 piece that should connect to form any kind of board. This is the easiest way of printing the board, but is not ideal if you need quick setup and teardown in a tournament environment.

Print with Octogram Spiral as the Top Infill pattern.

Print 9 of the [prod-grid-single-Chamfer.stl](CUSTOM_1x1_SET/prod-grid-single-Chamfer.stl) pieces as a test run and see how nicely they connect. Adjust your pressure advance value on your printer until the fit feels nice enough. (It shouldn't be too loose, but it shouldn't snap together. Ideally you will want to take the board apart)

Once you find the optimum settings, print a bunch of these pieces in black and white. You can also print light blue and gold pieces to indicate where the initial special pieces are placed.

# Printing Pieces

Please use 7% infill in rectilinear pattern. I used 2 floors, 3 ceilings, 1 wall, 0.28mm layer height fastest settings. Please ensure there is slightly less than 9mm of free space between the floor and ceiling solid layers. Add a PAUSE GCODE at the begginning of the first ceiling layer to add in 8 BBs tightly. No Supports.

For the Normal and Special tiles, there are multiple filament colors used in the same print. 
- For the special tiles, import both pieces of the STL at the same print to make a multi-part object in the slicer (this at least works in prusa slicer). Then change the extruder for the second part of the object. The outline piece, piece-B, should be a negative volume. Or just open the 3MF file.
- For the normal tiles, add a layer height modifier after the 5mm mark so that it changes to the second extruder
- For the "Wall" tiles, no additional changes are needed.

You may have to set up your printer to use multi-color or multi-extruder settings to print these correctly. Note, this doesn't require a AMS or multifilament solution, but it will requrie you to change out the filament once or twice per print.

To add BBs into these tiles in bulk, I had to make a custom jig. However such a jig required quite a bit of hacking with the slicer and is hard to explain. DM me, `_bae_` on Discord if you need help or file an issue.

# Printing Boards

## NEW BOARDS

Print the boards from [NEW_MAPS](NEW_MAPS). They are named "prod-grid-LxW-Chamfer.stl", where L and W are the length and width of the edges. 

Keep in mind that the maps require the following pieces

Main Street:
- 2x 9x9s
- 1x 9x8

Square Squared
- 1x 8x8
- 2x 8x7
- 1x 7x7

Thunder Point
- 2x 8x8
- 2x 8x7

If you need a custom size, edit (NEW_MAPS/prod-grid.FCStd). On the spreadsheet you can adjust the Length, Width, and piece tolerance. NOTE: A chamfer is added to the bottom to account for possible elephant's foot. Please delete the chamfer before editing these values, then recreate the chamfer thereafter.

Use PLA, 20% Infill. Top and bottom infill do not matter, no special settings or supports

After the grids are done, you will need to print the interior pieces to the grid (to form the black and white checkerboard)

Test prints of [inside-Body-05.stl](NEW_MAPS/inside-Body-05.stl), [inside-Body-1.stl](NEW_MAPS/inside-Body-1.stl), and [inside-Body-15.stl](NEW_MAPS/inside-Body-15.stl) to check your printer's tolerance. See what piece fits in the grid comfortably.

Once you find which "interior" piece fits, print as many as you can in black and white colors and fill the board. You may need to adjust the seams so that they are "Aligned" or "Random", otherwise you may end up getting a line of seams that poke out into the middle of the piece and make it impossible to fit the inside into the grid. Seams should be aligned to the corners if possible.

Please tweak the values of your "Pressure Advance" if pieces consistently do not fit. Different printers and filaments will flow on corners differently, and you may need to lessen the flow to get an exact square fit.

Interior pieces should use "Octogram Spiral" on the top infill pattern for a nice clean look.

## OLD BOARDS

Print the boards from [OLD_MAPS](OLD_MAPS). They are named "LxW.stl", where L and W are the length and width of the edges. 

You can get away with having 2 walls, 15% infill, 0.28 layer height, no supports. The print is forgiving. Please ensure that the magnets fit before printing many pieces, as I had to dial it in perfectly for my printer.

Once the grids are printed, print "Floor.stl" in the black and white colors. If the pieces do not fit, consider editing  the size of the piece in your slicer.

Use "Coencentric" on bottom infill for a nice sleek look. Place floor pieces into the grid bottom-side up.

To get the maximum amount per print, you may want to redo any bed leveling and bed mesh calibration steps that you did to set up your printer. Otherwise, just print as many as possible and throw away any pieces that don't fit.

# Printing Deckboxes

There are two sizes: Master and regular. "Master" was printed for holding the master set of all 111 cards, which was sold to artists on the Arty Siege project. "Regular" is the size of deckbox large enough to hold 15 sleeved cards + a few extras. This was sold at Riptide.

## LIDS

The QR Code needs to be added on in the slicer (CAD Software hates it). Add [qrcode.svg](DECKBOX/qrcode.svg) as a 1mm negative volume from the surface on the blank area.

There is a 3MF file with this already done.

Print QR code face down. Add a PAUSE (M600) on the layer where the bridging starts over the QR Code and another one after the layer where the "ARTY SIEGE" logo becomes visible. During these pauses, switch from a black filament to a shiny "silk" one, and vice versa.

Use "Archimedean Chords" for top infill. This will get the "shiny" look using silk filament.

You may want to consider uing supports on the "GUIDE & INFO" lettering if using a slow ender 3 printer, as the bridges are long.

## BOXES

It's a normal print; print it however you want.


