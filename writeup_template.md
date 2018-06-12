# Finding Lane Lines on the Road

The goals/steps of this project are the following:

- Make a pipeline that finds lane lines on the road.
- Reflect on your work in a written report.

# Reflections

## Description
The pipeline consists on 7 steps represented by 7 different functions:

- **grayAction**: Returns a gray scaled version of the input image using **cv2.cvtColor** method.
- **blurAction**: Applies a Gaussian blur to the provided image using **cv2.GaussianBlur** method.
- **cannyAction**: Use a [Canny transformation](https://en.wikipedia.org/wiki/Canny_edge_detector) to find edges on the image using **cv2.Canny** method.
- **maskAction**: Eliminate parts of the image that are not interesting in regards to the line detection (for now...).
- **houghAction**: Use a [Hough transformation](https://en.wikipedia.org/wiki/Hough_transform) to find the lines on the masked image using **cv2.cv2.HoughLinesP**. It also adjust a line to the set of lines returned by the Hough transformation in order to have a clearer-two-lines representation of the road lines using **Merge lines with original image** 
**ProcessVideo** get a image series and reproduce a video with all this steps above

The output of each step is saved in a directory:

- [test_images_gray](test_images_gray)
- [test_images_blur](test_images_blur)
- [test_images_canny](test_images_canny)
- [test_images_region](test_images_region)
- [test_images_hough](test_images_hough)
- [test_images_merged](test_images_merged)

## Potential shortcomings/suggestions

- The lines shake a lot on the videos, a better way to average them should be possible.
- The line size should be improved.
- Bright points outside the lines were taking into account.