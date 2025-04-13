# # Land2Sent
A benchmark for Landsat to Sentinel imageries via deep learning based super-resolution methods.
## Dataset Details
Image pairs of this dataset queried inside Google Earth Engine using the following criteria's: Cloudless images, the year 2023 images, acquisition time less than 1 hour between image pairs, and common area of pairs must be at least 100 km x 100 km. 30 pairs manually selected from these pairs using [Land2Sent GEE application](https://ee-aksoysamett.projects.earthengine.app/view/land2sent). Sentinel images are tiled 480 x 480 pixels and Landsat images are tiled 160 x 160 pixels for super resolution model training. Total of 15066 tiles produced. The dataset splitted %70 training, %20 validation, and %10 testing.

![platform](https://github.com/RSandAI/Land2Sent/blob/main/images/platform.jpg)

![tile_examples](https://github.com/RSandAI/Land2Sent/blob/main/images/tile_examples.png)

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

Correlation of coefficient (R²) values of NDVI
|Data|Image|HR-LR|CAFRN|DCM|FENet|HAUNet|HSENet|MHAN|Omnisr|RCAN|RDM|SAN|
|:--:|:---:|:---:|:---:|:-:|:---:|:----:|:----:|:--:|:----:|:--:|:-:|:-:|
|Normalized|1|0.385|0.700|0.695|0.695|0.711|0.703|0.686|0.709|0.718|0.725|0.689|
|Normalized|2|0.902|0.958|0.958|0.952|0.963|0.962|0.965|0.960|0.968|0.969|0.962|
|Normalized|3|0.799|0.908|0.913|0.907|0.927|0.906|0.910|0.921|0.932|0.928|0.915|
|Normalized|4|0.824|0.945|0.941|0.941|0.950|0.948|0.950|0.949|0.957|0.958|0.946|
|Normalized|5|0.744|0.859|0.863|0.860|0.865|0.866|0.870|0.866|0.844|0.881|0.869|
|16-bit|1|0.385|0.684|0.672|0.679|0.696|0.695|0.680|0.696|0.692|0.696|0.687|
|16-bit|2|0.902|0.953|0.955|0.952|0.953|0.956|0.956|0.948|0.963|0.963|0.957|
|16-bit|3|0.799|0.907|0.902|0.897|0.912|0.908|0.909|0.906|0.914|0.923|0.916|
|16-bit|4|0.824|0.934|0.935|0.936|0.937|0.944|0.948|0.936|0.946|0.951|0.942|
|16-bit|5|0.744|0.852|0.854|0.851|0.843|0.861|0.858|0.856|0.871|0.865|0.846|

RMSE values of NDVI
|Data|Image|HR-LR|CAFRN|DCM|FENet|HAUNet|HSENet|MHAN|Omnisr|RCAN|RDM|SAN|
|:--:|:---:|:---:|:---:|:-:|:---:|:----:|:----:|:--:|:----:|:--:|:-:|:-:|
|Normalized|1|0.083|0.028|0.028|0.028|0.027|0.028|0.029|0.028|0.027|0.027|0.031|
|Normalized|2|0.350|0.067|0.066|0.072|0.063|0.064|0.062|0.065|0.058|0.058|0.069|
|Normalized|3|0.321|0.119|0.118|0.124|0.106|0.121|0.128|0.114|0.094|0.103|0.121|
|Normalized|4|0.381|0.046|0.046|0.046|0.041|0.042|0.041|0.042|0.038|0.038|0.043|
|Normalized|5|0.181|0.063|0.062|0.064|0.059|0.060|0.060|0.061|0.068|0.056|0.062|
|16-bit|1|0.083|0.031|0.032|0.029|0.032|0.028|0.029|0.029|0.031|0.029|0.030|
|16-bit|2|0.350|0.072|0.070|0.071|0.072|0.070|0.075|0.074|0.071|0.071|0.068|
|16-bit|3|0.321|0.119|0.127|0.145|0.129|0.131|0.121|0.125|0.130|0.114|0.111|
|16-bit|4|0.381|0.054|0.061|0.052|0.066|0.043|0.046|0.048|0.043|0.044|0.061|
|16-bit|5|0.181|0.062|0.069|0.064|0.067|0.062|0.062|0.061|0.066|0.059|0.065|

### Visual Results
#### True Color Normalized

![TCN1](https://github.com/RSandAI/Land2Sent/blob/main/images/TCN1.png)

![TCN2](https://github.com/RSandAI/Land2Sent/blob/main/images/TCN2.png)

![TCN3](https://github.com/RSandAI/Land2Sent/blob/main/images/TCN3.png)

![TCN4](https://github.com/RSandAI/Land2Sent/blob/main/images/TCN4.png)

![TCN5](https://github.com/RSandAI/Land2Sent/blob/main/images/TCN5.png)

#### True Color 16-bit

![TC1](https://github.com/RSandAI/Land2Sent/blob/main/images/TC1.png)

![TC2](https://github.com/RSandAI/Land2Sent/blob/main/images/TC2.png)

![TC3](https://github.com/RSandAI/Land2Sent/blob/main/images/TC3.png)

![TC4](https://github.com/RSandAI/Land2Sent/blob/main/images/TC4.png)

![TC5](https://github.com/RSandAI/Land2Sent/blob/main/images/TC5.png)

#### False Color Normalized
![FCN1](https://github.com/RSandAI/Land2Sent/blob/main/images/FCN1.png)

![FCN2](https://github.com/RSandAI/Land2Sent/blob/main/images/FCN2.png)

![FCN3](https://github.com/RSandAI/Land2Sent/blob/main/images/FCN3.png)

![FCN4](https://github.com/RSandAI/Land2Sent/blob/main/images/FCN4.png)

![FCN5](https://github.com/RSandAI/Land2Sent/blob/main/images/FCN5.png)
#### False Color 16-bit

![FC1](https://github.com/RSandAI/Land2Sent/blob/main/images/FC1.png)

![FC2](https://github.com/RSandAI/Land2Sent/blob/main/images/FC2.png)

![FC3](https://github.com/RSandAI/Land2Sent/blob/main/images/FC3.png)

![FC4](https://github.com/RSandAI/Land2Sent/blob/main/images/FC4.png)

![FC5](https://github.com/RSandAI/Land2Sent/blob/main/images/FC5.png)

## Citation

Will be availabe.