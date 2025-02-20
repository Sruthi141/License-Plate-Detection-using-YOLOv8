# License Plate Detection using YOLOv8

## Project Overview

This project focuses on detecting license plates from images and video feeds using the **YOLOv8** (You Only Look Once) object detection model. The goal is to accurately identify and localize license plates in real-time, making it useful for applications like automated toll collection, parking management, and traffic monitoring.

## Features

- **Real-time detection** of license plates from video feeds.
- **High accuracy** using YOLOv8 model.
- **Custom dataset training** for improved performance.
- **Supports image and video input**.

## Requirements

To set up and run this project, install the following dependencies:

- Python 3.8+
- OpenCV
- Ultralytics YOLOv8
- Torch (PyTorch)
- NumPy
- Matplotlib
- TQDM

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-repo/Licence-Plate-Detection-using-YOLO-V8.git
   cd Licence-Plate-Detection-using-YOLO-V8
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Dataset Setup

Ensure you have a dataset structured as follows:

```
/dataset/
   /train/
      /images/  # Training images
      /labels/  # Corresponding YOLO format labels
   /valid/
      /images/  # Validation images
      /labels/  # Corresponding YOLO format labels
```

Modify `data.yaml` to specify the correct dataset paths.

## Training the Model

To train YOLOv8 on the dataset, run:

```bash
python ultralytics/yolo/v8/detect/train.py --model yolov8n.pt --data data.yaml --epochs 100
```

## Running Detection

For detecting license plates in images:

```bash
python ultralytics/yolo/v8/detect/predict.py --weights runs/detect/train/weights/best.pt --source test.jpg
```

For video:

```bash
python ultralytics/yolo/v8/detect/predict.py --weights runs/detect/train/weights/best.pt --source video.mp4
```

## Results

- The detected license plates will be shown with bounding boxes.
- Output images/videos will be saved in the `runs/detect/predict` directory.

## Contributors

- Kommati sruthi and Team


## License

This project is open-source and free to use for educational purposes.

