# Setup
Here are instructions to setup the environment

<ins>**Local** </ins>

1. Download dataset from https://drive.google.com/file/d/1LBg92gxtyrHnsjSQ0XQBzSl8lupePIsJ/view?usp=sharing
2. Make sure all dependencies are installed
	- tensorflow
	- matplotlib
	- pillow
	- pandas
	- numpy
3. Notebook to run is located in segmentation/train_everything/Notebook.ipynb

<ins>**Cloud** </ins>

Depending on which cloud provider you are using this can vary. I recommend [Paperspace](https://www.paperspace.com/) or Google Collab. 
1. Download dataset from https://drive.google.com/file/d/1LBg92gxtyrHnsjSQ0XQBzSl8lupePIsJ/view?usp=sharing to cloud storage or if using Collab you can mount your Google Drive directly: https://colab.research.google.com/notebooks/io.ipynb
2. Paperspace or Collab both have all the necessary dependencies for this project so no additional install should be required. 
3. You can either import the entire segmentation folder to the cloud or just use the notebook located in segmentation/train_everything/Notebook.ipynb.
4. If you decide to just use the notebook, you will need to also import /segmentation/config/class_dict.csv for the classes.
