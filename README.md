# OpenCV

### 3. Median Blurring

The Median blur operation is similar to the other averaging methods. Here, the function `cv.medianBlur()` takes the median of all the pixels under the kernel area and the central element is replaced with this median value. This is highly effective against salt-and-pepper noise in an image. But in median blurring, the central element is always replaced by some pixel value in the image. It reduces the noise effectively. Its kernel size should be a positive odd integer. This operation processes the edges while removing the noise.


In this demo, I added a 50% noise to our original image and applied median blurring. Check the result:


```python
median = cv.medianBlur(img,5)
```

Result:
![sample_image](https://user-images.githubusercontent.com/78999231/125315439-c235dd00-e354-11eb-9718-e59106a88285.jpg)
![median_blur](https://user-images.githubusercontent.com/78999231/125315456-c6fa9100-e354-11eb-9b15-134f4aa9064a.jpg)


### 4. Biletral Filtering

So far, we have explained some filters which main goal is to smooth an input image. However, sometimes the filters do not only dissolve the noise, but also smooth away the edges. To avoid this (at certain extent at least), we can use a bilateral filter. `cv.bilateralFilter()` is highly effective in noise removal while keeping edges sharp. But the operation is slower compared to other filters. It doesn't consider whether a pixel is an edge pixel or not. So it blurs the edges also, which we don't want to do.

```python
blur = cv.bilateralFilter(img,9,75,75)
```

![image](https://user-images.githubusercontent.com/78999231/125316735-0675ad00-e356-11eb-8781-608ce6ac4098.png)
