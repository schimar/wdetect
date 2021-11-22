# Weed detector deep neural network prototype 

========================================================================================

This repository exists solely to reproduce my first version of a weed detection neural network. The code comes from the [cocosynth](https://github.com/akTwelve/cocosynth) and [matterport's Mask R-CNN](https://github.com/matterport/Mask_RCNN) repositories, but I made some minor changes to suit this case. For detailed info on software dependencies, please refer to the [cocosynth](https://github.com/akTwelve/cocosynth) repository. Make sure that the two folders are in your working directory, and change the relative paths if needed. 

<br/>

There are two basic steps to be done, namely: 

1) creating the synthetic images and COCO *json* files  
2) training the model and performing visual validation 


<br/>


========================================================================================
<br/> 
<br/> 


## 1) creating the synthetic images and COCO *json* files


I created 3000 images, with 2000 for training and the remainder for validation:

```
python3 python/image_composition.py --input_dir=datasets/input/ --output_dir=datasets/output/ --count=2000 --width=1080 --height=1080

python3 python/coco_json_utils.py -md datasets/output/mask_definitions.json -di datasets/output/dataset_info.json

# for validation data
python3 python/image_composition.py --input_dir=datasets/input/ --output_dir=datasets/output/val/ --count=1000 --width=1080 --height=1080

python3 python/coco_json_utils.py -md datasets/output/mask_definitions.json -di datasets/output/dataset_info.json
```  

========================================================================================

<br/> 

## 2) training the model and performing visual validation

Note that in the following code, the steps for training the model are commented out. Change this, if you want to run training yourself. Further, I changed the visualize.display_instances function in the Mask_RCNN repo to write the resulting output image to ```cocosynth/datasets/output/plt/test.png```.

```
python3 wdetect.py
```






