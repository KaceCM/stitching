# stitching

A Python package for fast and robust Image Stitching.

Based on opencv's [stitching
module](https://github.com/opencv/opencv/tree/4.x/modules/stitching)
and inspired by the
[stitching_detailed.py](https://github.com/opencv/opencv/blob/4.x/samples/python/stitching_detailed.py)
python command line tool.

![inputs](https://github.com/lukasalexanderweber/stitching_tutorial/blob/master/docs/static_files/inputs.png?raw=true)

![result](https://github.com/lukasalexanderweber/stitching_tutorial/blob/master/docs/static_files/panorama.png?raw=true)

## Installation

Use pip to install stitching from
[PyPI](https://pypi.org/project/stitching/).

```bash
pip install stitching
```

## Usage

The command line interface
([cli](https://github.com/lukasalexanderweber/stitching/tree/main/stitching/cli/stitch.py))
is available after installation

`stitch -h`               show the help

`stitch *`                stitches all files in the current directory

`stitch img_dir/IMG*.jpg` stitches all files in the img_dir directory
starting with "IMG" and ending with ".jpg"

`stitch img1.jpg img2.jpg img3.jpg`
stitches the 3 explicit files of the current directory

Or use the Stitcher class in your script

```python
import stitching

stitcher = stitching.Stitcher()
panorama = stitcher.stitch(["img1.jpg", "img2.jpg", "img3.jpg"])
```

You can also use a single item list with a wildcard

```python
panorama = stitcher.stitch(["img?.jpg"])
```

Specify your custom settings as

```python
settings = {"detector": "sift", "confidence_threshold": 0.2}
stitcher = Stitcher(**settings)
```

## Questions

For questions please use our [discussions](https://github.com/OpenStitching/stitching/discussions).
Please do not use our issue section for questions.

## Contribute

Read through [how to contribute](CONTRIBUTING.md) for information on topics
like finding and fixing bugs and improving / maintaining this package.

## Tutorial

This package provides utility functions to deeply analyse what's
happening behind the stitching. A tutorial was created as [Jupyter
Notebook](https://github.com/lukasalexanderweber/stitching_tutorial). The
preview is
[here](https://github.com/lukasalexanderweber/stitching_tutorial/blob/master/docs/Stitching%20Tutorial.md).

You can e.g. visualize the RANSAC matches between the images or the
seam lines where the images are blended:

![matches1](https://github.com/lukasalexanderweber/stitching_tutorial/blob/master/docs/static_files/matches1.png?raw=true)
![matches2](https://github.com/lukasalexanderweber/stitching_tutorial/blob/master/docs/static_files/matches2.png?raw=true)
![seams1](https://github.com/lukasalexanderweber/stitching_tutorial/blob/master/docs/static_files/seams1.png?raw=true)
![seams2](https://github.com/lukasalexanderweber/stitching_tutorial/blob/master/docs/static_files/seams2.png?raw=true)

## Literature

This package was developed and used for our paper [Automatic stitching
of fragmented construction plans of hydraulic
structures](https://doi.org/10.1002/bate.202200010 "Automatic
stitching of fragmented construction plans of hydraulic structures")

## License

[Apache License
2.0](https://github.com/lukasalexanderweber/lir/blob/main/LICENSE)
