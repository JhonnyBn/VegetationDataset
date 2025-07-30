# VegetationDataset

This repository contains the public dataset used in the article **"Deep Learning Approaches for Detection of Vegetation in Contact with Power Distribution Lines in Urban Environments"**.

The dataset was prepared in a compatible format with the [Ultralytics YOLOv8+](https://docs.ultralytics.com) library.

## 📁 Repository Structure

```
VegetationDataset/
├── custom_dataset.yaml          # Dataset configuration file for YOLO
└── datasets/
    ├── classes.txt              # List of classes (0: vegetationWithoutContact, 1: vegetationContact)
    ├── train/
    │   ├── image1.jpg
    │   ├── image1.txt
    │   └── ...
    ├── val/
    │   ├── image2.jpg
    │   ├── image2.txt
    │   └── ...
    └── test/
        ├── image3.jpg
        ├── image3.txt
        └── ...
```

### `custom_dataset.yaml`

Configuration file that defines the paths to the training, validation, and testing directories, as well as the list of target classes.

### `classes.txt`

Contains the definition of the classes:

- 0 vegetationWithoutContact
- 1 vegetationContact

These classes represent, respectively:
- Vegetation without contact with the power grid
- Vegetation near or in direct contact with distribution cables

### `datasets/`

Folder with data divided into three sets:

- `train/` - Training set
- `val/` - Validation set
- `test/` - Test set

Each directory contains pairs of files:

- `.jpg` (or other image format) - the captured image.
- `.txt` - the corresponding annotation file, in YOLOv8+ format.

Each line of `.txt` has the following format:

<class_id> <x_center> <y_center> <width> <height>

All values are normalized between 0 and 1.