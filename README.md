# Weed detector deep neural network prototype 


This repository exists solely for reproducibility of my prototype of a weed detection neural network. The code mostly comes from the [cocosynth](https://github.com/akTwelve/cocosynth) and [matterport's Mask R-CNN](https://github.com/matterport/Mask_RCNN) repositories. 



'''python
python3 python/image_composition.py --input_dir=datasets/input/ --output_dir=datasets/output/ --count=2000 --width=1080 --height=1080

python3 python/coco_json_utils.py -md datasets/output/mask_definitions.json -di datasets/output/dataset_info.json

# for validation data
python3 python/image_composition.py --input_dir=datasets/input/ --output_dir=datasets/output/val/ --count=1000 --width=1080 --height=1080
'''


