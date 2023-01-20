# Image quality characterization

### The goal of this project is to find out the optimal configuration for strong lensing detection.

This by identifying metrics that allow us to define a function to estimate the probability of SL sources detection. The function should be in terms of deepness (number of coadded images/exposure time), location, band, PSF size, among others. 


We started exploring the PSF size and ellipticity. The current default method for PSF construction within the LSST pipeline uses a modified version of [PSFEx]([https://www.example.com](https://psfex.readthedocs.io/en/latest/)). The algorithm for point source selection uses k-means clustering classification. 


[PSFEx](https://psfex.readthedocs.io/en/latest/)
It is reserved 20% of the selected point sources. Postage stamps (41x41pix) are extracted and fed to PSFEx. 
