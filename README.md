# NeRF Implementation

CSCI-B 657 | Jaydeep Chauhan, Atharva Kulkarni

## 1. Overview
This is a pytorch-lighning implementation of paper [NeRF](https://www.matthewtancik.com/nerf). We experimented on the synthetic blenders dataset and try to reproduce the results for all 8 scene objects by training the model for 125K iterations and 200K iterations(only on lego and hotdog), we calculated the PSNR(Peak signal to noise ratio) as a metric to evaluate the generate 3D view quality and compare it with other contemporary methods. For training we used IU's carbonate gpu cluster.

## 2. Steps for training
#### Training :-
- First download the synthetic blender dataset from here : [Blender Dataset](https://drive.google.com/drive/folders/1JDdLGDruGNXWnM1eqY1FNL9PlStjaKWi) and extract the dataset.     
- Now to train the model first replace the ```dataset_path``` with your local path on your machine.
- Set the ```IMG_DIMENSION``` to (400, 400).
- All other parameters are adapted from the original paper, but you can adjust the parameter according to your preference.
- Train your model using  ```python train.py``` on local machine.
- During training, you can view the training loss and generated 3D view using tensorflow logger on [localhost](localhost:6006)
- To train the model, you might need to run it on ```carbonate``` machine using ``sbatch job.sh``.

#### Testing :-
- After training you can see the folder names logs inside this NeRF folder.
- Inside that folder there would be checkpoints folder and tfevent file.
- Set the ```root_dir``` path of the dataset scene object and ```checkpoint path``` in the ```eval.py```.
- After evaluate your model using ```python eval.py```
- It will generate a recursive folders in this fashion ```results/{dataset_name}/{scene_name}``` to store the final visualizations.

## 3. Results
