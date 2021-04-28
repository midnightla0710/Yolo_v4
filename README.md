# Yolo_v4資料前處理與部署Colab訓練模型

## <安裝方法一>參考官方文件
  1. [請按此下載檔案1](https://github.com/midnightla0710/Yolo_v4/blob/main/train.rar)
  2. [請按此下載檔案2](https://github.com/tzutalin/labelImg)
  3. labelImg官方說明 ![image](https://github.com/midnightla0710/Yolo_v4/blob/main/Windows%E6%88%96Windows%2BAnaconda.png)
  4. 把要訓練的圖片放進[檔案1](https://github.com/midnightla0710/Yolo_v4/blob/main/train.rar)底下的\VOCdevkit\VOC2021\JPEGImages
  5. 開啟labelImg 之後把Change Save Dir 改成[檔案1](https://github.com/midnightla0710/Yolo_v4/blob/main/train.rar)底下的VOCdevkit\VOC2021\Annotations
  6. 並且點擊Open dir 開啟 \JPEGImages


## <安裝方法二>使用EXE檔
  1. 下載[labelImg](https://github.com/midnightla0710/Yolo_v4/blob/main/windows_v1.8.1.rar)，[(官網載點)](https://tzutalin.github.io/labelImg/)


## <使用方式>
  1. 勾選左上選單的View底下的 Auto Save mode
  2. 可以開始拉框框標記了 (快捷鍵 W:拉框框， D:下一張， A:上一張)
    ![image](https://github.com/midnightla0710/Yolo_v4/blob/main/teach.PNG)
    每標記完一張圖Annotations 底下都會出現一個xml檔案  #檔名不要有中文


## <使用colab訓練>
  1.  使用colab訓練好處：避免Windows+Yolo_v4在呼叫本地端GPU時，可能產生的異常。
  2.  執行[檔案1]中的gen_train_val.py
  3.  [colab訓練方法](https://github.com/midnightla0710/Yolo_v4/blob/main/Yolov4_with_colab.ipynb)


# [檔案1]參數說明
1. voc_label.py
    * classes = ["第一的類別","第二個類別"]
2. obj.data:
    * classes = 1  #類別數量
    * train = 2021_train.txt  
    * valid = 2021_val.txt
    * names = obj.names  #標籤名稱
    * backup = backup  #yolo會將訓練結果的權重存在這裡
3. obj.names:
    * 放標籤名稱  
4. yolov4-tiny.conv.29 :
    * 預訓練權重檔
5. yolov4-tiny-myobj.cfg(config檔)需要修改如下:
    * subdivisions = 16  #記憶體如果不足可以改成32或64
    * max_batches = 2000乘以類別數量    #但最低不可以低於6000，所以一個類別的話要設定為6000
    * steps = 4800,5400   #max_batches 的80%與90%
    * classes=1  #辨識的類別數量，注意有兩個地方要改，分別是220行跟269行
    * filters = 18  #改成(classes 的數量+5) 乘以3   
##備註##  
[convolutional]  
size=1  
stride=1  
pad=1  
filters=18   <-- 下面有一個activation=linear的才是要改的，原檔是212跟263行  
activation=linear  
