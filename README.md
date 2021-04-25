# yolo_v4


## <安裝_方法一>參考官方文件
1. **[請按此下載檔案1]**(https://github.com/midnightla0710/Yolo_v4/blob/main/train.rar)
2. **[請按此下載檔案2]**(https://github.com/tzutalin/labelImg)
3. labelImg官方說明
    ![image](https://github.com/midnightla0710/Yolo_v4/blob/main/Win%E6%88%96Win%2BAnaconda.png)
5. 把要訓練的圖片放進[下載檔案1](https://github.com/midnightla0710/Yolo_v4/blob/main/train.rar)底下的\VOCdevkit\VOC2021\JPEGImages
6. 開啟labelImg 之後把Change Save Dir 改成[下載檔案1](https://github.com/a13140120a/yolo_v4/blob/main/train.rar)底下的VOCdevkit\VOC2021\Annotations
7. 並且點擊Open dir 開啟 \JPEGImages


## <安裝_方法二>使用EXE檔
1. 下載[labelImg](https://github.com/midnightla0710/Yolo_v4/blob/main/windows_v1.8.1.rar)，[(官網載點)](https://tzutalin.github.io/labelImg/)


## <使用方式>
1. 勾選左上選單的View底下的 Auto Save mode
2. 可以開始拉框框標記了 (快捷鍵 W:拉框框， D:下一張， A:上一張)
    ![image](https://github.com/midnightla0710/Yolo_v4/blob/main/teach.PNG)
    每標記完一張圖Annotations 底下都會出現一個xml檔案  #檔名不要有中文


## <使用colab訓練>
1.  使用colab訓練好處：避免Windows+Yolo_v4在呼叫本地端GPU時，可能產生的異常。
2.  [colab訓練方法](https://github.com/midnightla0710/Yolo_v4/blob/main/colab_yolov4.ipynb)
