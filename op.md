# 行人检测训练
(1) 下载caltech行人检测数据集的全部tar包和annotation.zip包放到$prj_root/data/caltech/data目录下
(2) 生成Yolo格式数据集
```bash
$ cd $prj_root/data/caltech
$ python trans.py
```
(3) 开始行人检测训练
```bash
$ cd $prj_root
$ python train.py --cfg cfg/ped-2.cfg --data D:/datasets/kitti/yolo/kitti.data --weights weights/yolov3-spp-ultralytics.pt --batch-size=36 --device=0 --resume
$ python train.py --cfg cfg/ped-2.cfg --data D:/datasets/caltech/yolo1/caltech.data --weights weights/yolov3-spp-ultralytics.pt --batch-size=20 --device=1
$ python detect.py --cfg cfg/ped-2.cfg --source D:/datasets/kitti/yolo/images --weights weights/best.pt --names D:/datasets/kitti/yolo/kitti.names
```
