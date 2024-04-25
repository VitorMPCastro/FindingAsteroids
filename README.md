# Finding Asteroids

Google Docs: https://docs.google.com/document/d/10D2yJlmfxxFpBIk1ulIUN3U_xpiv_9QuN15dcH_HwI4/edit?usp=sharing
Planejamento: https://docs.google.com/document/d/1Ma99utzA0t9uS3yH5-ZCBPoU08MLjO4f_agvJElcsTE/edit

Stack Exchange useful info:

There are two main datasets available from the PanSTARRS survey which are available from the archive at MAST/STScI. These are the Object Catalog, a (large) list of parameters such as position, brightness, shape etc (full list of catalog fields) and the Image Cutouts service which, well, cuts out sections of the images. (The survey went over the same patch of sky several times in 5 filters so there are deeper stacks available)

If you are looking for moving objects then you will need to use the "warp" single epoch images as a moving object would be averaged away in the stack (unless it was done on the object's motion). You will also need a source of positions in order to cutout the suitable postage stamps in the right places as the PanSTARRS archive doesn't support querying by moving objects or orbital elements. You would need to use something like the Minor Planet Center's Ephemeris Service or JPL's HORIZONS service to generate these positions (use 'F51' as the Observatory Code/Observers Location as this is the MPC site code for PanSTARRS1). Once you have a source of positions, you will probably want to investigate querying the Image Cutout Service via script/code; the Image Cutout Service documentation has instructions and a Python Jupyter notebook showing how to do this.

I should also caution you that one of the goals of the PanSTARRS survey, which my institution was a partner in, was to find moving objects. A lot of effort was put into the Moving Object Processing System (MOPS; paper, which I'm on, available (for free) here at IOPscience) and PanSTARRS was one of the two major sources of new Near Earth Objects (NEOs), see purpley bars in this plot at the Center for NEO Studies. I'm not saying there isn't new moving objects in there, we go back and search through the PanSTARRS data for precoveries of newly discovered NEOs that the automatic software missed on a roughly monthly basis, but bear this in mind before launching into a big project.

From: https://astronomy.stackexchange.com/questions/29506/how-does-one-use-the-pan-starrs-data
In Feb 16 - 2024

PanSTARRS website:

2024.02.02: Search for moving targets in PS1 images and catalogs
A new Python Jupyter notebook has been written to search PS1 images and catalogs that have observations of a moving solar system target.  In about one minute, the notebook finds all PS1 observations that included a particular target and extracts cutout images and catalog measurements.  See the How to search for moving targets in PS1 images and catalogs page for details. [link](https://outerspace.stsci.edu/display/PANSTARRS/How+to+search+for+moving+targets+in+PS1+images+and+catalogs)

https://outerspace.stsci.edu/display/PANSTARRS/PS1+News#PS1News-2024.02.02:SearchformovingtargetsinPS1imagesandcatalogs

Real-Bogus:

https://arxiv.org/abs/1907.11259

https://arxiv.org/abs/2102.09892

https://arxiv.org/abs/2206.12478

Deep Learning and applying ML to the dataset:
https://www.researchgate.net/publication/274321101_Machine_learning_for_transient_discovery_in_Pan-STARRS1_difference_imaging

