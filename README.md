# coco-eval-free
coco eval by custom category to multi object classification
# modified the 26th line in coco_detection.py
if category is two, then id index is [0,1], as following:

self.cat_ids = [0, 1] ##Custom category index

original line: self.cat_ids = dataset.cat_ids
# modified the 81th line in cocoeval.py
self.params.catIds = [0,1] #sorted(cocoGt.getCatIds())
