# Darknet 测试

> Darknet深度学习框架是由Joseph Redmon提出的一个用C和CUDA编写的开源神经网络框架。它安装速度快，易于安装，并支持CPU和GPU计算。

1. 首先执行 `sh data-install.sh`进行测试数据的下载
2. 然后执行`node index.js` 进行检查结果

## 环境要求
* Linux, Mac, Windows (Linux sub-system),
* Node (most versions will work, darknet.js <=1.1.5 only works on node <=8.11.2)
* Build tools (make, gcc, etc.)

## 输出信息如下

```shell
tester@tester:/opt/aa/darknet-test$ node index.js 
layer     filters    size              input                output
    0 conv     16  3 x 3 / 1   416 x 416 x   3   ->   416 x 416 x  16  0.150 BFLOPs
    1 max          2 x 2 / 2   416 x 416 x  16   ->   208 x 208 x  16
    2 conv     32  3 x 3 / 1   208 x 208 x  16   ->   208 x 208 x  32  0.399 BFLOPs
    3 max          2 x 2 / 2   208 x 208 x  32   ->   104 x 104 x  32
    4 conv     64  3 x 3 / 1   104 x 104 x  32   ->   104 x 104 x  64  0.399 BFLOPs
    5 max          2 x 2 / 2   104 x 104 x  64   ->    52 x  52 x  64
    6 conv    128  3 x 3 / 1    52 x  52 x  64   ->    52 x  52 x 128  0.399 BFLOPs
    7 max          2 x 2 / 2    52 x  52 x 128   ->    26 x  26 x 128
    8 conv    256  3 x 3 / 1    26 x  26 x 128   ->    26 x  26 x 256  0.399 BFLOPs
    9 max          2 x 2 / 2    26 x  26 x 256   ->    13 x  13 x 256
   10 conv    512  3 x 3 / 1    13 x  13 x 256   ->    13 x  13 x 512  0.399 BFLOPs
   11 max          2 x 2 / 1    13 x  13 x 512   ->    13 x  13 x 512
   12 conv   1024  3 x 3 / 1    13 x  13 x 512   ->    13 x  13 x1024  1.595 BFLOPs
   13 conv    256  1 x 1 / 1    13 x  13 x1024   ->    13 x  13 x 256  0.089 BFLOPs
   14 conv    512  3 x 3 / 1    13 x  13 x 256   ->    13 x  13 x 512  0.399 BFLOPs
   15 conv    255  1 x 1 / 1    13 x  13 x 512   ->    13 x  13 x 255  0.044 BFLOPs
   16 yolo
   17 route  13
   18 conv    128  1 x 1 / 1    13 x  13 x 256   ->    13 x  13 x 128  0.011 BFLOPs
   19 upsample            2x    13 x  13 x 128   ->    26 x  26 x 128
   20 route  19 8
   21 conv    256  3 x 3 / 1    26 x  26 x 384   ->    26 x  26 x 256  1.196 BFLOPs
   22 conv    255  1 x 1 / 1    26 x  26 x 256   ->    26 x  26 x 255  0.088 BFLOPs
   23 yolo
Loading weights from yolov3-tiny.weights...Done!
Dog: [ { name: 'car',
    prob: 0.6152912378311157,
    box: 
     { x: 572.1994018554688,
       y: 120.48184204101562,
       w: 214.3546600341797,
       h: 98.72494506835938 } },
  { name: 'car',
    prob: 0.517267107963562,
    box: 
     { x: 577.43359375,
       y: 126.0497817993164,
       w: 88.42097473144531,
       h: 62.76274108886719 } },
  { name: 'truck',
    prob: 0.5578269958496094,
    box: 
     { x: 577.43359375,
       y: 126.0497817993164,
       w: 88.42097473144531,
       h: 62.76274108886719 } },
  { name: 'bicycle',
    prob: 0.5850223302841187,
    box: 
     { x: 390.94427490234375,
       y: 300.541259765625,
       w: 369.40216064453125,
       h: 299.3248291015625 } },
  { name: 'dog',
    prob: 0.5707316994667053,
    box: 
     { x: 249.094970703125,
       y: 352.12335205078125,
       w: 239.8490753173828,
       h: 330.763671875 } } ]
Eagle: [ { name: 'bird',
    prob: 0.7649939656257629,
    box: 
     { x: 379.6971130371094,
       y: 260.68951416015625,
       w: 486.4349365234375,
       h: 322.6314392089844 } } ]
Giraffe: [ { name: 'zebra',
    prob: 0.5318787097930908,
    box: 
     { x: 359.7569885253906,
       y: 326.3610534667969,
       w: 109.50553894042969,
       h: 242.93246459960938 } },
  { name: 'giraffe',
    prob: 0.528597891330719,
    box: 
     { x: 296.3047180175781,
       y: 210.2434844970703,
       w: 285.6275329589844,
       h: 504.72705078125 } } ]

```