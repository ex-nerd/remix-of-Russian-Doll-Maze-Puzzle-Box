# Russian Doll Maze Puzzle Box Generator

Generator for [Thingiverse Thing 2980535](https://www.thingiverse.com/thing:2980535)

### system requirements

- OS
  - Windows 7 (64 bit) or greater
  - MacOS (tested with python3 installed via homebrew)
  - Linux may work but untested
- `python 3.5` or greater with:
  - numpy
  - pillow
- `openscad 2015.03-2` or later
- stl repair tool (I used netfab)

## instructions

install the above software before first use and edit the path in the python code to match your setup.
make sure to install the python libs!

1. If OpenSCAD is in a nonstandard location, adjust path at top of `main.py` (folders for output and preview created when run)
2. (optional) adjust the `bs` (lid sides) value in `make shells.scad` for a new look if you like
3. (optional) adjust values in `opt.ini` as you see fit
4. (optional) make a backup of `opt.ini` so you can reuse these values in the future. (optional)
5. open a python shell and run `main.py`. (you may be able to just double click it)
   - you will be prompted whether to use multi-threadding (if available) then nub count, a difficulty level and a shift mode value.
   - shifting is where each row of the maze is shifted and wrapped for the illusion of a bigger maze.
   - for shift mode 3, also input how much. it will be constrained by modulus, so large nums will not break it.
   - stl files go in the `stl_files` folder and previews in the `prev` folder.
6. the stl files may need repair. use a repair tool.
   - it is recomended to view all stl files to check that they will work.
7. print a 2-part test print at 0.2mm layers. if they fit, print the rest.

### Tips

- read `opt.ini`, it has important info about the options.
- put all these files in a project folder.
- If using Windows, use the [multi-thread openscad version](http://files.openscad.org/snapshots/OpenSCAD-2018.05.30-x86-64_multithread-Installer.exe).
- preview the mazes in the `prev` folder. if using transition point, the one ending with "a" is of the same shell as without the "a".

### Notes

- be patient: it may take a while to run the openscad scripts.
- `m=0.3` (`tolerance` in `opt.ini`)g for 0.4mm nozzle worked well for me with ABS. PLA or PETG recomended as some shells can be large, nubs rub off easier with "soft" materials, and cheating can be possible with "flexible" materials.
- editing during the run may not be possible.
- openscad scripts run via shell in the python code. this speeds the process of stl export as this limits having to switch between apps.
- to make another or to adjust values, you will need to restart from step 2 as some parts may no longer fit.