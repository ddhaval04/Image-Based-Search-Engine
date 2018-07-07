# Image Based Search Engine

![Search](https://github.com/ddhaval04/Image-Based-Search-Engine/raw/master/images/search-engine.jpg)

This repository consists of my implementation of an image-based search engine.

## Problem

Given an image, identify all the images that are similar.

## Why this problem is important?

The solution of this problem can be implemented in various verticals of a company. For example allowing the users to efficiently search through their photo libraries to the selfie they took at the beach! Finding out similar t-shirt on the Amazon fashion and many more! Sounds cool, isn't it?

There are already applications in the market implementing something similar, like, Google Reverse Image Search & Google Image Search.

Now this problem sounds trivial at first, but imagine the amount of data being handled by Pinterest, Google, Amazon etc.!! It is huge and any traditional algorithm created needs to be scalable and fast. Hence, if we are planning to build a image similarity search engine, it needs to adapt and scale well to the data evolution.


## Overview

I am using a pre-trained VGG16 network to create vector representations of the input images. To search a particular input image we simply find the vectors close to our input vector. The way I am calculating the similarity is based on the cosine distance between our input embedding and the embeddings of the other images. This approach is fast (a forward pass and an efficient similarity search (check [Annoy](https://github.com/spotify/annoy))) and is also scalable.

This is something I stumbled upon when checking out the work done by Spotify int the deep-learning space.

## Data:

The notebook uses two different data sources:
#### - Sunglasses dataset:
I made us of the script provided by [Hardikvasa](https://github.com/hardikvasa/google-images-download) to download 9 different types of sunglasses.
#### - Subset of Dog-breed-identification dataset on Kaggle.

## Dependencies (pip install)

```
numpy
pandas
matplotlib
annoy
keras
```
## Results

### Input Image (Image to search):

<p align="left">
  <img width="460" height="300" src="https://github.com/ddhaval04/Image-Based-Search-Engine/raw/master/images/dog-input.png">
</p>

### Similar Images:

<p align="left">
  <img width="460" height="300" src="https://github.com/ddhaval04/Image-Based-Search-Engine/raw/master/images/dog-results.png">
</p>

### Input Image (Image to search):

<p align="left">
  <img width="460" height="300" src="https://github.com/ddhaval04/Image-Based-Search-Engine/raw/master/images/sunglasses-input.png">
</p>

### Similar Images:

<p align="left">
  <img width="460" height="300" src="https://github.com/ddhaval04/Image-Based-Search-Engine/raw/master/images/sunglasses-results.png">
</p>