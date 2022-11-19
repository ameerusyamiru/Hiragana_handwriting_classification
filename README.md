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

