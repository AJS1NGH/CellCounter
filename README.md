# CellCounter
Repository for code that counts number of cells in an image. See description below.

In the image below, we only want to count the outer cell and not the inner smaller cells.
![alt text](https://github.com/AJS1NGH/CellCounter/blob/master/TestImage0075.jpg)

In order to do this, here is the approach I used:
We only want to count the number of cells and not the number of granules.
In order to do this, I used blob detection from the skimage library. If we apply blob detection
on the original image it highlights the outer cell as well as the inner granules. In order to fix
this I blurred the original image 3 times such that the blob detection algorithm treats the granules
in a cell as a cluster of 1 granule. Blob detection detects brighter blobs on a darker background only,
so we need to invert the image after applying a threshold for segmentation such that the cells are
brighter than the background.

The final output looks something like this:
