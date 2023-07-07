# Setup
Here are instructions to setup the environment

<ins>**Local** </ins>

1. Download dataset from https://drive.google.com/file/d/1LBg92gxtyrHnsjSQ0XQBzSl8lupePIsJ/view?usp=sharing
2. Make sure all dependencies are installed
	- [tensorflow](https://www.tensorflow.org/install/pip)
	- [matplotlib](https://matplotlib.org/stable/users/installing/index.html)
	- [pillow](https://pypi.org/project/Pillow/)
	- [pandas](https://pypi.org/project/pandas/)
	- [numpy](https://pypi.org/project/numpy/)
3. Notebook to run is located in segmentation/train_everything/Notebook.ipynb

<ins>**Cloud** </ins>

Depending on which cloud provider you are using this can vary. I recommend [Paperspace](https://www.paperspace.com/) or Google Collab. 
1. Download dataset from https://drive.google.com/file/d/1LBg92gxtyrHnsjSQ0XQBzSl8lupePIsJ/view?usp=sharing to cloud storage or if using Collab you can mount your Google Drive directly: https://colab.research.google.com/notebooks/io.ipynb
2. Paperspace or Collab both have all the necessary dependencies for this project so no additional install should be required. 
3. You can either import the entire segmentation folder to the cloud or just use the notebook located in segmentation/train_everything/Notebook.ipynb.
4. If you decide to just use the notebook, you will need to also import /segmentation/config/class_dict.csv for the classes.

# Notebook
Here are some notes about the notebook

1. Make sure the GPU is being used otherwise the training will take an extended period of time. This is done in **cell 3**.
2. In **cell 4**, specify the path to where the root of the dataset is located in the **dataset_path** variable. Also specify the path to the class_dict.csv file in the variable **classes_csv_path**.
3. **IMPORTANT NOTE:** In **cell 5**, multiple lists are created with paths to the images. The RGB and Annotated paths lists matching depends on the OS. The lists **must** be in the same order of the path name, ex:
	* fog_training_rgb = [**GOPR0475_frame_000041_rgb_anon.png**, **GOPR0475_frame_000049_rgb_anon.png**]
	* fog_training_annotated = [**GOPR0475_frame_000041_gt_labelColor.png**, **GOPR0475_frame_000049_gt_labelColor.png**]
	* Note how in both of the lists GOPR0475_frame_000041 comes first followed by GOPR0475_frame_000049 (order is the same). A way to ensure this order is always kept is to do .sort() for each list in this cell. For Windows machines however this order should automatically be the default. 
4. The data generator in **cell 10** is used for both the training and validation sets. For the training set data augmentation is applied as seen in the **__data_generation** function in the class. 
5. While the training is happening, the logs for each condition is stored in {condition}/logs/logs.csv. The weights are stored in {condition}/{condition}-weights.h5, only the epoch with the highest validation accuracy weights are saved. There are also logs stored to use with TensorBoard located in {condition}/logs.
