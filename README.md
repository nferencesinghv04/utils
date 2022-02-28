# utils
To pre-process conic dataset, yolo-format and custom anchors


## Configuration changes for small objects:
* set custom  anchor box using [kmeans](https://github.com/nferencesinghv04/utils/blob/d059094cab664466bcd5b6e883d89c6db3bfb4b7/gen_anchors.py)

  * ![alt text](https://github.com/nferencesinghv04/utils/blob/d059094cab664466bcd5b6e883d89c6db3bfb4b7/kmeans.png)
  * ![alt text](https://github.com/nferencesinghv04/utils/blob/d059094cab664466bcd5b6e883d89c6db3bfb4b7/anchors.png)
* set layers and stride for initial layers as feature maps for small objects will be better in initial layers
  * line 717 stride=2 to 4
  * line 720 layers = -1, 36 to -1, 11
* width and height : set network resolution to be 512*512, should be divisible by 32 and larger resolution helps better detection of small objects 
* Change jitter from 0.3 to 0 - it randomly crops and resizes images with changing aspect ratio from x
* Set resize from 1 to 0 :  In case of 1 image size of each iteration will be randomly from 320 to 512. If it is 0, the size of each training is the same as the input size.
