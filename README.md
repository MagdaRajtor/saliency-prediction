# saliency-prediction
Comparing prediction changes by different fine-tuning data

### Dataset description
1. ART - 150 images of paintings (https://www-percept.irisa.fr/art_paintings/)
   - stimuli, fixation and saliency maps
2. EMOTIONS - 698 images with emotional stimuli (https://ncript.comp.nus.edu.sg/site/ncript-top/emotionalattention/)
   - stimuli, fixation (binary) and saliency (continous) maps
3. CAT2000 - a sample of 400 images from the training set (https://saliency.tuebingen.ai/datasets.html)
   - stimuli and saliency maps (called as fixation)
  
### Project overview
Baseline performance of the TranSalNet_Res model (taken from https://github.com/LJOVO/TranSalNet) was established by calculating SSIM (Structural Similarity Index) scores for all three datasets. Characteristics of the most and least accurately predicted images were inspected (in the attatched presentation).

Later the ART and EMOTIONS datasets were split for training, validation and testing (70-15-15) and used seperately for finetuning the model. Comparison of the two resulting models and the base one revealed that, interestingly, model finetuned on paintings performed better also with the imotional images - and vice versa. The raw predictions of three models on all testing datasets are provided (in the _results_ folder), as well as the p-values for their statistically significant differences (in the notebook). Additionally, mean SSIM scores for each category in CAT2000 are given to compare the models' performance.

### What I learned:
* finetuning a pretrained model
* processing large volumes of nested data
* padding, resizing and restoring images
* torch, torchvision, PIL and skimage libraries
