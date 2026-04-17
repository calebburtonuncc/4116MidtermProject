# 4116MidtermProject
This is the submission for Caleb Burton's 4116 Midterm Assignment. This includes the notebook from assignment 1, SRGAN notebook training, and this README file.

This project builds on assignment 1, which was a baseline classifier on high resolution images completed earlier in the semester. Assignment 1's model will be referred to as Model A throughout this project, along with the SRGAN model being Model B. Model B is a model that is trained including a process that upscales lower resolution images into high resoltuion images and the program tries to distinguish between generated and real photos. The goal is to get Model B to understand the patterns deeply as a byproduct of it needing to generate missing details. 

The Dataset is shared with Assingment 1, being a group of OCT images. These fall under 3 classes: Normal, DME, and DRUSEN. 

DISCLAIMER: 
(The project, and professor during class, states this is to be a binary classifier, which would mean that DME and DRUSEN would be clumped into one class of DISEASED. I had already started on this assignment with training 150 epochs on 3 classes by the time this realization reached me. I understand point deductions if that is needed, but I believe this project to be nearly identical either way you go. I did Assignment 1 with 3 classes, so I am not sure how results would be accurate if classes are different. Three classes likely had to do with my low accuracy ratings)

## Steps taken to complete this project:
1. Upload dataset and Model A weights into Google Drive for recall and evaluation
2. Resize the data images to 128x128 for pipeline, then create 32x32 versions for SRGAN to upscale later
3. Create a generator (upscaler) and a discriminator (distinguishing upscaled and original images
4. Pretrain the generator on 10 epochs so that the reconstruction task is ready to start
5. Alternate between generator and discriminator updates to train the SRGAN. I monitored the generated images here and there
6. Use the now trained generator to make a new dataset of pscaled images. Save those images with the same test and train folder names and setup (Train and Test are folders that have each of the 3 classes within each of them)
7. Copy Model 1's classifier architecture for a fair comparison between the two training datasets
8. Using the mounted Google Drive data paths, have a folder that saves all epoch progress so that when the runtime naturally resets, you can easily pick up from the next epoch
9. (when the runtime does reset, just run every cell again to ensure varaibles are made and meaningful)
10. Run AUC, F1 Score, and Accuracy tests to measure model performance for Model A and B.

## Observations
Model B did not outperform Model A. This could be for multiple reasons. This could include the fact that these images were already pretty small, so downscaling them could've easily lost valuable information. The generative model could have used more epochs as well. If I was not knee deep in senior design, I may have been able to experiment with this. Typically generative models need big datasets because we lose information on some images. 
