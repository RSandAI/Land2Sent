# # Land2Sent
A benchmark for Landsat to Sentinel imageries via deep learning based super-resolution methods.
## Dataset Details
Image pairs of this dataset queried inside Google Earth Engine using the following criteria's: Cloudless images, the year 2023 images, acquisition time less than 1 hour between image pairs, and common area of pairs must be at least 100 km x 100 km. 30 pairs manually selected from these pairs using [Land2Sent GEE application](https://ee-aksoysamett.projects.earthengine.app/view/land2sent). Sentinel images are tiled 480 x 480 pixels and Landsat images are tiled 160 x 160 pixels for super resolution model training. Total of 15066 tiles produced. The dataset splitted %70 training, %20 validation, and %10 testing.

![platform](https://github.com/RSandAI/Land2Sent/blob/main/images/platfrom.jpg)

![tile_examples](https://github.com/RSandAI/Land2Sent/blob/main/images/tile_examples.jpg)

## Benchmark Results
### Metrics
Metric values on normalized 4-band images:
|Method  |PSNR↑	    |SSIM↑	| AG↑	    |NIQE↓	    |PI↓   |
|:------:|:--------:|:-----:|:---------:|:---------:|:----:|
|CAFRN   |35.212 	|0.964 	| 0.00545 	|20.327 	|13.764|
|DCM     |35.468 	|0.967 	| 0.00533 	|20.283 	|13.882|
|FENet   |35.061 	|0.963 	| 0.00531 	|20.214 	|13.829|
|HAUNet  |35.932 	|0.965 	| 0.00567 	|20.317 	|13.736|
|HSENet  |35.588 	|0.963 	| 0.00571 	|20.338 	|13.670|
|MHAN    |35.801 	|0.970 	| 0.00582 	|20.295 	|13.627|
|Omnisr  |35.530 	|0.965 	| 0.00559 	|20.366 	|13.696|
|RCAN    |36.171 	|0.965 	| 0.00614 	|20.305 	|13.487|
|SAN     |35.653 	|0.966 	| 0.00558 	|20.260 	|13.655|
|RDN     |36.636 	|0.972 	| 0.00594 	|20.364 	|13.555|

Metric values on original 16-bit images
|Method  |PSNR↑	    |SSIM↑	| AG↑	    |NIQE↓	    |PI↓   |
|:------:|:--------:|:-----:|:---------:|:---------:|:----:|
|CAFRN	 |50.262 	|0.986 	|0.00082 	|20.605 	|14.155|
|DCM	 |50.388 	|0.987 	|0.00086 	|20.615 	|14.221|
|FENet	 |49.977 	|0.987 	|0.00082 	|20.529 	|14.112|
|HAUNet	 |50.879 	|0.989 	|0.00085 	|20.496 	|14.029|
|HSENet	 |51.748 	|0.991 	|0.00081 	|20.702 	|14.171|
|MHAN	 |51.362 	|0.991 	|0.00085 	|20.765 	|14.195|
|Omnisr	 |50.470 	|0.984 	|0.00083 	|20.551 	|14.171|
|RCAN	 |51.684 	|0.991 	|0.00085 	|20.765 	|14.180|
|SAN	 |50.977 	|0.989 	|0.00084 	|20.705 	|14.183|
|RDN	 |51.877 	|0.991 	|0.00086 	|20.880 	|14.213|

### Visual Results
#### True Color

![TC1](https://github.com/RSandAI/Land2Sent/blob/main/images/TC1.png)

![TC2](https://github.com/RSandAI/Land2Sent/blob/main/images/TC2.png)

![TC3](https://github.com/RSandAI/Land2Sent/blob/main/images/TC3.png)

#### False Color
![FC1](https://github.com/RSandAI/Land2Sent/blob/main/images/FC1.png)

![FC2](https://github.com/RSandAI/Land2Sent/blob/main/images/FC2.png)

![FC3](https://github.com/RSandAI/Land2Sent/blob/main/images/FC3.png)

## Citation

Will be availabe.