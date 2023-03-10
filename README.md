# Bit Depth Enhancement <a name="headin"></a>

This repository is mainly used to track the dynamics related to bit depth enhancement, including mainstream data sets, algorithms for bit enhancement in image or video fields, and open source code. Promote the development of Ultra HD images or videos such as HDR by investigating bit depth enhancement algorithms. This repository will be continuously updated！

> :pencil2:**Authors:**
> [Jing Liu](https://github.com/TJUMMG), [Jiaxiang Wang](https://github.com/DumbFox123), [Zhiwei Fan](https://github.com/FanDady).

## :bookmark:Contents
- **[Bit Depth Enhancement <a name="headin"></a>](#bit-deep-enhancement-)**	
	- **[Contents](#contents)**	
	- **[Introduction](#introduction)**
	- **[Datasets](#datasets)**
	- **[Papers and Codes](#papers-and-codes)**
		- **[Image Domain](#image-domain)**
		- **[Video Domain](#video-domian)**

## :blue_book:Introduction

With the development of digital signal visualization technology, the demands for high resolution and bit-depth monitors have been raised for their enjoyable visual experience. However, since the HBD image acquisition technology has only gained popularity in recent years, most existing images and video contents are of low bit-depth. When these LBD images are viewed on higher bit-depth monitors directly, pixel values are usually de-quantized with simple algorithms like Zero Padding (ZP). It is highly likely to result in severe false contouring artifacts in smooth gradient areas as well as chroma distortions in high illumination regions , degrading the image visual quality. The false contour artifacts and chroma distortions are illustrated as Figure. 1 . The 16-bit image is quantized to 4-bit and de-quantized with ZP algorithm to display as the left sub-image. Compared with the raw HBD sub-image, some false contours appear on the reconstructed sub-image and the colors are less bright than the right sub-image, especially when the pixels have high illumination. Therefore, designing an effective bit-depth enhancement algorithm is of significant value.


<p align="center">
    <a href="https://imgse.com/i/ppnlCTK"><img src="https://s1.ax1x.com/2023/03/09/ppnlCTK.png" alt="ppnlCTK.png" border="0" /></a>
    <em> 
    Figure 1: Illustration of false contour artifacts and chroma distortions.
    </em>
</p>




## :file_folder: Datasets

The design and verification of the bit depth enhancement algorithm cannot be separated from the high-order deep content database. At present, the commonly used high-order deep image and video data sets at home and abroad include Sintel data set, MIT-Adobe 5K data set, TESTIMAGES data set, FuntHDR data set, SJTU HDR, Tears of Steel data set, and SVT data set.
|**Year**|**Dataset**|**Resolution**|**High Bit**|**Low Bit**|**Frame rate**|**Download Link**|**Description**|
| :-: | :-: | :-: | :-: |:-: | :-: | :-: | :- |
|2012|**Sintel**|1K,2K,4K|16|8|24|[Link](http://sintel.is.tue.mpg.de/downloads)|Computer-synthesized animated film with fine and smooth content texture, including various animals and plants, buildings, natural scenes and extreme light and dark conditions|
|2011|**MIT-Adobe5K**|-|16|-|-|[Link](https://data.csail.mit.edu/graphics/fivek/)|The natural image sets taken by different photographers with different brands of cameras cover a variety of natural scenes such as people, animals and plants, buildings, etc., including a variety of different lighting conditions and resolutions. The HDR image with professional color adjustment is saved in the original format of the camera.|
|2014|**TESTIMAGES**|100×100至2400×2400|16|8|-|[Link](https://sourceforge.net/projects/testimages/files/)|Used for analysis and quality evaluation of display equipment or image processing technology, including 40 actual natural images, and 8 bit images are generated from 16 bit images through brightness normalization.|
|2010|**Funt HDR**|2142×2142|16|-|-|[Link](https://www2.cs.sfu.ca/~colour/data/funt_hdr/#DESCRIPTION)|The 105 scenes taken with the NikonD700 digital still life camera contain 9 different exposure values for each scene. Including raw data format and 16bit PNG format, HDR image is generated through MATLAB image processing toolbox.|
|2016|**SHTU HDR**|4K|16|-|60|[Link](https://medialab.sjtu.edu.cn/post/16-01-01-sjtu-hdr-video-sequences/)|16 ultra-high definition HDR video sets captured by Sony F65 and F55 cameras|
|2013|**Tears of Steel**|2K,4K|16|8|24|[Link](https://mango.blender.org/download/)|A movie sequence mixed with natural scenes and computer synthesis.|
|2014|**SVT**|4K|16|-|50|[Link](https://tc11.cvc.uab.es/datasets/SVT_1)|4K test clip released by Video Quality Expert Group (VQEG).|

In addition to the high bit depth database mentioned above, the traditional 8bit image database can also be used to verify the effectiveness of the bit depth enhancement algorithm due to its rich content and more consistent with early degradation. The classic 8bit database mainly includes Kodak, DPED, ADE20K, OST300, etc.

|**Year**|**Dataset**|**Number**|**Download Link**|**Description**|
| :-: | :-: | :-: | :-: | :- |
|1999|**Kodak**|24|[Link](https://r0k.us/graphics/kodak/)|Classic lossless true color image database, released by Eastman Kodak|
|2017|**DPED**|16K|[Link](https://people.ee.ethz.ch/~ihnatova/)|It is composed of three smart phones and a digital SLR camera synchronously taking pictures in the field. Each picture taken by the smart camera has corresponding different and complex degraded pictures|
|2019|**ADE20K**|25M|[Link](https://groups.csail.mit.edu/vision/datasets/ADE20K/)|Real complex scene images (such as roads, trees, etc.) collected from multiple early data sets were initially used for scene perception and semantic understanding. It can also be used for enhancement tasks facing real scenes due to various degradation such as shooting and reading noise, network transmission compression loss, etc|
|2018|**OST300**|10K|[Link](http://mmlab.ie.cuhk.edu.hk/projects/SFTGAN/)|The real outdoor scene data set collected by keyword retrieval contains rich texture details, as well as various compression losses and shooting and reading noise, which is used to verify the image enhancement model for semantic texture|


## :computer:Papers and Codes

- ### :camera:Image Domain

   - [IFTC 2017]:boom: **Bit-Depth Enhancement via Convolutional Neural Network.** &nbsp; *Jing Liu* , BE-CNN.\
   [[Website](https://link.springer.com/chapter/10.1007/978-981-10-8108-8_24)] [[Code](https://github.com/TJUMMG/BE-CNN)] 
   - [ACCV 2018]:boom: **BitNet: Learning-Based Bit-Depth Expansion.** &nbsp; *Junyoung Byun* , BitNet.\
   [[Website](https://link.springer.com/chapter/10.1007/978-3-030-20890-5_5)] [[Code](https://github.com/kamkyu94/BitNet)] 
   - [ACCV 2018]:boom: **Gradient-Guided DCNN for Inverse Halftoning and Image Expanding.** &nbsp; *Yi Xiao* , GG-DCNN.\
   [[Website](https://link.springer.com/chapter/10.1007/978-3-030-20870-7_13)]
   - [ACCV 2018]:boom: **BE-CALF: Bit-Depth Enhancement by Concatenating All Level Features of DNN.** &nbsp; *Jing Liu* , BE-CALF.\
   [[Website](https://ieeexplore.ieee.org/document/8713480)] [[Code](https://github.com/TJUMMG/BE-CALF)] 
   - [Neucom 2019]:boom: **Photo-realistic image bit-depth enhancement via residual transposed convolutional neural network.** &nbsp; *Yuting Su* , RT-CNN.\
   [[Website](https://www.sciencedirect.com/science/article/pii/S0925231219305272)] 
   - [TIP 2019]:boom: **Deep reconstruction of least significant bits for bit-depth expansion.** &nbsp; *Yang Zhao* , BDEN.\
   [[Website](https://ieeexplore.ieee.org/document/8603810)] 
   - [TCSVT 2020]:boom: **Lighter but efficient bit-depth expansion network.** &nbsp; *Yang Zhao* , LBDE.\
   [[Website](https://ieeexplore.ieee.org/document/9044324)] 
   - [Arxiv 2020]:boom: **Deep attentive generative adversarial network for photo-realistic image de-quantization.** &nbsp; *Yang Zhang* , DAGAN.\
   [[Website](https://arxiv.org/ftp/arxiv/papers/2004/2004.03150.pdf)] 
   - [TCSVT 2021]:boom: **Residual-Guided Multiscale Fusion Network for Bit-Depth Enhancement.** &nbsp; *Jing Liu* , RMFNet.\
   [[Website](https://ieeexplore.ieee.org/document/9491068)] [[Code](https://github.com/TJUMMG/RMFNet)] 
   - [Displays 2021]:boom: **Photo-realistic residual bit-depth enhancement by advanced conditional GAN.** &nbsp; *Jing Liu* , BE-ACGAN.\
   [[Website](https://www.sciencedirect.com/science/article/pii/S0141938221000512)] [[Code](https://github.com/TJUMMG/BE-ACGAN)] 
   - [TPAMI 2021] :boom: **A Little Bit More: Bitplane-Wise Bit-Depth Recovery.** &nbsp; *Abhijith Punnappurath* , ALBM.\
   [[Website](https://blog.alexalemi.com/diffusion.html)] [[Code](https://colab.research.google.com/github/google-research/vdm/blob/main/colab/SimpleDiffusionColab.ipynb)] 
   - [SPL 2022] :boom: **Iterative Residual Feature Refinement Network for Bit-Depth Enhancement.** &nbsp; *Jing Liu* , IRFRN.\
   [[Website](https://ieeexplore.ieee.org/abstract/document/9787714)] [[Code](https://github.com/TJUMMG/IRFRN)]    
   - [Arxiv 2022] :boom: **Learning Weighting Map for Bit-Depth Expansion within a Rational Range.** &nbsp; *Yuqing Liu* , BRNet.\
   [[Website](https://arxiv.org/abs/2204.12039)] [[Code](https://github.com/yuqing-liu-dut/bit-depth-expansion)] 


- ### :movie_camera:Video Domian

   - [TMM 2019]:boom: **Spatiotemporal symmetric convolutional neural network for video bit-depth enhancement.** &nbsp; *Jing Liu* , SSCNN\
[[Website](https://ieeexplore.ieee.org/document/8636159)] 

   - [TMM 2021]:boom: **Tanet: Target attention network for video bit-depth enhancement.** &nbsp; *Jing Liu* , TANet.\
[[Website](https://ieeexplore.ieee.org/abstract/document/9547837)] [[Code](https://colab.research.google.com/github/google-research/vdm/blob/main/colab/SimpleDiffusionColab.ipynb)] 

   - [BMSB 2021]:boom: **3D-BitNet: Flow-agnostic and precise network for video bit-depth expansion.** &nbsp; *Geyingjie Wen* , 3D-BitNet.\
[[Website](https://ieeexplore.ieee.org/document/9547086)]

   - [MMSP 2022] :boom: **Bit-depth enhancement detection for compressed video.** &nbsp; *Nickolay Safonov*, BEDCV.\
[[Website](https://arxiv.org/abs/2211.04799v1)] [[Code](https://colab.research.google.com/github/google-research/vdm/blob/main/colab/SimpleDiffusionColab.ipynb)] 

---

# :mailbox_with_no_mail: Contact

 Jing Liu (jliu_tju@tju.edu.cn).

[⬆ back to top](#headin)
