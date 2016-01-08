# Hand-Recognition-using-OpenCV

This C++ code uses OpenCV 'C' api and analyse hand gestures under following ways -

1 - Convert RGB image (taken through web camera (IplImage* src)) into GRAYSCALE (IplImage* gray).

2 - Set ROI (Region Of Interest) using cvSetImageROI(src, cvRect(340,100,270,270)) function.
  # What is ROI ?
  # The idea behind the ROI is that, once it is set, functions that would normally operate on the entire image will instead act only on the subset of the image  indicated by the ROI. All OpenCV functions will use ROI if set.

3 - Smooth the grayscale image using cvSmooth(gray,gray,CV_BLUR,(12,12),0)
  # Why do we use smoothing ?
  # It effectively reduces the information content of the image by convolving it with a Gaussian or other similar kernel function. It reduces the noise and OpenCV  makes such convolutions exceptionally easy to do.

4 - Then we will threshold the smoothed image bu using cvThreshold(gray,gray,0,255,(CV_THRESH_BINARY_INV+CV_THRESH_OTSU)) function.

5 - At last we will find contours using contour detection , convex hull of palm region , convexity defects.
