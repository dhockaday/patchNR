# PatchNR: Learning from Small Data by Patch Normalizing Flow Regularization

This code belongs to the paper [1] available at https://arxiv.org/abs/2205.12021. Please cite the paper, if you use this code.

The repository contains an implementation of patchNRs and cPatchNRs as introduced in [1]. It contains scripts for reproducing the numerical example Superresolution in Section 5.1, CT imaging in Section 5.2 and Deblurring in Section 5.3.

The folder `input_imgs` contains the images for learn the patchNR and cPatchNR, a validation image and the test image illustrated in the paper.

For questions and bug reports, please contact Fabian Altekrüger (fabian.altekrueger@hu-berlin.de), Alexander Denker (adenker@uni-bremen.de) or Paul Hagemann (hagemann@math.tu-berlin.de).

## CONTENTS

1. REQUIREMENTS  
2. USAGE AND EXAMPLES
3. REFERENCES

## 1. REQUIREMENTS

The code requires several Python packages. We tested the code with Python 3.9.7 and the following package versions:

- pytorch 1.10.0
- numpy 1.21.2
- tqdm 4.62.3
- scipy 1.7.1
- freia 0.2
- dival 0.6.1
- odl 1.0.0

Usually the code is also compatible with some other versions of the corresponding Python packages.

## 2. USAGE AND EXAMPLES

You can start the training of the patchNR and cPatchNR by calling the script `train_patchNR.py` and `train_cPatchNR.py`, respectively. There you can choose between the different image classes. 

### SUPERRESOLUTION

The scripts `patchNR_superres.py` and `cPatchNR_superres.py` are the implementations of the superresolution example in [1, Section 5.1]. The used images of material microstructures have been acquired in the frame of the EU Horizon 2020 Marie Sklodowska-Curie Actions Innovative Training Network MUMMERING (MUltiscale, Multimodal and Multidimensional imaging for EngineeRING, Grant Number 765604) at the beamline TOMCAT of the SLS by A. Saadaldin, D. Bernard, and F. Marone Welford. The low-resolution image used for reconstruction is generated by artificially downsampling and adding Gaussian noise. For more details on the downsampling process, see [1, Section 5.1]. 

### CT IMAGING

The script `patchNR_CT.py` is the implementation of the CT example in [1, Section 5.2]. Here you can choose between the full angle and the limited angle case. The used data is from the LoDoPaB dataset [3], which is available at https://zenodo.org/record/3384092##.Ylglz3VBwgM.

### DEBLURRING

The scripts `patchNR_deblurring.py` and `cPatchNR_deblurring` are implementations of the deblurring example in [1, Section 5.3] for the Kylberg Texture [2] `Lentils`, which is available at https://kylberg.org/kylberg-texture-dataset-v-1-0. The ground truth and the learning image are different 500×500 sections cropped from the original texture images, while the noisy data is generated by applying a blur kernel and adding Gaussian noise. The blur kernel is the first blur kernel in [4], which is available at https://webee.technion.ac.il/people/anat.levin/papers/LevinEtalCVPR09Data.rar. You have to extract the first file (im05_flit01.mat) and save it into the repository.

### ZERO-SHOT SUPERRESOLUTION

The script `patchNR_zeroshot.py` is the implementation of the zero-shot superresolution example in [1, Appendix A]. The patchNR was tested on the BSD68 dataset [5] and the low-resolution image used for reconstruction is generated by artificially downsampling and adding Gaussian noise. For more details on the downsampling process, see [1, Appendix A]. 

## 3. REFERENCES

[1] F. Altekrüger, A. Denker, P. Hagemann, J. Hertrich, P. Maass and G. Steidl.  
PatchNR: Learning from Small Data by Patch Normalizing Flow Regularization.   
ArXiv Preprint#2205.12021

[2] G. Kylberg.  
The Kylberg texture dataset v. 1.0.  
Centre for Image Analysis, Swedish University of Agricultural Sciences and Uppsala University, 2011.

[3] J. Leuschner, M. Schmidt, D. O. Baguer and P. Maass.  
LoDoPaB-CT, a benchmark dataset for low-dose computed tomography reconstruction.  
Scientific Data, 9(109), 2021.

[4] A. Levin, Y. Weiss, F. Durand and W. T. Freeman.  
Understanding and evaluating blind deconvolution algorithms.  
IEEE Conference on Computer Vision and Pattern Recognition, 2009, pp. 1964-1971.

[5] D. Martin, C. Fowlkes, D. Tal, and J. Malik.  
A database of human segmented natural images and its application to evaluating segmentation algorithms and measuring ecological statistics.  
Proceedings Eighth IEEE International Conference on Computer Vision. ICCV 2001, volume 2, pages 416–423. IEEE, 2001.
