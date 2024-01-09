# Image quality characterization

### The goal of this project is to develop diagnostic tools in order to validate the upcoming LSST observations for strong lensing source detection.


This by identifying metrics that allow us to define a function to estimate the probability of SL sources detection. The function should be in terms of deepness (number of coadded images/exposure time), location, band, PSF size, among others. 

We started exploring the PSF size and ellipticity. The current default method for PSF construction within the LSST pipeline uses a modified version of [PSFEx](https://psfex.readthedocs.io/en/latest/). The algorithm for point source selection uses k-means clustering classification instead of a size-magnitude region. 

It is reserved 20% of the selected PSF candidates in order to test the model. Postage stamps (41 $\times$ 41pix) are extracted and fed to the PSF constructor. The fitting of the PSF model is done to each CCD completely independently, using a second-order polynomial to interpolate between stars.

The moments of the intensity, such as the mean (first moment), variance (second moment), skewness (third moment), and kurtosis (fourth moment) give us information of the size, shape, and orientation of the light distribution. In particular, the determinant of the covariance matrix of the second moment provides information about the shape and orientation of the light distribution, while the trace of the covariance matrix is a measure of the average size of the light distribution. Along the document and in the notebooks we use as PSF size the trace radius of the covariance matrix of the second moment of the intensity distribution. 

* PSF exploration: [PSF_exploration.ipynb](./PSF_exploration.ipynb) <br>
Different ways to extract the PSF, residual distribution, comparison between model and actual measurements. Spatial and filter variation in visits and coadds. 

* Visit selection, custom coadd construction and characterization: [visits_selection_and_coadd.ipynb](./visits_selection_and_coadd.ipynb) <br>
For a given sky position (RA, DEC), select the best (user defined) visits and create a custom coadd. The best visits can be chosen according PSF size mean and standard deviation, airmass, seeing, wind velocity.

