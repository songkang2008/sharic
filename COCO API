from pycocotools.coco import COCO
import matplotlib.pyplot as plt
import cv2
# first import the json file
coco = COCO('./annotations/instances_train2017.json')
# get the img_Ids
img_ids = coco.getImgIds()
for i, id in enumerate(img_ids):
    print("i", i)
    # get the img_info dict
    img_info = coco.loadImgs(id)[0]
    # get img path
    img_path = "F:\DeepLearning/tools/coco\images/train2017/train2017/"+ img_info['file_name']
    print('img_path', img_path)
    img = cv2.imread(img_path)
    img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    print(img)
    ann_ids = coco.getAnnIds(id)
    print(ann_ids)
    for ann_id in ann_ids:
       ann = coco.loadAnns(ann_id)[0]
       x, y, width, height = ann['bbox']  # x, y Bottom left coordinate
       # print(x, y, width, height)
       cv2.rectangle(img, (int(x), int(y)), (int(x+width), int(y+height)), (0, 0, 255), 2)
       plt.imshow(img)
       plt.show()
    # only show the four
    if i==3:
        break
