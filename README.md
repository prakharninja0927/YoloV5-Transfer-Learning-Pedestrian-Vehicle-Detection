# Pedestrian And Vehicle Detection using YOLOv5 Transfer Learning

This guide outlines the steps to train a custom YOLOv5 model for pedestrian and vehicle detection using transfer learning. We will use OpenImages dataset for collecting data.

## Step 1: Downloading Data

First, we need to download images from the OpenImages platform using the `oi_download_dataset` tool provided by Google. Run the following command:

```bash
oi_download_dataset --base_dir download --csv_dir download --labels Car Bicycle Person Truck Bus Motorcycle --format darknet --limit 500
```

## Step 2: Data Preparation

Perform data preparation tasks such as data cleaning, augmentation, and labeling. You can use the `datapreparation.ipynb` notebook for this purpose.

## Step 3: Clone YOLOv5 Repository

Clone the YOLOv5 model repository from GitHub:

```bash
git clone https://github.com/ultralytics/yolov5
```

Unzip the `yolov5.zip` file containing pre-trained models.

## Step 4: Install Requirements

Install the required Python packages by running:

```bash
pip install -r yolov5/requirements.txt
```

## Step 5: Write Custom `model.yaml` File

Write a custom `model.yaml` file specifying the details of your custom dataset and model configuration.

## Step 6: Train the Model

Train the YOLOv5 model using the following command:

```bash
python yolov5/train.py --data model.yaml --weights yolov5s.pt --epochs 15 --batch 8 --freeze 10
```

Adjust parameters such as `--epochs`, `--batch`, and `--freeze` as per your requirements.

## Step 7: Validate the Trained Model

Validate the trained model using the following command:

```bash
python yolov5/val.py --data model.yaml --weights yolov5/runs/train/exp/weights/best.pt
```

Ensure to replace `best.pt` with the actual name of your best-trained model weights.

## Conclusion

By following these steps, you should have successfully trained a custom YOLOv5 model for pedestrian and vehicle detection using transfer learning. Adjustments can be made to the parameters and dataset labels as needed for your specific use case.

## Reference
Please Visit this website where I got all of my info to train Yolov5 on myown data : https://kikaben.com/yolov5-transfer-learning-dogs-cats/
