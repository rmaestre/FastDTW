FastDTW - Dynamic Time Warping (DTW) with a linear time and memory complexity 

authors: Stan Salvador, stansalvador@hotmail.com
         Philip Chan, pkc@cs.fit.edu

thanks to other contributors:
   Matt Mahoney
   Maya Cakmak
   Thierry Bodhuin
   David Cacenabes Vázquez


project webpage:  http://code.google.com/p/fastdtw/

License:  This code is released under the MIT License

Overview:
FastDTW is an approximate Dynamic Time Warping (DTW) algorithm that provides optimal or near-optimal alignments with only O(N) time and memory requirement, in contrast to the O(N^2) requirement for the standard DTW algorithm. FastDTW uses a multilevel approach that recursively projects a solution from a coarser resolution and refines the projected solution. 

Implementation: 
FastDTW is implemented in Java. If the JVM heap size is not large enough for the cost matrix to fit into memory, the implementation will automatically switch to an on-disk cost matrix. Alternate approaches evaluated in the papers listed below are also implemented: Sakoe-Chiba Band, Abstraction, Piecewise Dynamic Time Warping (PDTW). 

Reference: 
-FastDTW: Toward Accurate Dynamic Time Warping in Linear Time and Space. S. Salvador & P. Chan. KDD Workshop on Mining Temporal and Sequential Data, pp. 70-80, 2004. (http://cs.fit.edu/~pkc/papers/tdm04.pdf) 
-Toward accurate dynamic time wrapping in linear time and space.. S. Salvador and P. Chan. Intelligent Data Analysis, 11(5):561-580, 2007

Compiling the Code:
-Install the Java SDK (java.sun.com).  Version 1.3+ should work fine, and some previous versions may also be OK.
-from the "src" directory compile code by running:  "javac com/FastDtwTest.java com/AbstractionTest.java com/BandTest.java com/DtwTest.java".  This will create executable (through the Java JVM ) ".class" files for the four executable files and any other source files that they require. 

Using the Code:
-Compile the source code (see above)
-Four classes in the com package are tests for FastDTW and the three similar approaches that were examined in the papers listed above: FastDtwTest.java, AbstractionTest.java, BandTest.java, and DtwTest.java.  All four test programs use a different Dynamic Time Warping algorithm to align two time series with a specified "radius" used during the alignment.  The warp distance and warp path are printed to standard output.
-Examples of the time series input files supported by this code are included (trace0.csv, and trace1.csv).  To support new time series formats com.timeseries.TimeSeries would need to be modified or replaced in the test files so a new TimeSeries implementation is used instead.
-Run a test from the "src" directory by typing "java com.FastDtwTest trace0.csv trace1.csv 10.  The output should be:
   Warp Distance: 9.139400704860002
   Warp Path:     [(0,0),(0,1),(1,2),(2,3),...,(272,272),(273,272),(274,273),(274,274)]

Notes:
-Time series files should have one value per line ordered by time
-Data points in the time series files may be multi-dimensional by specifying multiple values by commas on each line
-Euclidean distance is the default distance metric, others that are supported are Manhattan, and Binary (0 if equal, 1 otherwise)
-By default the Java Virtual Machine only permits a small amount of memory to be used, for large time series it is advisable to run with an increased JVM heap size.  To set a 512 MB heap size run the program run: "java -Xmx512m ...".  If a "Ran out of memory ... Will use a swap file instead" message is printed to standard output the program should be run with an increased heap if size possible.
