Follow this link to download the data: https://drive.google.com/file/d/1BGolQzYYaU1oSx0CdFwntCOPQ8nyqaPE/view?usp=sharing
- Split into train/test/valid data, where each file name corresponds to a unique index
- "data.csv" contains more metadata for each index, such as latitude, longitude, country, and 'geocell'

I divided the world up into 275 "geocells", where a geocell is a lat/long-bounded box containing approximately 300 images.

Set counts:
- train: 77654 images
- valid: 9707 images
- test: 9707 images

There are a few tasks you can use this dataset for:
- Classifying the country
- Classifying the geocell
- Predicting the lat/lng location. "geocell_centers.csv" is useful for this task: it contains the median lat and lng for the images in each geocell
    
Lastly, I included code I used to create and visualize the dataset. They each read and modify "data.csv". To re-create the datasets, you would run them in this order:
1. scrape_gmaps.ipynb - used for scraping the google maps streetview API
2. make_geocells.ipynb - used to divide the world up into geocells. Also has tools for visualizing the distribution of cells and images on the world map
3. make_train_valid_test.ipynb - divide the scraped data into train/valid/test datasets. I removed all data for countries we had fewere than 50 images, and for geocells where we have fewer than 50 images. This allows us to have enough data to train our model for each class
