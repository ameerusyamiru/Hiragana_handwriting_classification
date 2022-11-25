# Hiragana Handwriting Classification
My proposed project during the KPT-PACE Machine Learning workshop is Hiragana Handwriting Classification. The objective of the project is classify each handwritten hiragana character to determine the diffences between one character with another.

![japanese handwriting](https://www.fluentin3months.com/wp-content/uploads/2021/09/hiragana-vs-katakana.jpg)

Before starting, make sure you have already installed Python and Pytorch and run inside your Docker or Environemnt.

# 1) Download project to your Jetson Nano:
```
git clone https://github.com/ameerusyamiru/Hiragana_handwriting_classification.git

```
```
pip install -r requirements.txt
```

It is also can be download into your local machine before starting the training. Use `pip` command to install the required modules. Place your dataset inside `/data` folder. You may use your own dataset or find it from [inoueMashuu's github](https://github.com/inoueMashuu/hiragana-dataset).
Before start training your dataset, make sure all the requirement listed in `requirement.txt` are installed inside your Docker or Environment

# 2) To start training your dataset, run this:
```
python train.py --model-dir=models/apple --epochs=50 --batch-size=4 --workers=2 --lr=0.001 --arch=resnet34 data/hiragana
```
You can adjust the epoch, batch size, learning rate and pre-trained model accordingly. The model file will be save inside `/models/hiragana` with name `model_best.pth.tar`

# 3) After finish training, run the conversion file `onnx_export.py` to convert the tar format to onnx format:
```
python onnx_export.py --model-dir=models/hiragana
```
You will find a file inside `/models/apple` with name `resnet34.onnx`. The file will depends on the pretrained model name that you use during the training.You can also download the file from my drive,
```
gdown https://drive.google.com/uc?id=1JDL9Ttwepzze0nQJobEIxUsownitDeAF
or
gdown https://drive.google.com/uc?id=1irmM1qMHo178qSXRtO-36UOSY3JxqKeC
```

# 4) To run the inference:
>from image:
>```
>python imagenet.py --model=models/hiragana/resnet34.onnx --input_blob:input_0 --output_blob:output_0 --labels=data/hiragana/labels.txt image.jpg
>```
>from video
>```
>python imagenet.py --model=models/hiragana/resnet34.onnx --input_blob:input_0 --output_blob:output_0 --labels=data/hiragana/labels.txt video.mp4
>```
>from webcam
>```
>python imagenet.py --model=models/apple/resnet34.onnx --input_blob:input_0 --output_blob:output_0 --labels=data/hiragana/labels.txt /dev/video0
>```
To check which webcam available in your jetson, run `/dev/video*` in the terminal before running inference code.

**Please comment any improvement that can be add into the code.Thank you for using this programs.**

Here my full video on this project:
