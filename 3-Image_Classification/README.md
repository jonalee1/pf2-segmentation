# Image classification 
This is a python project which contains code and data for training a Computer Vision model for binary classification.


The two classes are :
1) plain t-shirts 
2) typography t-shirts

We will be leveraging several pre-trained CV models such as Resnet, Inception and train the model  to our use case with only a limited set of data of less than 500 images per class.

## Google Colab and GPU requirements:
* The jupyter notebook included contains the raw code to iterate using different models in an interactive fashion. This notebook is run on Google colab. To execute it, all you have to do is upload to your google drive and open it using Colab.

* It is adviced to train Deep learning models on GPUs since they are quite fast compared to CPUs. 
On Colab, you can accomplish by selecting the GPU runtime. 

* Tensorflow>=2.0 doesn't need any code changes to switch between CPU vs GPU training.


## Setting up the environment
Incase you are running the code in a local environment or on a server, you can follow the steps below to set up your environment:
* Step 1 : Create a new python environment using either pip or conda 
* Step 2 : Install the requirements using 

    ```bash
    pip install -r requirements.txt
    ```

## Data overview and organization

The data for training and validation is set up in the following way:
```
input
├── images
│   ├── train
│   │   ├── plain
│   │   └── typography
│   └── valid
│       ├── plain
│       └── typography
```

This strucuture enables Tensorflow library to automatically build the labels based on the directory names without explicity mentioning them.

> Each leaf level direcotry contains images in the .jpg format which will be read in batches for training and validation. This eliminates the need to load all the data in memory


## Important files:
* `src/config.ini`: contains various configurations for training the model
* `src/engine.py`: the main code to be executed 

# Code execution:
1. Before executing the code, change the `home_dir` variable in `src/config.ini` file to this project folder

2. Move to `src` folder:
    ```bash
    cd src
    ```

3. Execute the `engine.py` file 
    ```
    python engine.py
    ```

4. To run hyperparameter tuning, set the `hp_tune` param in `src/config.ini` to `True` and set your choice of hyper parameters in the `param_grid` and run the following command
    ```
    python engine.py
    ```


## Resources:
1. [Transfer learning](https://blogs.nvidia.com/blog/2019/02/07/what-is-transfer-learning/)
2. [Resnet Paper](https://arxiv.org/pdf/1512.03385.pdf)
3. [Inception Paper](https://arxiv.org/pdf/1409.4842.pdf)
4. [Tensorflow](https://www.tensorflow.org/)
5. [Google colab](https://colab.research.google.com/)