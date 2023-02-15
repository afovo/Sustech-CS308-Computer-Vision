# Lecture Note

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104101155763.png" alt="image-20230104101155763" style="zoom:25%;" /><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213162715184.png" alt="image-20221213162715184" style="zoom: 33%;" />



## 1. Introduction 

- The first **digital** image was produced in 1920

- Charge-coupled device(CCD)

- Larry Roberts at MIT(1960): extracting 3D geometrical information from 2D perspective views of blocks

​        <u>Father of computer vision</u> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213162927511.png" alt="image-20221213162927511" style="zoom:33%;" /> 

| **Applications**                |                                                              |
| ------------------------------- | ------------------------------------------------------------ |
| Image classification            | Building a model (function) from hypothesis space  Image to label  Matrix to number |
| Object detection                | Input: image  Output: locations of objects                   |
| Image segmentation              | Input: image   Output: regions, structures                   |
| Pose estimation                 | Input: image   Output: configuration                         |
| Image captioning                | generating textual description of an image                   |
| Visual Question Answering (VQA) | • Given an image and a question (text) about the image  Aim to provide an accurate natural language answ |
| Image generation                |                                                              |
| Object tracking                 | Input: video  Output: trajectory                            |
| Object re-identification        | Input: images (multi-camera)   Output: associations          |

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213163014438.png" alt="image-20221213163014438" style="zoom:50%;" /> 



<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20220928141548493.png" alt="image-20220928141548493" style="zoom: 50%;" /> 



## 2. Image formation

formation process: 3D (real-world) to 2D (matrix)

(a) Perspective projection

(b) Light scattering when hitting a surface

(c) Lens optics

(d) Bayer color filter array



###  2.1 Geometric primitives and transformations (几何图元和变换)

(Vanishing points and vanishing lines)

**2D points, lines**     

**3D points, lines, plane**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213164703253.png" alt="image-20221213164703253" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213164742166.png" alt="image-20221213164742166" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213164804070.png" alt="image-20221213164804070" style="zoom:50%;" /> 





### 2.2 Projections

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213165521871.png" alt="image-20221213165521871" style="zoom:50%;" />  

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213165632247.png" alt="image-20221213165632247" style="zoom:50%;" /> 



**Pinhole camera model**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213165020381.png" alt="image-20221213165020381" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213165138687.png" alt="image-20221213165138687" style="zoom:50%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213165214580.png" alt="image-20221213165214580" style="zoom:25%;" /> 





**Camera projection matrix**

 <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213165931953.png" alt="image-20221213165931953" style="zoom:50%;" />







<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170106805.png" alt="image-20221213170106805" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170143829.png" alt="image-20221213170143829" style="zoom:50%;" /> 





<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170216304.png" alt="image-20221213170216304" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170242288.png" alt="image-20221213170242288" style="zoom:50%;" /> 

 <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170311819.png" alt="image-20221213170311819" style="zoom:50%;" />

.......

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170402448.png" alt="image-20221213170402448" style="zoom:50%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170431779.png" alt="image-20221213170431779" style="zoom:50%;" />

### 2.3 Photometric image formation

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170520128.png" alt="image-20221213170520128" style="zoom:50%;" />  



### 2.4 The digital camera

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170554466.png" alt="image-20221213170554466" style="zoom:50%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170638859.png" alt="image-20221213170638859" style="zoom:50%;" />

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221213170751036.png" alt="image-20221213170751036" style="zoom:50%;" /> 





## 3. Image processing

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230114637066.png" alt="image-20221230114637066" style="zoom:50%;" /> 

### 3.1 Point Operation

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230114827089.png" alt="image-20221230114827089" style="zoom:50%;" /> 

• Brightening a picture by adding a constant value to all three channels==>increases the apparent intensity of each pixel, affect the pixel’s hue and saturation.

Some color ratio images multiplied by the middle gray value for better visualization



#### Compositing and Matting

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230115547245.png" alt="image-20221230115547245" style="zoom:50%;" />  



#### **Histogram equalization**

• A technique for adjusting image **intensities** to enhance **contrast**

 find an intensity mapping function *f(I)* such that the resulting histogram is flat.

 An image would have a linearized cumulative distribution function (CDF)

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20220928154618800.png" alt="image-20220928154618800" style="zoom:67%;" /> 

normalization

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221009164754198.png" alt="image-20221009164754198" style="zoom:50%;" /> 

standardization

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221009164840696.png" alt="image-20221009164840696" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230161427507.png" alt="image-20221230161427507" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230121030265.png" alt="image-20221230121030265" style="zoom:50%;" /> 

| e.g.<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230120337342.png" alt="image-20221230120337342" style="zoom:50%;" /> |
| ------------------------------------------------------------ |
| <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230120352916.png" alt="image-20221230120352916" style="zoom:50%;" /> 像素总个数：25 |
| <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230120449537.png" alt="image-20221230120449537" style="zoom:50%;" /> |
| <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230120507864.png" alt="image-20221230120507864" style="zoom:50%;" /> |
| <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230120556343.png" alt="image-20221230120556343" style="zoom:50%;" /> |
| <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230120833434.png" alt="image-20221230120833434" style="zoom:50%;" /> |

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230121000449.png" alt="image-20221230121000449" style="zoom:50%;" /> 





### 3.2 Linear filtering

The most commonly used type of <u>neighborhood operator</u> is a *linear filter*

#### **Linear shift-invariant (LSI) operators**

correlation operator: *g* = *f* *⊗* *h.* 

convolution operator: *g* = *f* **h* (中心对称)

[h: kernel]

**Padding**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230162318684.png" alt="image-20221230162318684" style="zoom:50%;" />  ***padding=kernel//2***

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230162559445.png" alt="image-20221230162559445" style="zoom:50%;" /> 

#### **Separable Filtering**

A convolution kernel whose operation can be significantly sped up by first performing a one-dimensional horizontal convolution followed by a one-dimensional vertical convolution(which requires a total of 2K operations per pixel)

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20220928142711563.png" alt="image-20220928142711563" style="zoom:50%;" /> 

#### Band-pass and Steerable Filtering

| Band-Pass  带通滤波器                                        | Steerable Filtering                                          |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Sobel and corner operators are simple examples of band-pass and oriented fifilters | Sobel operator is a simple approximation to a *directional* or *oriented* filter |
| ***Gaussian*** Smoothing +***Laplacian* operator**:[(undirected) second derivative of a two-dimensional image] = *Laplacian of Gaussian* (**LoG**) filter<br>![image-20220928142955599](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20220928142955599.png)<br><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20220928143051733.png" alt="image-20220928143051733" style="zoom:80%;" /> | ***Gaussian*** Smoothing + ***directional derivative***      |
| nice *scale-space properties*                                | construct both feature descriptors (Section 4.1.3) and edge detectors |

#### **Summed area table (integral image)**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103150044902.png" alt="image-20230103150044902" style="zoom:33%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230164606441.png" alt="image-20221230164606441" style="zoom:50%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230164643942.png" alt="image-20221230164643942" style="zoom:45%;" />

### 3.3 More neighborhood operators

| Median Filtering                                             | Bilateral Filtering                                          | Morphology                                                   | **Distance transforms**                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Select the median from neighborhood（Filter away shot noise, not as efficient at averaging away regular Gaussian noise） | It replaces the intensity of each pixel with a weighted average of intensity values from nearby pixels(can be based on a Gaussian distribution). | <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230165259272.png" alt="image-20221230165259272" style="zoom: 200%;" /> | <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230165632757.png" alt="image-20221230165632757" style="zoom:200%;" /> |
| *α-trimmed mean* (averages together all of the pixels except for the *α* fraction that are the smallest and the largest) | non-linear, edge-preserving                                  |                                                              | Connected Components![image-20221230165723866](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230165723866.png) |
| *weighted median* (each pixel is used a number of times depending on its distance from the center. This turns out to be equivalent to minimizing the weighted objective function) | ![image-20221230165107118](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230165107118.png) |                                                              |                                                              |

**e.g.**![image-20221230170806311](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230170806311.png) 





### 3.4 Thinking in Frequency

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230174141970.png" alt="image-20221230174141970" style="zoom:30%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230174312115.png" alt="image-20221230174312115" style="zoom:40%;" />

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230174347937.png" alt="image-20221230174347937" style="zoom: 33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230174551827.png" alt="image-20221230174551827" style="zoom: 33%;" />



### 3.5 Pyramids

**interpolation**

Select some interpolation kernels to convolve the image

**decimation**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230175303460.png" alt="image-20221230175303460" style="zoom:50%;" /> 

multi-resolution

**image blending**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230175339473.png" alt="image-20221230175339473" style="zoom:50%;" /> 

### **3.6 Geometric transformations**

**Parametric transforms**

forward Warp

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230175525524.png" alt="image-20221230175525524" style="zoom:50%;" /> 

inverseWarp

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230175511182.png" alt="image-20221230175511182" style="zoom:50%;" /> 

**Mesh-based warping**





## 4. **Feature detection and matching**

keyPoints: Repeatability, Saliency, Compactness and efficiency, Locality

| Point detection                                              | Point decriptor                                              | Point Matching                                               |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Harris Corner detection**<br>[Precise localization in x-y]<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221012154303703.png" alt="image-20221012154303703" style="zoom: 33%;" /><br>Denote the change around E(u,v) [E(0,0)=0 denoting identity]<br><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221012155143696.png" alt="image-20221012155143696" style="zoom:33%;" /><br><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230180432223.png" alt="image-20221230180432223" style="zoom: 50%;" /> | **SIFT**<br/>Histogram of Oriented Gradients<br/><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230201819854.png" alt="image-20221230201819854" style="zoom:50%;" /> | nearest neighbor<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230203222707.png" alt="image-20221230203222707" style="zoom:80%;" /> |
| **Difference-of-Gaussian**<br>[Good localization in scale]<br>(DoG)+rejection <br><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230201923913.png" alt="image-20221230201923913" style="zoom:50%;" /><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230201527989.png" alt="image-20221230201527989" style="zoom:50%;" /> | • 8 orientations x 4x4 array = 128 dimensions![image-20221230202306207](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230202306207.png) |                                                              |
| **Affifine invariance**                                      |                                                              |                                                              |

***image representation:**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20221230201745222.png" alt="image-20221230201745222" style="zoom:50%;" /> 

## 5. Fitting

*Building a Model for a Set of Features*

 Noise

 Extraneous data: clutter (outliers), multiple lines

 Missing data: occlusions



• If we know which points belong to the line, how do we find the “optimal” line parameters?

​	 Least squares

• What if there are outliers? 

​	 Robust fitting, RANSAC

• What if there are many lines? 

​	 Voting methods: RANSAC, Hough transform

• What if we’re not even sure it’s a line?

​	 Model selection



### 5.1 Least Squares 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101183718212.png" alt="image-20230101183718212" style="zoom:67%;" /> 

 <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104120738984.png" alt="image-20230104120738984" style="zoom:33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104120855071.png" alt="image-20230104120855071" style="zoom: 33%;" />



#### Total Least Squares

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101184023125.png" alt="image-20230101184023125" style="zoom:25%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101184108175.png" alt="image-20230101184108175" style="zoom:30%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101184204991.png" alt="image-20230101184204991" style="zoom: 33%;" /> 

**Robust Estimators**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101193820316.png" alt="image-20230101193820316" style="zoom: 33%;" />!

 

### 5.2 RANSAC

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101193932695.png" alt="image-20230101193932695" style="zoom:50%;" /> 

| s          | t                                                            | d                                                            | N                                                            |
| ---------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| minimum: 2 | <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101194158031.png" alt="image-20230101194158031" style="zoom:50%;" /> | <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101194239813.png" alt="image-20230101194239813" style="zoom:50%;" /> | <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101194219234.png" alt="image-20230101194219234" style="zoom:50%;" /> |

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101194318816.png" alt="image-20230101194318816" style="zoom: 33%;" /> 



### 5.3 Hough Voting

| Line                                                         | Circle                                                       | Generalized                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Cartesion<br><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101195650505.png" alt="image-20230101195650505" style="zoom:50%;" /><br>![image-20230101195707810](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101195707810.png) | Known radius:<Br>2D Hough Space                              | <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101200009112.png" alt="image-20230101200009112"/><br>voting for each edge point p by r(θ) |
| Polar<br><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101195629623.png" alt="image-20230101195629623" style="zoom:50%;" /> | Unknown radius:<br>3D Hough Space<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101195830284.png" alt="image-20230101195830284" style="zoom:50%;" /> |                                                              |



### 5.4 Image Alignment

*fitting a model to a transformation between pairs of features (matches) in two images[previosly, one image]*

Direct (pixel-based) alignment

Feature-based alignment

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101200614991.png" alt="image-20230101200614991" style="zoom:33%;" /> 





## 6. Machine Learning

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230101205441200.png" alt="image-20230101205441200" style="zoom:33%;" /> 

#### 6.1 Dimensionality Reduction

##### Linear

###### PCA

Find projections that capture the largest amounts of variation in data 

Find the eigenvectors of the covariance matrix, and these eigenvectors define the new space

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103114444564.png" alt="image-20230103114444564" style="zoom:33%;" /> 

| one dim                                                      | two dim                                                      | three dim                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103114722721.png" alt="image-20230103114722721"  /> | ![image-20230103114840369](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103114840369.png) | ![image-20230103114910814](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103114910814.png) |

![image-20230103144108645](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103144108645.png)

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103120354675.png" alt="image-20230103120354675" style="zoom:53%;" />







<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103142044248.png" alt="image-20230103142044248" style="zoom:50%;" />   



<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103115629421.png" alt="image-20230103115629421" style="zoom:23%;" /><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103115748350.png" alt="image-20230103115748350" style="zoom:23%;" /> 



 









**Kernel**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103115306985.png" alt="image-20230103115306985" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103120728260.png" alt="image-20230103120728260" style="zoom:33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103120747571.png" alt="image-20230103120747571" style="zoom:33%;" />









###### MDS

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103142300055.png" alt="image-20230103142300055" style="zoom:50%;" /> 



##### Nonlinear(Manifold Learning)

###### LLE

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103142936951.png" alt="image-20230103142936951" style="zoom:50%;" />
    
###### LE

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103143024388.png" alt="image-20230103143024388" style="zoom:50%;" /> 

###### Isomap

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103143304619.png" alt="image-20230103143304619" style="zoom:50%;" /> 

###### T-SNE     

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103144332295.png" alt="image-20230103144332295" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103143459393.png" alt="image-20230103143459393" style="zoom:23%;" /> **Symmetric SNE**<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103143520375.png" alt="image-20230103143520375" style="zoom:23%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103144709629.png" alt="image-20230103144709629" style="zoom:50%;" />





**T-distributed Stochastic Neighbor Embedding (T-SNE)**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103144433509.png" alt="image-20230103144433509" style="zoom:50%;" /> 





## 7. Object Detection

*The process of finding and classifying objects in an image.* 

### 7.1 Viola/Jones detector

** Rectangle features**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103145948538.png" alt="image-20230103145948538" style="zoom:50%;" /> 

** Integral images for fast computation**

​	3.2

** Boosting for feature selection**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103150122965.png" alt="image-20230103150122965" style="zoom:33%;" /> 



** Attentional cascade(注意级联) for fast rejection of negative windows**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103150348976.png" alt="image-20230103150348976" style="zoom:33%;" /> 



### 7.2 Deformable Part Models (DPM)

#### Histogram of gradients

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103151058578.png" alt="image-20230103151058578" style="zoom: 50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103151506971.png" alt="image-20230103151506971" style="zoom: 33%;" /> 





#### Partial models - Pictorial Structure

Objects are decomposed into parts and spatial relations among parts

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103152257325.png" alt="image-20230103152257325" style="zoom:33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103152316841.png" alt="image-20230103152316841" style="zoom:40%;" />







#### Latent (Structured) SVM

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103151723634.png" alt="image-20230103151723634" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103151738290.png" alt="image-20230103151738290" style="zoom:50%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103151751866.png" alt="image-20230103151751866" style="zoom: 50%;" /> 



### 7.3 Two-stage Object Detection

 The first stage identifies a subset of regions in an image that might contain an object

 The second stage classifies the object in each region

#### R-CNN

(Regions with CNN features)

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103152910082.png" alt="image-20230103152910082" style="zoom:50%;" /> 

Propose class-independent regions of interest by **selective search**(**Warp** to have a fixed size as required to pretrained CNN)

------->Finetune CNN on warped proposal regions for K+1classes

------->Create features from the image proposals( One SVM for each object class The positive sample: IoU overlap threshold >= 0.3)

--------->correction offset using CNN features( Non-max suppression)



#### Fast R-CNN

Whole input image to the CNN to generate a convolutional feature map

Alter the pre-trained CNN:

 Replace the last max pooling layer of the pre-trained CNN with a **RoI** pooling layer

1. 根据输入image，将 ROI 映射到 feature map 对应位置；
2. 将映射后的区域划分为相同大小的 sections（sections数量与输出的维度相同）；
3. 对每个 sections 进行 max pooling 操作

 Replace the last fully connected layer and the last softmax layer (K classes) with a fully connected layer and softmax over K + 1 classes

• Two output layers:

 A softmax estimator of K + 1 classes outputs a discrete probability distribution per RoI

 A bounding-box regression model predicts offsets relative to the original RoI for each of K classes



#### Faster R-CNN

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103160107440.png" alt="image-20230103160107440" style="zoom:33%;" /> 

 <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103160119555.png" alt="image-20230103160119555" style="zoom:33%;" />

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103160146767.png" alt="image-20230103160146767" style="zoom:33%;" /> 

#### Masked R-CNN

 Replacing the ROI Pooling module with a more accurate **ROI Align module**

 Inserting an additional branch out of the ROI Align module

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103163304303.png" alt="image-20230103163304303" style="zoom:50%;" /> 



<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103163332577.png" alt="image-20230103163332577" style="zoom:33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103163349164.png" alt="image-20230103163349164" style="zoom:33%;" />



### 7.4 One-stage Object Detection

**YOLO**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103160503392.png" alt="image-20230103160503392" style="zoom:50%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104094437785.png" alt="image-20230104094437785" style="zoom:53%;" />

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103160632494.png" alt="image-20230103160632494" style="zoom:33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103160735033.png" alt="image-20230103160735033" style="zoom:33%;" />

![image-20230103160835124](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103160835124.png)







## 13. Segmentation

#### 13.1 Semantic Segmentation

(半静态分割)

##### Things/Stuff

| Things                                                       | Stuff                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|  Person, cat, horse, etc<br/> Constrained shape<br/> Individual instances with separate identities <br/> May need to look at objects |  Road, grass, sky etc<br/> Amorphous, no shape<br/> No notion of instances<br/> Can be done at pixel level<br/> “texture |
| Do object detection, then segment out detected objects       | ”Texture classification” Compute histograms of filter responses  Classify local image patches |

##### Down/Upsampling

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103161552625.png" alt="image-20230103161552625" style="zoom:50%;" /> 

| Downsampling                                                 | Upsampling                                                   |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![image-20230103161637178](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103161637178.png) | ![image-20230103161659037](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103161659037.png)<br>![image-20230103161709826](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103161709826.png) |

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103161900702.png" alt="image-20230103161900702" style="zoom:50%;" /> 



##### **Transpose Convolution**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103162035698.png" alt="image-20230103162035698" style="zoom:33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103162058381.png" alt="image-20230103162058381" style="zoom:50%;" />

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103162111413.png" alt="image-20230103162111413" style="zoom:50%;" /> 

##### Problems

• Problem: Need fine details!

​			• Shallower network / earlier layers?

​			 Deeper networks work better: more abstract concepts

​			 Shallower network => Not very semantic!

• Remove subsampling?

​			 Subsampling allows later layers to capture larger and larger patterns

​			 Without subsampling => Looks at only a small window

| Image pyramid                                                | Skip connections                                             | Dilation                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![image-20230103162531473](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103162531473.png) | ![image-20230103162619907](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103162619907.png)<br>Problem: early layers not semantic<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103162641010.png" alt="image-20230103162641010" style="zoom:33%;" /> | ![image-20230103162908518](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103162908518.png) |

#### 13.2 Video Object Segmentation

Appearance changes， Occlusions， Distraction from similar backgrounds

| Semi-supervised (one-shot)                                   | Unsupervised (zero-shot)                                     | Interactive                                                  | Language-guided                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![image-20230103163720040](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103163720040.png) | ![image-20230103163731614](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103163731614.png) | ![image-20230103163746219](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103163746219.png) | ![image-20230103163755990](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103163755990.png) |

**One classical SVOS model: MaskTrack**

前一帧的mask+当前帧--》当前帧的mask

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103163834509.png" alt="image-20230103163834509" style="zoom:50%;" /> 



• Network

​	 DeepLabv2-VGG network

​	 pre-trained on ImageNet

​	 Extra mask channel of filters: gaussian initialization

• Offline training

​	 Does not require pixel-label annotations on videos

​	 Images and masks: ECSSD, MSRA10K, SOD, and PASCAL-S 

​	 Deforming the binary segmentation masks

• Online training

​	 200 iterations 

​	 1000 augmented training samples from the first frame

​	 Same learning parameters as for offline training



## 14. Object Tracking

• Input: target 

• Objective: Estimate target state over time 

• State: Position, Appearance, Shape, Velocity, affine transformation w.r.t. previous patch

• Choice: (O. S. S.)

​	 **O**bject representation

​	 **S**imilarity measure

​	 **S**earching process 



**Four stages:**

① Target initialization

② Appearance modeling

​	 **Visual representation**: construct robust features and representation that can describe the object (template) 

​	 **Statistical modeling**: use statistical learning techniques to build mathematical models for object identification effectively.

③ Motion estimation

④ Target positioning



**Challenges**

• Illumination Variation

• Scale Variation 

• Occlusion

• Deformation – non-rigid object deformation 

• Motion Blur 

• Fast Motion – the motion of the ground truth is larger than 20 pixels

• In-Plane Rotation

• Out-of-Plane Rotation

• Out-of-View

• Background Clutters 

• Low Resolution – the number of pixels inside the groundtruth bounding box is less than 400



**Object representation**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103165636727.png" alt="image-20230103165636727" style="zoom: 33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103165423099.png" alt="image-20230103165423099" style="zoom: 33%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103165446163.png" alt="image-20230103165446163" style="zoom:50%;" />**Recent trend: CNN features**





#### Online object tracking 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103234000499.png" alt="image-20230103234000499" style="zoom:50%;" />![image-20230103234043005](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103234043005.png) 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103234043005.png" alt="image-20230103234043005" style="zoom:50%;" />  

##### **PN Learning**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103234139699.png" alt="image-20230103234139699" style="zoom:50%;" /> 



##### Deep SORT Tracker

MOT(multiple object tracking):

Locate multiple objects of interest in a given video simultaneously, maintain their IDs and record their trajectories.

**detections**-->**association**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104003248768.png" alt="image-20230104003248768" style="zoom:50%;" />motion model i 个target，j个追踪

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104003345081.png" alt="image-20230104003345081" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104003422776.png" alt="image-20230104003422776" style="zoom:50%;" /> appearance model 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104003534126.png" alt="image-20230104003534126" style="zoom:50%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104003643042.png" alt="image-20230104003643042" style="zoom:40%;" /><img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104003656107.png" alt="image-20230104003656107" style="zoom:40%;" />





#### Offline object tracking

##### **GOTURN**

Generic Object Tracking Using Regression Network

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103234353593.png" alt="image-20230103234353593" style="zoom:50%;" /> 

**What to track?**

• Crop and scale the previous frame to be centered on the target object

• Padding-receive extra contextual information about the surroundings

**Where to look?**

• Hypothesis: objects tend to move <u>smoothly</u> through space

• Choose a search region in current frame based on the object’s previous location—> crop

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103234437509.png" alt="image-20230103234437509" style="zoom:33%;" /> 在周围固定范围提取

• Conv Layers: extract image features

• Fully connected layers: compare the features from the target object to the features in the current frame to find where the target object has moved and output bounding box.

• Loss: L1 loss between predicted bounding box and ground truth.



##### Siamese-based Tracker

| SiamFC                                                       | SiamRPN                                                      | SiamRPN++                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![image-20230104000734469](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104000734469.png) | ![image-20230104001155957](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104001155957.png) | **Spatial aware sampling strategy**<br>[目标不一定在bbox中心]<Br>![image-20230104001841635](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104001841635.png) |
| ![image-20230104000837173](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104000837173.png) | ![image-20230104001347668](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104001347668.png) | **Layer-wise Aggregation**<br>![image-20230104001954586](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104001954586.png) |
| Cross Correlation (XCorr) layer predicts a single channel similarity map between target template and search patches<br>![image-20230104002313710](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104002313710.png) | Up-Channel Cross Correlation (UPXCorr) layer outputs a multi-channel correlation features by cascading a heavy convolutional layer with several independent XCorr layers<Br>![image-20230104002344133](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104002344133.png) | Depth-wise Cross Correlation (DW-XCorr) layer predicts multi-channel correlation features between a template and search patches<Br>![image-20230104002436046](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230104002436046.png) |













## 15. Vision-Language Learning 

*aims to build models that can process and relate information from vision and language*

| Visual Question Answering:                                   | Cross-modal retrieval                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [vision+language--->language]<br>Generating natural language description of an image/video | [language--->vision]<br>Given an image and a question (text) about the image/video, the model aims to provide an accurate natural language answer |
| • Applications:<br/>➢ Alt-text generation (from PowerPoint).<br/>➢ Generating summaries for Videos (YouTube)<br/>➢ Content-based image retrieval. | ![image-20230102103515394](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102103515394.png) |
| ![image-20230102102944268](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102102944268.png) | ![image-20230102103807893](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102103807893.png) |

****

**Visual captioning:** vision--->language

**Text-to-image Synthesis:** language--->vision

**Vision-Language Navigation**

**Vision dialog**

**NLVR2: **Predict if the caption is True or False

![image-20230102104109437](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102104109437.png)









#### Sequence-to-Sequence Modeling (Seq2Seq)

Text, image and video are all sequence data

##### RNN

Recurrent Neural Networks (RNN): connections between nodes form a directed or undirected graph along a temporal sequence

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102104909791.png" alt="image-20230102104909791" style="zoom: 33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102104928717.png" alt="image-20230102104928717" style="zoom: 33%;" /> 

| Many input to one output                                     | Many input to many output                                    | One input to many output                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| • Text classification   • Stock forecasting                  | • Language translation                                       | • Image caption                                              |
| ![image-20230102105423284](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102105423284.png) | ![image-20230102105440053](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102105440053.png) | ![image-20230102105457779](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102105457779.png) |

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102105409266.png" alt="image-20230102105409266" style="zoom:50%;" /> 



**Long Short-Term Memory (LSTM)**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102110051242.png" alt="image-20230102110051242" style="zoom:50%;" /> 



##### Transformers

• Sequence-to-sequence (Seq2seq)   • Encoder and Decoder Stacks

<u>**Self-Attention**</u>

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102111135639.png" alt="image-20230102111135639" style="zoom:25%;" /> 

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102110645421.png" alt="image-20230102110645421" style="zoom:50%;" /> 



<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102110949275.png" alt="image-20230102110949275" style="zoom:50%;" /> 

<u>**Multi-head Self-Attention**</u>

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102111101545.png" alt="image-20230102111101545" style="zoom:50%;" /> 

**Position Encoding**

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102111329802.png" alt="image-20230102111329802" style="zoom:33%;" /> 

![image-20230102111734961](C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230102111734961.png)

• CNN: self-attention that can only attends in a receptive field.

• RNN：hard to learn long-range dependencies; nonparallel, more computation time





 <u>in Neural Language Processing (NLP)</u>

• BERT: same network architecture as **transformer encoder.**

Masked language modeling (MLM) pre-training



in Computer Vision (CV)

• Image Recognition

• Object detection

• Vison-Language (VL)



## Appendix

#### a.1 Transfer Learning

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103164513956.png" alt="image-20230103164513956" style="zoom:33%;" /> <img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103164534466.png" alt="image-20230103164534466" style="zoom:50%;" />

<img src="C:\Users\afo\AppData\Roaming\Typora\typora-user-images\image-20230103164614749.png" alt="image-20230103164614749" style="zoom:50%;" /> 