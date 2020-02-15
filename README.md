<h1>Malaria-Bounding-Boxes</h1>

<h2>Business/Real World Problem-</h2>
<h3>Problem Statement:- </h3>
Malaria is a disease caused by Plasmodium parasites that remains a major threat in global health, affecting 200 million people and causing 400,000 deaths a year. The main species of malaria that affect humans are Plasmodium falciparum and Plasmodium vivax. For malaria as well as other microbial infections, manual inspection of thick and thin blood smears by trained microscopists remains the gold standard for parasite detection and stage determination because of its low reagent and instrument cost and high flexibility. Despite manual inspection being extremely low throughput and susceptible to human bias, automatic counting software remains largely unused because of the wide range of variations in brightfield microscopy images. However, a robust automatic counting and cell classification solution would provide enormous benefits due to faster and more accurate quantitative results without human variability; researchers and medical professionals could better characterize stage-specific drug targets and better quantify patient reactions to drugs.

The data consists of two classes of uninfected cells (RBCs and leukocytes) and four classes of infected cells (gametocytes, rings, trophozoites, and schizonts).Annotators were permitted to mark some cells as difficult if not clearly in one of the cell classes.

<h2> Source/Useful links- </h2>
The Dataset can be downloaded from-

1-Data Source: https://www.kaggle.com/kmader/malaria-bounding-boxes
<h3>Data Overview-</h3>

We are given folder named malaria which contains 3 files-

1-Images -contains train and test images.

2-Test json- it contains test image name and its bounding box information in json format.

3-Training json-it contains train image name and its bounding box information in json format.

<h2>Real World/Business objectives and constraints-</h2>

1-No low-latency requirement.

2-Interpretability is important.

3-Errors can be costly.

4-Probability of a cell belonging to each class is needed.

<h2>Mapping the real world problem to machine learning problem-</h2>
<h3>Type of problem-</h3>

Given an image of blood sample, we need to mask the cell and label to which class(infected vs uninfected) it belongs (applying mask-rcnn).

<h3>Performance Metric-</h3>

mAP(mean average precision)- The average or mean of the average precision (AP) across all of the images in a dataset is called the mean average precision, or mAP.

<h3>Losses-</h3>

rpn_class_loss : How well the Region Proposal Network separates background with objects

rpn_bbox_loss : How well the RPN localize objects

mrcnn_bbox_loss : How well the Mask RCNN localize objects

mrcnn_class_loss : How well the Mask RCNN recognize each class of object

mrcnn_mask_loss : How well the Mask RCNN segment objects

total_loss=sum of all the losses

so objective is to minimize the total loss

<h2>Machine learning objectives and constraints-</h2>

1-Probabalities of cell belonging to specific category is needed.

2-no latency constraints as in medical field reports are given within few hours.

3-Interpretability.

<h2>References:-</h2>

1-https://github.com/matterport/Mask_RCNN

2-https://machinelearningmastery.com/how-to-train-an-object-detection-model-with-keras/

3-https://www.jeremyjordan.me/evaluating-image-segmentation-models/




