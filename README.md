Code from my GeoGuessrBot project. The goal is to predict the country and location of any given Street View image.
- Play with the live demo [here](http://geoguessrbot.com/)
- To learn more about how it works, check out my [blog post](https://vdefont.github.io/2021/06/20/geoguessr.html)

DATA

Follow this link to download the data: https://drive.google.com/file/d/1BGolQzYYaU1oSx0CdFwntCOPQ8nyqaPE/view?usp=sharing
- Split into train/test/valid data, where each file name corresponds to a unique index
- The data/ directory contains more metadata. For example, "data.csv" contains more metadata for each index, such as latitude, longitude, country, and 'geocell'

Set counts:
- train: 77654 images
- valid: 9707 images
- test: 9707 images

The data/ directory also contains code I used to make the data:
- scrape_gmaps has code to scrape Street View images from the Google Maps API
- make_geocells has code to divide the world up into 275 geocells.

There are a few tasks you can use this dataset for:
- Classifying the country
- Classifying the geocell
- Predicting the lat/lng location. "data/geocell_centers.csv" is useful for this task: it contains the median lat and lng for the images in each geocell

MODELS

I trained models to:
- Predict the country
- Predict the US state
- Predict the geocell

The code used to train three models are contained in the models/ directory. If you'd like the weights for a pretrained model, feel free to send me an email (my email address is located on my blog).

Additionally, I trained a KNN that uses the outputs of these three models to predict the precise location of an image, as described in my [blog post](https://vdefont.github.io/2021/06/20/geoguessr.html). This code is in "knn.ipynb"

FIGURES

I also included code used to generate the figures in my blog post. These files are under the figures/ directory.

A NOTE ON NOTEBOOKS

I learned many lessons over the course of this project. One of them is that jupyter notebooks are not good for large-scale projects. My future projects will mostly consist of ".py" files, but it was too late to change course on this one. I apologize that the code here may be a bit hard to use.
