# Deepfake Source Identification and Disinformation Dissemination Estimation for Social Networks
This paper focuses on Deepfake Source Identification algorithm that identifies the deepfakes posted on social media particularly twitter.

## Implementation
We have proposed the DeSI(Deepfake Detection and Source Identification) algorithm for source identification of deepfakes on the social media platform-twitter.

This particular algorithm will act as a filtering process where in each step, the tweets which cannot be the sources of deepfake media are discarded. The steps that involve extracting and discarding the tweets that are purely text is called Tweet Filtering.

The next step involves detection of deepfakes based on an input query. In our research work, we have given our input query in two forms- text query and image query. 

The last step involves locating the source tweets of all the retweets and then identifying their source from Source Identification.

 

#### Tweet Filtering 
In order to filter the tweets containing deepfakes, we use deep learning based detection model to create a deepfake detection algorithm. The tweets are extracted through the twitter API based on the two input modalities-text and image.The text query contains hashtags for better filtering of tweets. For images, an additional image query along with text query is provided as input.For both text and images, the deepfake model is used
to filter out the deepfakes from the tweets that have already been screened. The list of all the tweets with the deepfakes is then used for further processing.

#### Twitter API
We have used the python library Tweepy to access the twitter API, which is used ti make requests to twitter platform.The API has a
limit of 50 requests per 15 minutes when using the search
functionality and the relevant tweets are extracted based on
the provided query. 

#### Image Similarity
In order to compute the image similarity between the input image and the extracted deepfake image, LightCNN model is used for feature extraction. Before extracting the features, facial regions are cropped out of the image. For this we have used the MTCNN model.

#### Deepfake Detection
In order to detect deepfake, we have used the XceptionNet deep learning network. This model is trained on Forensics++ dataset which is a large scale deepfake dataset.The dataset has consists of 4 manipulation techniques - Deepfakes, Face2Face, Face swap and Neural textures. 


## Authors

- Aryaman : @Aryaman-Arya

- Sanjam Kaur Bedi : @Sanjam-Bedi
