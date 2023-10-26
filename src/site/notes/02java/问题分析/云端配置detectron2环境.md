---
{"dg-publish":true,"permalink":"/02java//detectron2/","dgPassFrontmatter":true}
---

# 云端配置detectron2环境以及别的环境

## 选择云服务器

我选择这个AutoDL云服务器,

#### 1. 价格

因为这个云服务器感觉相比其他的,价格更便宜,同时GPU的数量也挺多的4090才需要2.6元一个小时,同时这个

3090是1.6 2080Ti才0.9元一个小时

![image-20230806092152055](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308060921092.png)

![image-20230806091936372](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308060919424.png)

![image-20230806092142919](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308060921957.png)

#### 2. 可存储镜像的空间大小

你可以在镜像盘中存储你配置好的环境,下次打开的时候就不用重新进行配置了

免费空间是30个G,超出部分,1G一毛钱,感觉这个价格真的很公道

![image-20230806092357702](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308060923732.png)

#### 3. 数据空间大小

免费空间可以有100个G

![image-20230806092532421](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308060925451.png)

#### 4. 社区镜像丰富

![image-20230806092701078](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308060927107.png)



## 1.选择镜像

1. 在社区镜像中选择这个detectron2镜像

![image-20230806092701078](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308060927107.png)

2. 运行下面的示例代码

## 2. 示例代码

```python
import os
import cv2
from detectron2 import model_zoo
from detectron2.config import get_cfg
from detectron2.data import MetadataCatalog
from detectron2.utils.visualizer import Visualizer
from detectron2.engine import DefaultPredictor

# 加载配置文件和预训练权重
cfg = get_cfg()
cfg.merge_from_file(
    model_zoo.get_config_file("COCO-Detection/faster_rcnn_R_50_FPN_3x.yaml")
)
cfg.MODEL.ROI_HEADS.SCORE_THRESH_TEST = 0.5  # 设置置信度阈值
cfg.MODEL.WEIGHTS = model_zoo.get_checkpoint_url(
    "COCO-Detection/faster_rcnn_R_50_FPN_3x.yaml"
)

# 构建Detector预测器
predictor = DefaultPredictor(cfg)

# 加载要测试的图片
image_path = "2.jpeg"
image = cv2.imread(image_path)

# 进行目标检测
outputs = predictor(image)

# 可视化结果
v = Visualizer(image[:, :, ::-1], MetadataCatalog.get(cfg.DATASETS.TRAIN[0]), scale=1.2)
out = v.draw_instance_predictions(outputs["instances"].to("cpu"))
result_image = out.get_image()[:, :, ::-1]

# 保存目标检测后的结果
save_dir = "image"
os.makedirs(save_dir, exist_ok=True)
save_path = os.path.join(save_dir, "result.jpg")
cv2.imwrite(save_path, result_image)

print("目标检测结果已保存到:", save_path)

```

## 3. 根据代码遇到的错误提示信息进行安装包环境

### 模块错误

`ModuleNotFoundError: No module named 'cv2'`

解决办法

用终端中执行代码

`pip install -i https://pypi.tuna.tsinghua.edu.cn/simple opencv-python`

### 查看自己的cuda版本

`nvcc --version`

参考链接

[查看 CUDA 版本 正确方法（亲测有效）](https://blog.csdn.net/baidu_30506559/article/details/121908428)

### 绝对路径和相对路径错误

尽量把图片放在该项目里面，在项目里面webroot下面新建一个文件夹比如说img，把图片放进去

在引用的时候要用相对路径，不能使用图片在服务器的存储地址，否则会发生只能在服务器上面可见，

外网不可见，使用的时候要用片在该项目下的相对路径，比如在webroot的img文件夹下的1.jpg，

使用的时候要写 img\1.jpg    注意开头的时候不能用\，否则则会默认使用的是绝对路径



web项目下的相对路径：不能以\开头

web项目下的绝对路径：必须用\开头（只会是本地可见，其他人看不到）
————————————————

对这个云服务器中的相对路径和绝对路径我也不是太了解,我于是就参考了下面的这个文章

参考连接
原文链接：https://blog.csdn.net/qq_36080060/article/details/81697962



## 其他环境的配置

其他环境的配置我们其实相比较这个就是换一个镜像，换一个代码，会使用这个云服务器配置环境之后我们就可以很方便的配置环境了