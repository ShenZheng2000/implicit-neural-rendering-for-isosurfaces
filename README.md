# implicit-neural-rendering-for-isosurfaces
This is a **official** Pytorch implementation for our project "**Implicit Neural Rendering For Isosurfaces**".

# Short Summary
This project aims to develop a fully convolutional neural network with [Siren](https://arxiv.org/abs/2006.09661) activation function to render isosurfaces with three groups of parameters, including image resolution, (two) viewpoints and isovalue. 

# Sample Results

# Pre-requisites
1. Windows/Linux
2. Python3
3. CPU/GPU+CUDA+CUDNN

# Prepare Dataset
The training and testing images (2021.9.20 version) can be downloaded from [BaiduYun](https://pan.baidu.com/s/12LnBpCqz4mlI_BohBoogQw) with code `o7ad`. After that, unzip the files and put the training images at `/data/train_data` and testing images at `/data/test_data`. For each folder (train or test), there will be one txt file with numbers of png files. 

# Train
Run the following command in terminal 

```
python main.py --train_test train
```

# Test
Run the following command in terminal 

```
python main.py --train_test test
```

# Output Files
The output files consists of the following. 

The visualized outcome on training images: `/train_iter`. 

The visualized outcome on testing images: `/test_iter`

The recent model weights: `net.pkl`

The logout file: `log{month}{day}.txt`

The up-till-now training loss curve: `loss_curve2.png`


# Hyperparameters
Here are some crucial hyperparameters you may be interested in.

1. Basic Hyperparameters

| Name                    | Type | Default           | Description                |
|-------------------------|------|-------------------|----------------------------|
| **save_txt_root_path**      | str  | ./data/train_data | Path for training txt file |
| **save_txt_root_path_test** | str  | ./data/test_data  | Path for testing txt file  |
| **input_image**             | str  | ./data/train_data | Path for training images   |
| **input_image_test**        | str  | ./data/test_data  | Path for training images   |
| **input_image_test**        | str  | ./data/test_data  | Path for training images   |
| **train_test**              | str  | train             | Chooce train or test       |

2. Training/Testing Hyperparameters

| Name          | Type  | Default | Description                                |
|---------------|-------|---------|--------------------------------------------|
| **epoch**         | int   | 501     | The training epochs                        |
| **side_len**      | int   | 512     | The resolution ratio of an (squared) image |
| **batch_size**    | int   | 120000  | The training batch size                    |
| **lr_rate**       | float | 5e-5    | The initial learning rate                  |
| **train_weight**  | str   | net.pkl | The weights to resume training             |
| **test_weight**  | str   | net.pkl | The weights for testing           |
| **use_scheduler** | bool  | True    | Whether to use learning rate scheduler     |


3. Model Hyperparameters

| Name            | Type | Default | Description                                |
|-----------------|------|---------|--------------------------------------------|
| **is_final_linear** | bool | True    | Whether to use an ending linear layer      |
| **is_final_res**    | bool | True    | Whether to use an ending residual block    |
| **in_features**     | int  | 5       | Input channel number                       |
| **out_features**    | int  | 3       | Output channel number                      |
| **init_features**   | int  | 256     | Middle channel number                      |
| **num_res**         | int  | 15      | Numbers of hidden layers (residual blocks) |
| **is_pos_encode**   | bool | False   | Whether to use [positional encoding](https://arxiv.org/pdf/2003.08934.pdf)         |
| **innermost_res**   | bool | True    | Whether to use a starting residual block   |

# Sample Visualized Images
TODO

# Citation 
TODO

# Recommended Readings
Please refers to our archieved [repository](https://github.com/ShenZheng2000/Isosurface-Rendering) for recommended papers about this topic. 
