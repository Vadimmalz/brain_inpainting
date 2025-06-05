# brain_inpainting

Assessment description
For our first assessment, our goal is to solve an imputation problem: we will create a neural network architecture that learns how to recover missing portions of an image.

This is an important problem in magnetic resonance imaging (MRI), where patient scans are often limited to a few areas to avoid lengthy scanning times.

In particular, we are going to focus on images of human heads. We have managed to gain access to one hundred images of patient's heads but, unfortunately, these images have a significant portion of missing information. Your goal during the assessment is to design a neural network that can recover these missing portions.

We do not have access to the labels for the images we want to recover, so we will have to be a bit creative to obtain a workable dataset on which to train our neural network.

Fortunately for us, we have access to a generative model that has been trained to produce realistic-looking MRI images of patient's heads. Using this model, you will create an appropriate dataset to train your architecture. We have provided you with the basic setup code to start using this generative model in Question 1.

The corrupted images that we want to recover are contained in the numpy file test_set.npy of this repository. The file contains 100 patient images with a size of 64x64 pixels.

The architecture that you design in this assessment should use the artificially-generated dataset in order to recover the missing information in the images contained in test_set.npy.

Assessment format
A notebook file called Assessment.ipynb is provided for you to solve and turn in the assessment. All answers to the assessment should be contained within the Assessment.ipynb notebook and the name of the notebook should NOT be changed.

Inside the Assessment.ipynb file, you will find three questions. Please, do not change the structure the notebook, but you are free to add new code and text cells as required to your answers. Read the text for each question and follow the instructions carefully. Answers that do not follow this structure will not be marked.

Please, make sure to execute all your cells and save the result of the execution. We will only mark cells that have been executed and will not execute any cells ourselves.

Question 1 (25%)
Using the provided image-generation network, create a dataset of brain images that will later be used to train your chosen architecture.

Given that you will likely want to use this dataset multiple times during training, we recommend that you save the generated images to an appropriate folder in your GDrive.

Once you have generated your dataset, load and display ten of your generated images in the notebook.

We have also provided you with some corrupted images in the file test_set.npy of this repository. You should also load and display ten of these corrupted images here.

Inside the notebook, we have provided template code, including some required downloads and installations, so that you can easily use the trained generative model. Sample generation in this model is done using the function generate, and is controlled by some input arguments. It is your job to figure out a sensible set of parameters that will produce images that are useful for the requirements of your task.

Question 2 (25%)
Using the data generated in Question 1, create a PyTorch TensorDataset and a DataLoader for the training set.

Using the provided corrupted images inside test_set.npy, create another TensorDataset and a DataLoader for the test set.

The training dataset should provide batches of brain images generated in Question 1 and should corrupt these images appropriately so that they resemble images in the test set. The dataset should also pair each image with its corresponding un-corrupted image as a label.

The test dataset should provide the corrupted images provided, for which no labels are available.

Display in the notebook ten images of your training dataset and ten images of your test dataset, and their corresponding labels when available.

Question 3 (50%)
Using the dataset created in Question 2, design and train an architecture to recover the missing image lines of the provided test dataset.

Once you have trained your architecture, display here ten images of the test set with the recovered lines filled in.

Additionally, save the test data with the missing values filled in into a numpy file called test_set_nogaps.npy. These images should be in the same order as those in the test_set.npy file and should have the same pixel size of 64x64. Any images not contained in the test_set_nogaps.npy file or incorrectly ordered will not be marked.

You have freedom to choose an architecture that you consider appropriate to solve this problem. However, you will need to train your chosen architecture as part of the assessment: pre-trained networks are not allowed.

You will be assessed by the quality of your predictions of the missing data values and additional marks will be given for originality in your network design choices. You should include, as part of your answer, a paragraph explaining the architecture you have chosen and any additional design choices and hyperparameters that have been important to build your solution.

This is an open-book assessment and you are encouraged to use resources online, including tools like chatGPT. However, make sure to always mention the sources for your code and ideas, including websites, papers, and tools like chatGPT.

