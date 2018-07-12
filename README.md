# Content-based-Video-Recommendation
Video Relevance Prediction ACM Mutimedia Grand Challenge 2018

**Can't really discuss about the methods till end of July as paper is in review but basic approaches are discussed.**

   As a part of ACM Multiledia 2018 Grand Challenge, we participated in this challenge which is conducted by HULU organization.Due to legal issues, we don't have access to the videos of TV Shows and Movies. So, based on the features of InceptionV3 network and Convolution 3D network, we predicted videos based on the feature analysis.

   Video relevance prediction is one of the most important tasks for online streaming service. Given the relevance of videos
and viewer feedbacks, the system can provide personalized recommendations, which will help the user discover more
content of interest. In most online service, the computation of video relevance table is based on users’ implicit feedback,
e.g. watch and search history. However, this kind of method performs poorly for “cold-start” problems - when a new video
is added to the library, the recommendation system needs to bootstrap the video relevance score with very little user
behavior known.

   Several approaches have been done using collabartive filtering methods. However,this kind of method performs poorly on “cold-start” problems - when a new video is added to the library, the recommendation system needs to bootstrap the video relevance score with very little user behavior known.     

## Dataset Overview


   The dataset contains feature vectors from Inception-pool3 layer and Convolutional 3D-pool5 layer. Inception Network was used to generate **frame-level** features and C3D model was used to generate **video-level features**. 
   * For frame-level features, video is decoded at 1 fps and then feed the decoded frames into the InceptionV3 networks trained on ImageNet dataset, and fetch the ReLU activation of the last hidden layer, named pool 3 reshape with 2048 dimensions. 
   * For video-level features, state-of-the-art architecture C3D model was employed, resorting to its most popular implementation from Facebook.

**Track 1** - TV shows: For TV-shows, there were nearly 7,000 TV-show video trailers with pre-extracted features. The whole set is divided into 3 subsets: training set (3,000 shows), validation set (864 shows), and testing set (3,000 shows).
**Track 2** - Movies: For movies, we provide over 10,000 movie video trailers. The whole set is divided into 3 subsets:
training set (4,500 movies), validation set (1188 movies), and testing set (4,500 movies).

*An overview of the dataset is uploaded. The whole dataset is too large.* 


## Methods

## 1) Regression using Deep Learning
We devised our own model in which the Inception-pool3 features and Convolution-pool5 features were input vector and then Tv Shows/Movies are predicted. We tested our model with various losses such as cosine proximity loss, poisson loss and mean squared error loss.


## Evaluation Metrics
For the performance, evaluation hit@30 and recall@100 were taken into evaluation:

1) Hit@k
2) Recall@k
