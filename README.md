# Image classification on Pascal VOC

This university project focuses on "Object Recognition" using the Pascal VOC 2012 dataset, which is rich in images representing various objects in different contexts. The goal is to develop a classification system to determine the presence of objects in the test images by assigning them to one of twenty classes in the dataset. A Convolutional Neural Network (CNN)-based approach is adopted for visual feature extraction. Transfer learning is employed to exploit pre-trained networks on larger datasets. The pyramid sliding window algorithm with the InceptionV3 model is used to handle the classification of multiple objects in images by examining different portions and overlaps.

## Table of contents

- [Image classification on Pascal VOC](#image-classification-on-pascal-voc)
  - [Table of contents](#table-of-contents)
  - [DATASETS](#datasets)
  - [SETUP](#setup)
  - [PRE-PROCESSING OF DATA](#pre-processing-of-data)
  - [CREATING THE BACKGROUND CLASS](#creating-the-background-class)
  - [CUTTING AND SAVING BOUNDING BOXES FROM IMAGES](#cutting-and-saving-bounding-boxes-from-images)
  - [CREATING TEST SET AND TRAIN SET](#creating-test-set-and-train-set)
  - [DATA AUGMENTATION](#data-augmentation)
  - [TRAINING](#training)
  - [TESTING](#testing)
  - [Contributors](#contributors)
  - [License](#license)

## DATASETS

- [Pascal VOC 2012](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/VOCtrainval_11-May-2012.tar)

## SETUP

Initialize the varaible `main_path` with the path to your workspace.

Initialize the variables with the paths associated with the annotations and images in the dataset that were downloaded from the official Pascal Voc site.

## PRE-PROCESSING OF DATA

Run the cells for the pre-processing part that will allow you to create a csv file called `annotFiles.csv` with the coordinates of the objects associated with the images and a `csv` called `filesXML.csv` with all the `xml` file names.

## CREATING THE BACKGROUND CLASS

Run the cells for creating the background class images. In this step, a folder called `background_img` will be created with the background-classified images that will be used for training. A csv file called `annotBackground.csv` will also be created with all the file names created and classified with background.

## CUTTING AND SAVING BOUNDING BOXES FROM IMAGES

Run cells for cutting instances in the images. This creates a folder called **CuttedBoundingBoxImages** containing all the images with only the individual instances annotated to the images in the dataset. A csv file called `BoundingBoxes.csv` is also created with all the files created.

## CREATING TEST SET AND TRAIN SET

Run the cells to separate the dataset and create the csv for the train set and test set. At this stage two files will be created: `dataset_testing.csv` and `boundingBoxes_without_testing.csv`. After that from the file `boundingBoxes_without_testing.csv` class balancing is performed and an additional csv called `dataset_training.csv` containing the file names of the balanced images is created. The latter will then be used for the training phase.

## DATA AUGMENTATION

Run cells to create a folder called **AugmentedImages** containing the augmented images. A csv called `augmImg.csv` is also created with the file names of the newly created images.

## TRAINING

Run the **loading data** cells to load and run the training with the unaugmented dataset, instead run the **loading data with data augmentation** section to load and run the training with the augmented dataset.

Next, run the **loading network** section to perform the training that will save the towed model in a `.h5` file.

## TESTING

Run the cells in the sub-sections to perform the various tests.

1. The first subsection is devoted to accuracy on the test data which will output a confusion matrix.
2. The second part is devoted to metrics such as precision, recall and f1.
3. The third part performs the true prediction on the whole image using the Sliding Window. It is necessary to go and specify the path of the image on which you want to perform the prediction.

## Contributors

- [Fabio Marini](https://github.com/fabbio00)
- [Riccardo Andena](https://github.com/anduz15)

## License

This project is licensed under the [MIT License](LICENSE) - see the [LICENSE](LICENSE) file for details.
