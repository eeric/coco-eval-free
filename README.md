# coco-eval-free
coco eval by custom category to multi object classification
if category is two, then id index is [0,1], as following:
## modified two lines in coco.py
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
