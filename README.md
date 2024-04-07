This code was used to analyze motion tracking data taken from video recorded from a Thorlabs Portable Optical Tweezer setup examining the brownian motion of 1 and 3 micron polystyrene beads in deionized water at 0.04% CV. Motion tracking was performed using blender 2.8 (GNU GNL), which can be downloaded at https://ftp.nluug.nl/pub/graphics/blender//release/Blender2.80/.
Motion tracking data was exported as a csv file using a python add-on that is available from https://github.com/Amudtogal/blenderMotionExport. In my code, for each bead the mean squared displacement and time mean value is calculated, and then an average displacement per unit time is calculated for all beads of the same size by taking an average of all their time mean values. The average displacement for 1 and 3 micron beads are then plotted against time and a linear regression used to fit the curve through the origin. The slope of the curve can be used to calculate the effective viscosity for each solution.

Some notes to make on this analysis:
a) The video was shot at 1280 x 1024 resolution at 15 FPS. 
b) Frame to seconds conversion in the code is based on these video parameters.
c) Pixel to micrometre conversion in the code is based on the number of pixels across a 3 micron bead (11.66 pixels/micrometre) and is subject to uncertainties due to the differential z-positions of individual beads within the 20 micrometre deep well that the sample was placed in, and the coefficient of variation (CV) of 5% of the bead size from the manufacturer. These uncertainties have not been factored into the preliminary analysis yet.
d) Code will be added at a later date to determine the maximum holding force of the optical tweezers from the best instance of bead trapping I could accomplish in my experiment. 
