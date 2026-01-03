# YOLO-based-Planthopper-Detection-System
<<<<<<< HEAD
系统功能：基于YOLO算法实现白盘中稻飞虱的检测，并实现了简单的可视化操作

![流程](F:\SoftWare_Files\Typora Files\Pictures\流程.png)

![系统界面图片](F:\SoftWare_Files\Typora Files\Pictures\系统界面图片.png)

### 环境配置

1. 安装 Anaconda

首先，请确保你已经从 [Anaconda 官网](https://www.anaconda.com/products/distribution) 下载并安装了适合你操作系统的 Anaconda 版本。

2. 创建虚拟环境

```bash
conda create -n yolo-rph python=3.8
conda activate yolo-rph
cd yolo-rph
```

3. 安装依赖

```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

pip install -r ./requirements.txt
```

### 运行

训练

```bash
yolo task=detect mode=train model=yolov8n.pt epochs=150 batch=32 device=0 worker=0 imgsz=640 data=D:\Code\Pycharm_Code\ultralytics-main\data\Rice_Planthopper.yaml resume=True
```

评估

```bash
yolo task=detect mode=val model=D:\Code\Pycharm_Code\ultralytics-main\runs\detect\train-EfficientVit\weights\best.pt data=D:\Code\Pycharm_Code\ultralytics-main\data\Rice_Planthopper.yaml
```

导出为ONNX

```bash
yolo task=detect mode=export model=D:\Code\Pycharm_Code\ultralytics-main\runs\detect\train-yolov8\weights\best.pt format=onnx
```

切片推理

```bash
python predict_with_sahi.py --yolov8_model_path D:\Code\Pycharm_Code\ultralytics-main\runs\detect\train-RepGhost-MSDA-NWD(loss)\weights\train-RepGhost-MSDA-NWD(loss).onnx --mode 1 --image_path data/origin_images/0_SV_IMG_20221209_132750_819.jpg
```

=======
A Planthopper Detection System Based on YOLO Algorithm
>>>>>>> 9f4199c97e445d3ef477e2b86c254b12bbf5e12a
