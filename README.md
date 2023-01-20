# Image quality characterization

### The goal of this project is to find out the optimal configuration for strong lensing detection.

This by identifying metrics that allow us to define a function to estimate the probability of SL sources detection. The function should be in terms of deepness (number of coadded images/exposure time), location, band, PSF size, among others. 

We started exploring the PSF size and ellipticity. The current default method for PSF construction within the LSST pipeline uses a modified version of [PSFEx](https://psfex.readthedocs.io/en/latest/). The algorithm for point source selection uses k-means clustering classification instead of a size-magnitude region. 

It is reserved 20% of the selected PSF candidates in order to test the model. Postage stamps (41 $\times$ 41pix) are extracted and fed to the PSF constructor. The fitting of the PSF model is done to each CCD completely independently, using a second-order polynomial to interpolate between stars.

* PSF size dependency on band:  [PSFsize_band.ipynb](/home/alrakomala/notebooks/kaam/myGitRepo/)

* PSF diagnostics. Luminosity residuals, spatial distribution and residual histograms ($\Delta = PSFmodel - star$) for PSF size and ellipticity:  [ellipticity_fwhm_DP02.ipynb](/home/alrakomala/notebooks/kaam/myGitRepo/)

* Construction of custom coadds:  [custom_coadd_airmassSelection.ipynb](/home/alrakomala/notebooks/kaam/myGitRepo/)

* PSF size grids for calexps and coadds, same region in different filters: [PSFsize_filter_comparison.ipynb](/home/alrakomala/notebooks/kaam/myGitRepo/)
