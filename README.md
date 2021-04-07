![corn_header2](data/images/corn_header2.png)

# Maize Well 

### Corn Leaf Disease Classification with Convolutional Neural Networks
#### Authors: Diane Tunnicliffe & Dana Rausch 

## Overview 

Corn is a highly significant crop throughout the planet and is at the center of agricultural production. Corn has to survive many disease threats throughout the season, such as Gray Leaf Spot, Northern Corn Leaf Blight, and Common Rust. As explained by Bayer Crop Science, "Managing these diseases early is essential to keeping your corn crop healthy and protecting your yields. Knowing what these diseases look like is the first step in prevention and protection." In an effort to solve this problem and assist farmers and everyday gardeners to ensure a healthy crop, Maize Well uses an image classification model to help predict and identify these three prevalent leaf diseases based on images of both healthy and diseased corn plant leaves.


## Business Problem 

Corn is an integral part of the agricultural ecosystem and both the American and global economy. According to the United States Grain Council, the US is the largest corn producer in the world, with 96,000,000 acres of land reserved for corn production. "In the 2018/2019 crop marketing year, (Sept. 1- Aug. 31) the United States grew more than 14.42 billion bushels (366 million metric tons) of corn. Roughly 14.3 percent of production was exported to more than 73 different countries."
Considering how much of an impact corn has on agriculture and economy, it is imperative that farmers be able to avoid the occurrence of leaf diseases affecting their crops. With acres of corn to care for, it can be difficult and time-consuming to identify diseased plants. Since diseased corn plants are not able to be harvested, continuing to water them and care for them is a waste of resources and time.
By developing a model to analyze and evaluate the health of corn plant leaves, Maize Well applies technology to the realm of nature, thereby making the process of identifying corn leaf diseases faster and easier for farmers.


## Data Understanding 

Our data was sourced from https://www.kaggle.com/smaranjitghose/corn-or-maize-leaf-disease-dataset .
This is a dataset for classification of corn/maize plant leaf diseases.

The images are in 4 folders, classified as follows: 
0. Common Rust - 1306 images
1. Gray Leaf Spot - 574 images
2. Blight - 1146 images
3. Healthy - 1162 images

#### Common Rust

"Common rust is caused by the fungus Puccinia sorghi and occurs every growing season. It is seldom a concern in hybrid corn. Rust pustules usually first appear in late June. Early symptoms of common rust are chlorotic flecks on the leaf surface. ... The lesions sometimes form a band across the leaf and entire leaves will die if severely infected. ... Husks, leaf sheaths, and stalks also may be infected." [source](https://cropprotectionnetwork.org/)

![rust](data/images/rust.png)

#### Gray Leaf Spot

"Gray leaf spot, caused by the fungus Cercospora zeae-maydis, occurs virtually every growing season. If conditions favor disease development, economic losses can occur. Symptoms first appear on lower leaves about two to three weeks before tasseling. The leaf lesions are long (up to 2 inches), narrow, rectangular, and light tan colored. Later, the lesions can turn gray. They are usually delimited by leaf veins but can join together and kill entire leaves." [source](https://cropprotectionnetwork.org/)

![gray](data/images/rust.png)

#### Blight

"Northern corn leaf blight (NCLB) is caused by the fungus Setosphaeria turcica. Symptoms usually appear first on the lower leaves. Leaf lesions are long (1 to 6 inches) and elliptical, gray-green at first but then turn pale gray or tan. Under moist conditions, dark gray spores are produced, usually on the lower leaf surface, which give lesions a "dirty" gray appearance. Entire leaves on severely blighted plants can die, so individual lesions are not visible." [source](https://cropprotectionnetwork.org/)

![blight](data/images/rust.png)

#### Healthy 

Healthy corn leaves have no disease or cause for concern.

![healthy](data/images/heathly.png)

Each class has healthy representation as the dataset is relatively balanced. As illustrated in the visual below, Gray Leaf Spot has slightly fewer images than the other three classes, but is still adequately represented and causes no concern. 

![representation](data/images/representation.png) 


## Methodology & Results

Maize Well is built using a convolutional neural network for image classification. Below we will walk through several model iterations and discuss overfitting, a common problem when dealing with neural networks. 

Two convolutional layers were used for the first model with a softmax output to account for all four classes. As expected, this model resulted in a promising training accuracy score but a poor validation score - signaling overfitting. 

![pre_augmentation](data/images/pre_augmentation.png)

Next, data augmentation was applied to the images. Data augmentation is a common method to combat overfitting. This process takes an image and changes it in various ways so that the model learns to differentiate to images in many different formats and appearances. Below we see how images can be augmented by changing the orientation or brightness. 

![aug1](data/images/aug1.png) ![aug2](data/images/aug2.png)

Although data augmentation solved for a good amount of the model's overfitting, adding a dropout layer was the final step in creating a dependable model that would perform well on new, unseen data. 

![final_model](data/images/final_model.png)

## Conclusion 

Although overfitting was a major issue during this project, after applying data augmentation and dropout layers, the final model performed well on both training and validation sets with low loss. Training accuracy landed around 90% while validation accuracy settles around 85%. This means that Maize Well can be expected to correctly class new images with an 85% accuracy. 

## Recommendation

Maize Well can be trusted to properly class common maize leaf diseases. We recommend to use this product as early as possible to catch disease before it spreads to the rest of the crop. 

Our recommendation: **use Maize Well!**

## Future Work

Maize Well's model is currently trained to identify three common leaf diseases along with healthy leaves. Going forward, we would like to expand the database to include other common diseases. Some examples include Eyespot, Charcoal Rot, and Common Smut. 
Adding location data to the model would be helpful for users as some diseases are more common in certain climates. Including region information would provide the user with more information on how to prevent and spot disease for their particular crop. 

## Want to Know More? 

Check out our [Jupyter notebooks](Integrated_CornDisease_CNN) and [presentation](Presentation) here! 

For additional questions, reach out to **[Diane Tunnicliffe](diane.j.tunnicliffe@gmail.com)** and **[Dana Rausch](dana.rausch5@gmail.com).**