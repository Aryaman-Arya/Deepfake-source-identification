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
We have used the python library Tweepy to access the twitter API, which is used to make requests to twitter platform.When using the search capability, the API has a cap of 50 calls per 15 minutes, and the pertinent tweets are extracted depending on the specified query. There is no assurance that we will receive a comprehensive list of all tweets matching the given query.
These restrictions do not apply to the Twitter Premium API, though. Twitter is the social media site we prefer over others since it is a leading platform for the dissemination of news and both politicians and celebrities are frequent users.

#### Image Similarity
In order to compute the image similarity between the input image and the extracted deepfake image, LightCNN model is used for feature extraction. Before extracting the features, facial regions are cropped out of the image. For this we have used the MTCNN model. MTCNN or Multi-Task Cascaded Convolutional Neural Networks is a neural network which detects faces and facial landmarks on images. It consists of 3 neural networks connected in a cascade. We pick 10 frames from the video and use them to compute the average similarity scores between the image and the video. For matching, a similarity criterion of 0.4 is employed.

#### Deepfake Detection
At last, in order to detect deepfake, we have used the XceptionNet deep learning network. This model is trained on Forensics++ dataset which is a large scale deepfake dataset.The dataset has consists of 4 manipulation techniques - Deepfakes, Face2Face, Face swap and Neural textures. Xception, which means for "extreme inception," pushes the fundamental ideas of Inception to the limit. In Inception, the initial input was compressed using 1x1 convolutions, and from each of those input spaces, we utilised various types of filters on each depth space. Just the opposite occurs with Xception. Instead, it applies the filters to each depth map individually before using 1X1 convolution to compress the input space all at once. Following the extraction of 10 frames from each video for training, MTCNN face detection alignment is used. The Adam optimizer trains the model over 30 iterations using the Binary Cross-Entropy loss function.

## Authors

- Aryaman : @Aryaman-Arya

- Sanjam Kaur Bedi : @Sanjam-Bedi
