# DigestPath2019
## Colonoscopy tissue segmentation and classification
The goal of the task was to evaluate automatic algorithms colonoscopy tissue screening from digestive system pathological images. This is the first challenge and first public dataset on colonoscopy tissue screening. Release of the large quantity of expert-level annotations on digestive-system pathological images has substantially advance the research on automatic pathological object detection and lesion segmentation. 


A total of 450 patients' 750 tissue slices of an average size of 3000x3000 were provided as the training set. Also another 150 patients' 250 tissues were provided as the testing set.

## Dataset Description:
(Directly from https://digestpath2019.grand-challenge.org/Dataset/)

Colonoscopy pathology examination can find cells of early-stage colon tumor from small tissue slices. Pathologists need to daily examine hundreds of tissue slices, which is a time consuming and exhausting work. Here we propose a challenge task on automatic colonoscopy tissue segmentation and screening, aiming at automatic lesion segmentation and classification of the whole tissue (benign vs. malignant). A total of 450 patients' 750 tissue slices of an average size of 3000x3000 will be provided as the training set. The fine pixel-level annotations of lesion and the diagnosis of the tissues will be labelled by experienced pathologists. We will also provide another 150 patients' 250 tissues as the testing set. The data in the challenge will show great variations in terms of appearance because the data are collected from multiple medical centers, especially from several small centers in developing countries/regions. Image style differences can be an obstacle for the screening task. Holding the challenge and releasing the large quantity of expert level annotations will attract much attention from the medical imaging community and substantially advance the research on automatic colonoscopy screening. All whole slide images were stained by hematoxylin and eosin and scanned at X20.

## METHODOLGY:
As, the challenge is not yet over, we could not disclose our methodology but we have updated the docker image and also uploaded some test images along with the ground-truth which could be used for testing of the docker.

The link for docker is:

https://drive.google.com/file/d/1EJWc63fdyV5FT6hdVNwKUHFx7mhiW17s/view?usp=sharing


Once, the challenge gets over we will upload all the codes which can be used for training as well as testing on Colonoscopy images.

Till, then for you can test the algorithms on your Digestpath dataset by following the below mentioned procedure:

`docker load --input 2016bec062_task2.tar`

For running the docker:

`docker run -dit --runtime nvidia --name 2016bec062_task2_container -v /home/digestpath/TestData:/input:ro -v /output digestpath:2016bec062_task2`

For Execution of the docker:
`docker exec -it 2016bec062_task2_container python /digestpath/Segmentation.py`

After that copy and move the results from Docker container to local disk:

`docker cp 2016bec062_task2_container:/output Result`

`mv Result/output/* Result/`

In the dataset folder, some of the samples are given.

The results would contain prediction folder and .csv file predicting the accuracy of samples to be positive.
## Citation
Li, J., Yang, S., Huang, X., Da, Q., Yang, X., Hu, Z., ... & Li, H. (2019, June). Signet Ring Cell Detection with a Semi-supervised Learning Framework. In International Conference on Information Processing in Medical Imaging (pp. 842-854). Springer, Cham. (https://arxiv.org/abs/1907.03954)



