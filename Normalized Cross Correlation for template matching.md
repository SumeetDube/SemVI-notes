![[Pasted image 20240517012708.png]]
![[Pasted image 20240517012728.png]]
![[Pasted image 20240517012753.png]]

The normalized cross-correlation method is a technique used in image processing and computer vision for template matching. Template matching is a process where a template image (or pattern) is compared against a larger image to find instances where the template closely resembles a part of the larger image. The normalized cross-correlation method measures the similarity between the template and various subregions of the larger image by computing their cross-correlation coefficient, which is then normalized to make it invariant to changes in brightness and contrast.

Here's how the normalized cross-correlation method works, illustrated with an example:

Let's say we have a template image (T) and a larger image (I) as follows:

Template Image (T):
```
1 0 1
0 1 0
1 0 1
```

Larger Image (I):
```
1 0 1 0 0 1
0 1 0 1 1 0
1 0 1 0 0 1
0 1 0 1 1 0
1 0 1 0 0 1
```

1. **Compute Mean of Template and Larger Image**:
   - Calculate the mean intensity value of pixels in both the template image (T) and the larger image (I).

2. **Compute Cross-Correlation**:
   - Place the template image (T) on top of different subregions of the larger image (I).
   - For each position, compute the cross-correlation coefficient between the template and the corresponding subregion of the larger image.
   - The cross-correlation coefficient is calculated as the sum of the element-wise products of the template and the subregion divided by the square root of the sum of squares of the intensities in both images.

3. **Normalize the Cross-Correlation Coefficients**:
   - Normalize the computed cross-correlation coefficients to make them invariant to changes in brightness and contrast. This is done by dividing each coefficient by the square root of the sum of squares of the intensities in the template and the subregion of the larger image.

4. **Find the Best Match**:
   - Identify the position(s) in the larger image where the normalized cross-correlation coefficient is maximized. These positions correspond to the locations where the template matches the subregions of the larger image most closely.

In the example above, we would place the template (T) over different subregions of the larger image (I), calculate the cross-correlation coefficients, normalize them, and then identify the position(s) with the highest normalized cross-correlation coefficient as the best matches.

The normalized cross-correlation method is widely used in various applications such as object detection, pattern recognition, and image registration because it is robust to changes in illumination and contrast, making it suitable for matching templates in real-world images.