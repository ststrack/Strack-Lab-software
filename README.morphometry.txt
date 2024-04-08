/* Morphometry in thresholded images for automatic mitochondria or other particle morphology analysis in ImageJ
- copyleft Stefan Strack, April 30, 2006

Macros:

Help & Options [F1] - displays help screen and configuration menu
Save Results & Selections [F2] - saves Output.txt and Selections.txt in current directory, appending -1,2 ..  if files already exist
Open Next [F3] - closes current image and opens next
Enlarge Selection [F4] -
Shrink Selection [Space][F4] - (by 20 pixels)
RGB <-> Stack [F5] - toggles between RGB and 3-slice stack. If there is no user selection in RGB mode, macro tries to outline mitochondria with cell perimeter.
(e.g. mitochondria in red, diffuse cell label in green (e.g. GFP-Drp1)). The macro
converts the "Autoselect" channel to a binary mask and outlines with selection, then transfers selection
to "Morphometry" channel
Edit Stack [F6] - rearrange (delete, extract, move) slices in image stack
Morphometry [F7] - performs morphometry on selected slice or channel and optional 3-way colocalization
Morphometry-Next [F8] - F7, then F3
Measure Entire Stack [F9] - applies selection to entire stack

Modifiers:
[Alt][F2] - starts Excel to view saved results/selections (Windows only)
Batch Process Selections.txt - applies selections in "Selections.txt" to specified images in current directory (useful for testing deconvolution options)
[Alt] [F3]/F5] - skip autoselection
[Alt][F7]/F8] - accumulate image result
[Alt][F9] - print accumulated results of entire stack
[Space][F2] - save with overwrite
[Space][F5] - dump accumulator (doesn't update selections list; use only if you forgot to output accumulated image series with [F7]/[F8])
[Space][F7]/[F8]/[F9] - prepend comment (specified with [F1]) to output line

Version history:
v4.63:				 undid several BatchMode kludges that corrected bugs in prior ImageJ Change Log:
v4.7 [Oct 26, 2017]: replaced defunct broken openNext() with built-in run("Open Next")
v4.8 [Feb 10, 2018]: fixed openNext, now works from split channel image
v4.9 [April 18, 2019]: consistent use of batchmode (faster)
v4.93 [Nov 4, 2021]: Added "Select None" before Auto Threshold
v5.0 [Feb 6, 2022]: added options for LLPS, BMC and other aggregate analyses
 */
