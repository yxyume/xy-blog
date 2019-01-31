database collection
=

# general databse collection
## github数据集git
https://github.com/awesomedata/awesome-public-datasets<br>

## kaggle数据集
https://www.kaggle.com/datasets<br>

## 亚马逊数据集
https://registry.opendata.aws<br>

## VisualData	计算机视觉数据集
https://www.visualdata.io/<br>

## UCI 机器学习数据集
https://archive.ics.uci.edu/ml/datasets.html<br>

## 微软数据集搜索引擎
https://msropendata.com/<br>

## 中科院GOT-10k	视频目标检测数据集
http://got-10k.aitestunion.com/downloads<br>


# pro database
## MS_COCO2017
More Info :	 https://blog.csdn.net/daniaokuye/article/details/78699138<br>
http://images.cocodataset.org/zips/train2017.zip<br>
http://images.cocodataset.org/annotations/annotations_trainval2017.zip<br>
http://images.cocodataset.org/zips/val2017.zip<br>
http://images.cocodataset.org/annotations/stuff_annotations_trainval2017.zip<br>
http://images.cocodataset.org/zips/test2017.zip<br>
http://images.cocodataset.org/annotations/image_info_test2017.zip<br>

MS_COCO2017 API：https://github.com/cocodataset/cocoapi<br>
```
# a demo of COCO2017 API
# signal person photo in MSCOCO
def load_data(self, dataDir, dataType, annType):
    annFile = '{}annotations/{}_{}.json'.format(dataDir, annType, dataType)
    self.coco = COCO(annFile)
    catID = self.coco.getCatIds(catNms=['person'])
    imgID = self.coco.getImgIds(catIds=catID)
    if self.signle:
        self.ids = []
        for id in imgID:
            img = self.coco.loadImgs(id)[0]
            annID = self.coco.getAnnIds(imgIds=img['id'])
            anns = self.coco.loadAnns(annID)
            if len(anns) == 1:
                self.ids.append(id)
    else:
        self.ids = imgID
        # print('ok')
```

        
        
        
