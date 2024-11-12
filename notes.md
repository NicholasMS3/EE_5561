# Implementation Notes and Links:

## Dataset
* We will use the SCGM challenge dataset located here: http://cmictig.cs.ucl.ac.uk/niftyweb/challenge/
* Details regarding the challenge, the dataset, and the overall problem of spinal cord gray matter segmentation is described in this paper: https://www.sciencedirect.com/science/article/pii/S1053811917302185
* This challenge consists of training and test data.
*   The training data is comprised of 40 subjects, each with the original image and four separate masks created manually by medical experts. These masks are the "ground truth" for the training of our model.
*   The test data is also comprised of 40 subjects, but only contains the original images because our code will generate the masks to be tested.
* To test our output masks, we can upload them to this website and receive back how well it performs: http://niftyweb.cs.ucl.ac.uk/program.php?p=WMGM
*   We may also calculate our own assessments, but we may have to use a different test dataset because they do not release the masks for the test data as far as I can tell.
*   **Jordan To Do:** Look for more spinal cord datasets that could be used for analysis of model performance.

## Augmentation
* We will use augmentation to generate more training data. This should increase overall model accuracy and make the model more robust to common image quality issues seen during aquisitions such as noise, translations, rotations, and warping.
* TorchIO will be used to generate the augmented training data.
* One example where augmentation is used for skull segmentation is described in: https://dl.acm.org/doi/10.1007/978-3-030-64327-0_6
* A more general description of augmentation for brain MRIs is found in: https://arxiv.org/abs/1902.09383
* This is not just a straightforward application of the augmentations to the original training data given from the challenge. For each new training image generated, a valid mask must also be produced. This needs to be done automatically and with input from the original training data.
*   **Jordan To Do:** Begin to experiment with this process (what types of augmentations to make, how to generate valid masks for new training data, how to use input data formats correctly for various slices).

# Proposal Notes and Links:

## Other Github Ideas for Medical Imaging
1. Pneumonia detection from X-ray images using **Tensor Flow** Convolution Neural Network (https://github.com/sanghvirajit/Medical-Image-Classification-using-CNN/tree/main)
2. **PyTorch and CUDA** Chest X-rays Medical Image Diagnosis usnig CNN (https://github.com/roshansadath/Medical-Image-Diagnosis-using-Convolutional-Neural-Networks)
3. Random chect x-ray medical imaging github (https://github.com/lokeshBI/Medical-Image-Processing/tree/master)
4. Random "Efficient Brain Tumor Detection for Early Intervention with Deep Convolutional Neural Networks" (https://github.com/HassanMahmoodKhan/Efficient-Brain-Tumor-Detection-for-Early-Intervention)
5. CBIM-Medical-Image-Segmentation (https://github.com/yhygao/CBIM-Medical-Image-Segmentation)
   * **Pytorch**
   * Another repo that used this same one (https://github.com/medical-images-process/CNN-Transformer?tab=readme-ov-file)
6. This is a cool project from Facebook/NYU for "faster" MRIs with lots of support, examples, and some datasets (https://github.com/facebookresearch/fastMRI/)
   * **PyTorch and CUDA**
   * Main Article (https://arxiv.org/pdf/1811.08839)

## Githubs with Tons of Paper Links 
1. Links for 100 papers from 2012-2016 (too old?) "Awesome - Most Cited Deep Learning Papers" (https://github.com/terryum/awesome-deep-learning-papers)
2. Source with more Deep Learning Papers on Medical Image Analysis (https://github.com/albarqouni/Deep-Learning-for-Medical-Applications/tree/master)

## Survey Papers
1. Big boi from 2021 (https://www.sciencedirect.com/science/article/pii/S0925231221001314)

## PyTorch Frameworks and Add-Ons
1. Framework built on top of PyTorch specifically for medical images, includes a tutorial for spinal cord gray matter sengmentation (https://github.com/perone/medicaltorch)
2. Another framework built on top of PyTorch. This is a popular one and more recent but not all documentation is complete (https://github.com/nitrain/nitrain/tree/main). There are tutorials for both 2D and 3D computations (https://github.com/nitrain/tutorials/tree/main)
3. Yet another framework, also very new and seems to have good examples (https://github.com/HiLab-git/PyMIC)
4. Older but popular and recently updated 3D computation framework with an example and cool GIF output code (https://github.com/ellisdg/3DUnetCNN/tree/master)
5. Interesting library for PyTorch that helps read in medical images specifically. Maybe could be implemented on top of whatever idea we end up choosing to improve the efficiency of handling the dataset if something similar is not already done (https://www.sciencedirect.com/science/article/pii/S0169260721003102 / https://github.com/fepegar/torchio)

## Datasets
1. A big list (https://github.com/sfikas/medical-imaging-datasets)
