# ComputerVision3D_DisparityMap
You need Imagine++ library (http://imagine.enpc.fr/~monasse/Imagine++/)

Compute the disparity map associated to a pair of images. We start from high confidence points (seeds) then expand by supposing that the disparoty map is regular. 
We compute disparity map of all points with NCC score, we keep only those with sufficiently high score (seeds), put them in a priority queue q. 
While q is not empty, pop P the top of queue
    For each 4-neighbor N of P having no valid disparity, set the disparity of N by highest NCC score amongst dP-1, dP, dP+1
    Push N in queue
