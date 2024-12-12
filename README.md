# SSD-based Object Detection in PyTorch

This repo implements [SSD (Single Shot MultiBox Detector)](https://arxiv.org/abs/1512.02325) in PyTorch for object detection, using MobileNet backbones.  It also has out-of-box support for retraining on Google Open Images dataset.  

> For documentation, please refer to Object Detection portion of the **[Hello AI World](https://github.com/dusty-nv/jetson-inference/tree/dev#training)** tutorial:
> [Re-training SSD-Mobilenet](https://github.com/dusty-nv/jetson-inference/blob/dev/docs/pytorch-ssd.md)

Thanks to @qfgaohao for the upstream implementation from:  [https://github.com/qfgaohao/pytorch-ssd](https://github.com/qfgaohao/pytorch-ssd)

## Notes

Needed to upgrade `pandas`.

```
$ pip install --upgrade numpy pandas
```

Needed to change the image downloader script by replacing `iteritems` with `items`.

```
Traceback (most recent call last):
  File "open_images_downloader.py", line 183, in <module>
    log_counts(annotations[dataset_type]['ClassName'])
  File "open_images_downloader.py", line 81, in log_counts
    for k, count in values.value_counts().iteritems():
  File "/home/user/.local/lib/python3.8/site-packages/pandas/core/generic.py", line 5989, in __getattr__
    return object.__getattribute__(self, name)
AttributeError: 'Series' object has no attribute 'iteritems'
```

These changes are included in this commit.


