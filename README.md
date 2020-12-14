# coco-eval-free and training with custom category 
## supporting Nanodet projects
https://github.com/RangiLyu/nanodet/blob/main/nanodet/evaluator/coco_detection.py

coco eval by custom category to multi object classification

if category is two, then id index is [0,1], as following:
## modified two lines in nanodet/data/dataset/coco.py to training on line, while not change to label
117th line added

    # 2 classes label
        
    lablist=ann['labels']
        
    twolist=np.array([1 if i !=0 else i for i in lablist])
        
126th line modified

    gt_labels=twolist
        
original line: gt_labels=ann['labels']
## modified the 26th line in coco_detection.py
self.cat_ids = [0, 1] ##Custom category index

original line: self.cat_ids = dataset.cat_ids
## modified the 81th line in cocoeval.py
self.params.catIds = [0,1] #sorted(cocoGt.getCatIds())

original line: self.params.catIds = sorted(cocoGt.getCatIds())

## find cocoeval.py
    user@server:~/your path/nanodet$ python3
    >>> import pycocotools.cocoeval
    >>> pycocotools.__file__
    '/your path/python3.6/site-packages/pycocotools/'
## config
    num_classes: 2
    class_names: ['person', 'nonhuman']
## If I can help you, please give me a star :star2::star2::star2:
my csdn: https://blog.csdn.net/yyqq7226741/article/details/110918317
