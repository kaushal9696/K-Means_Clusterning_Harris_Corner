## [Machine Learning] Object Detection Model | K-means Clustering

- The goal of this project is to implement Harris corner detection technique
    to find the data points and perform k-means clustering by self-made
    function without using any build in function from any library.
- After getting the best fit value of k and maxi iteration, plot the different
    points on the original image.
- In last part, draw a bounding box for each cluster of the data points and use
    different color for each bounding box.

## Project methodology, equations and implementations

Explanation: -

1. Firstly, import all the necessary libraries in this case following libraries are
    used: - NumPy for vectorization, indexing, and broadcasting. Matplotlib’s
    pyplot function to plot graphs. Cv2 for image processing and converting
    image to array. SciPy for Euclidian distance finding.
2. Second step is to import given image by using cv2 library, but cv2 library
    import image as a BGR, but for better result and original color result,
    convert it to RGB by function cv2.cvtColor.
3. Next step is to convert the RGB image to Grayscale image such that it
    converts into 2d array from 3d array and we can get the Harris corner.
4. For finding corners, we have used the built-in function
    cv2.goodFeaturesToTrack to get the best 100 points which are corner
    points by giving quality level 0.10 and minimum distance 16 to the function.
    This can be varied in different images and purposes.


5. As cv2.goodFeaturesToTrack gives the array inside array we need to get the
    last array containing points and for that and this library gives the double
    value of each point, for better result convert it to integer type.
6. Next step is to plot an original image with the points we found in above
    steps by using scatter points and matplotlib’s plotting function.
7. In above figure you can see that we find all the necessary points, next step
    is to implement the k-means algorithm to get them in a cluster by define
    the different k values.
8. For K-means algorithm we have created a function named
    K_Means_Finder, where this function takes 3 arguments, 1 st is points that
    we got from above steps, 2nd is value of k, and third is number of iterations.
9. Here are the steps for how I implemented k-means algorithm, first we got
    random 3 centroids (if k = 3 , centroids = 3) from our original array X, which
    contains all the points, means getting random 3 points from X. Next step is
    to put a loop for maximum iteration, in this case we get 100 iteration for
    the more accurate result by our algorithm. For K-means algorithm
    implementation, first get the Euclidian distance for each point in our array
    X and find distance between that and our random centroids. Now when we
    get the all the distances, create a dictionary with the cluster index as an
    index of dictionary (if k = 3 , dictionary index will be { 1 : [], 2 : [], 3 : []}) now
    cluster all points and get the minimum value of Euclidian distance and index
    of that minimum value to categorize them in our dictionary such that all the
    100 points arranged. Next step is getting each index’s all the points and get
    the mean value and make it as a new centroid and repeat the steps until we
    get the accurate result and accurate points in each index of dictionary.

10. Next step is to find the result for different values of k and get the best
    value of k according to given image which describes the best clustering of
    the points. Below is a image which show the graphs for different value of k.


11. From above images, we can clearly see that the k = 3 is best fit in according
    to given image. Next step is to finalize the k, which is finalized that the
    value of k = 3 for the given 100 points. Below is the graph plotted for the
    value of k = 3 with different color for each cluster


12. In final step, the objective is to draw a bounding box for each cluster and
    such that the clusters pop-up by using different color for each bounding
    box for each cluster. For creating bounding box cv2.rectangle() is used to
    draw a bounding box. Here to get the bounding box for each cluster, we
    need maximum value of x axis and y axis from all the clusters and get the
    minimum value of x axis and y axis, from that values we can make a
    rectangle which is best fit to our cluster and make a bounding box. (if k = 3 ,
    there will be 3 bounding boxes for each cluster). Below is the image that
    shows bounding box.


# Conclusion

This project is done with three main goals, first is to implement the harish corner
detection points, in this case, we took 100 best points by using
cv2.goodFeaturesToTrack() library and plot the 100 points on the original image
to check that there are the corner points. In second part, k-means algorithm is
implemented, which is implemented by creating my own function and not by
using any built-in libraries. After implementing the k-means algorithm we have
plotted different graphs for different value of k and get the best value of k. For
the best suited value of k we plotted a graph showing different color points for
each cluster group such that it clearly differentiate from each cluster group. In
last, I bounding box is implemented on each cluster group by using the each
cluster’s maximum and minimum value of x and y axis and by that I have
implemented it by using function cv2.rectangle().

# References

Matplotlib (For Plotting Graphs): - https://matplotlib.org/

OpenCV (For Image Processing): - https://opencv-python-
tutroals.readthedocs.io/en/latest/py_tutorials/py_gui/py_image_display/py_ima
ge_display.html

SciPy (To find Euclidian Distance): -
https://docs.scipy.org/doc/scipy/reference/spatial.distance.html


