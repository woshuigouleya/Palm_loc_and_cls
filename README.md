# 手掌定位与分类
## 手掌定位
使用resnet18作为backbone,输入为在原图上关键点所在矩形框padding 100px之后crop 并resize到192的图

## 代码说明
训练代码：./train_net/my_train.py(数据读取也在这里)
测试代码：test_image.py

## 手掌分类
在classification中

### 如何确定标签

1. 首先确定一个覆盖所有类别的字典
2. 然后根据不需要的类别(这个得与数据集匹配)筛选出需要的字典，并且按照顺序排序，确定每个类别的标签

---
举个例子：
在大类分类中，所有类别为 1,2,3……9
但是我不需要2 6 9 这三个类别(只需要1,3,4,5,7,8),所以经过匹配后的字典为：  

{  
    "1": 1,  
    "3": 2,  
    "4": 3,  
    "5": 4,  
    "7": 5,  
    "8": 6       
}




![avatar](./myplot.png)

![avatar](./myplot1.png)