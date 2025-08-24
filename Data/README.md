# FlowEdit Data

This directory contains all the assets used in FlowEdit numerical evalutions:

- **Images** located in the `Images` subdirectory.
- **Source and target prompts** defined in the `flowedit.yaml` file. 

These images are sourced from the [DIV2K dataset](https://data.vision.ee.ethz.ch/cvl/DIV2K/) and from the Internet, mainly from royality-free websites, including [pexels](https://www.pexels.com/), [pixabay](https://pixabay.com/) and [pxhere](https://pxhere.com/). 

**All images retain the licensing terms of their origimal sources. This dataset is intended for academic use only, and copyright remains with the original owners.**

The `dataset.csv` file provides URLs for most of the images (listed in the same order as they appear in the `Images` subdirectory) and indicates wheter each image was sourced from DIV2K. 

The URLs points to the original images. The images included in the FlowEdit dataset (located in the `Images` subdirectory) were cropped and resized to $$1024 \times 1024$$ pixels. Resizing was perfromed using Pillow [`Image.resize`](https://pillow.readthedocs.io/en/stable/reference/Image.html#PIL.Image.Image.resize) method with its default parameters. 
