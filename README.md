# Projet-classifiction-especes-vegetales

Project conducted in collaboration with ONERA

Supervisors:

Rollin Gimenez - rollin.gimenez@onera.fr – Tel.: +33 5 62 25 28 16

Sophie Fabre - sophie.fabre@onera.fr – Tel.: +33 5 62 25 28 59

Lab: ONERA / DOTA (Department of Optics and Associated Techniques) / POS (Optical Properties of Scenes)

## Abstract
The identification of plant species is essential for biodiversity analysis and the monitoring of environmental degradation. Many studies have highlighted the interest of optical remote sensing to map plant species on a given satellite image. Each pixel of the satellite image can be well paired with a plant since each plant has its own spectrum. However, the performance of mapping algorithms is affected by the presence of outliers: some plant species are a minority and should not be labelled. Rejecting these outliers would reduce pixel misclassification. Five classification algorithms (Regularized Logistic Regression with l1 or l2 regularization, Linear Support Vector Machine, Radial Basis Function Support Vector Machine and Random Forest) applied on an image give a vector of probabilities that a given pixel belongs to each tree species. Unfortunately, no efficient post-rejection algorithm has been developed yet in the field of hyperspectral and multispectral images. Our aim is to find relevant rejection methods which can be applied post classification on probability vectors. Boundaries between species and minor species must be rejected. We compare different clustering methods applied on probability vectors: K-means, SVM (Support Vector Machine), DBSCAN (Density-Based Spatial Clustering) and GMM (Gaussian Mixture Models). We improve our results taking the context into account. We define qualitative and quantitative ways to evaluate the rejection performance. K-means and SVM have significant visual results as they reject some specific points of interest on the image. K-means algorithm applied on the dataset Random Forest gives the best result with a True Rejection Rate of 57%. The False Rejection Rate obtained with K-means and SVM is quite low on every dataset, around 0.5-1%, which means that most of the time we do not reject wrongly. Our classification assists the ONERA laboratory (National Office for Aerospace Studies and Research) in their research. For example, to quantify contaminating anthropogenic impacts in soils, the vegetation condition is analysed and it is necessary to know the species corresponding to every pixel. Further research can use our results to compare the efficiency of a rejection option performed during classification with a rejection option performed post-classification.

## Installation
```
install rasterio on linux
$ sudo add-apt-repository ppa:ubuntugis/ppa
$ sudo apt-get update
$ sudo apt-get install python-numpy gdal-bin libgdal-dev
$ pip install rasterio

on the machine terminal of INSA 
pip install rasterio
```

## Team notes
- projet_data_extraction: Contains everything related to data extraction and dictionary construction.
- tentative_gmm: Same as above, but also includes an attempt at implementing a GMM (though it doesn’t work, at least not on my computer).
- clustering2.py: Performs clustering on the small dataset 
- clustering_small_data.py: Same code as clustering2.py, but refactored into reusable functions for use in other algorithms.
- clustering_kmeans_v2.py: Same code as clustering2.py, but without the cumbersome dictionary manipulation.

------------------------------------------------------------------------------------------------------------------------------------------ 
