FastDTW- Dynamic Time Warping (DTW) with a linear time and memory complexity
============================================================================

Original project: https://code.google.com/p/fastdtw/

FastDTW is an approximate Dynamic Time Warping (DTW) algorithm that provides optimal or near-optimal alignments with an O(N) time and memory complexity, in contrast to the O(N^2) requirement for the standard DTW algorithm. FastDTW uses a multilevel approach that recursively projects a solution from a coarser resolution and refines the projected solution.

Implementation:
---------------

FastDTW is implemented in Java. If the JVM heap size is not large enough for the cost matrix to fit into memory, the implementation will automatically switch to an on-disk cost matrix. Alternate approaches evaluated in the papers listed below are also implemented: Sakoe-Chiba Band, Abstraction, Piecewise Dynamic Time Warping (PDTW).

This is the original/official implementation used in the experiments described in the papers below.

Reference:
---------------

FastDTW: Toward Accurate Dynamic Time Warping in Linear Time and Space. Stan Salvador & Philip Chan. KDD Workshop on Mining Temporal and Sequential Data, pp. 70-80, 2004. (http://cs.fit.edu/~pkc/papers/tdm04.pdf)

Toward accurate dynamic time wrapping in linear time and space. Stan Salvador and Philip Chan. Intelligent Data Analysis, 11(5):561-580, 2007. (http://iospress.metapress.com/content/h74w3l3156332247)
