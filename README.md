# OpenCV

### Filtering

Image filtering is the process of modifying an image by changing its shades or color of the pixel or by increasing the brightness and contrast of that image. In the image processing filters, which are mainly used to suppress either the high frequencies in the image (i.e. image smoothing), or the low frequencies (i.e. enhancing or detecting edges in the image used).
OpenCV provides a function called `cv.filter2D()` to convolute a kernel with an image. 

### 3. Median Blurring

The Median blur operation is same as the other averaging methods. The function `cv.medianBlur()` takes the median of all the pixels in the kernel area. Then the central element is replaced with the median value. This is very fruitful against salt-and-pepper noise in an image. But in this type of method, the central element is always replaced by some pixel value in the image. this operqation reduces the noise effectively. The kernel size given should be a positive odd integer. The process processes the edges while removing the noise.


In this demo, we have added a 50% noise to the original image and applied median blurring. Check the result:


```python
median = cv.medianBlur(img,5)
```

Result:

![Opencv](https://user-images.githubusercontent.com/78999231/125387969-512a1000-e3bc-11eb-8a8e-40d680a6ced1.jpeg)
![medianBlur](https://user-images.githubusercontent.com/78999231/125388271-da414700-e3bc-11eb-9ecf-6fa8a918867f.jpg)


### 4. Biletral Filtering

Till now, we have explained you some filters whose main goal is to smooth an image which a user inputs. However, sometimes these filters not only dissolve the noise, but also smooth the edges. For avoiding this, we use a bilateral filter. `cv.bilateralFilter()` is very fruitul in noise removal by keeping the edges sharp. But this operation is slower as compared to other filters used. It does not consider if a pixel is an edge pixel or not. So, it blurs the edges.

```python
blur = cv.bilateralFilter(img,9,75,75)
```

Result:

![Opencv](https://user-images.githubusercontent.com/78999231/125387969-512a1000-e3bc-11eb-8a8e-40d680a6ced1.jpeg)
![download](https://user-images.githubusercontent.com/78999231/125388740-aca8cd80-e3bd-11eb-89b6-2777eeb5099b.png)

