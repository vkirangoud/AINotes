# AINotes
Capture Notes related to Linear Algebra, Signal Processing wrt to AI applications
* ## Difference between a linear problem and a non-linear problem ? <span style="color:blue"> *Essence of dot-product and Kernel Trick*</span><br>
Many classifiers, among them the linear Support Vector Machine (SVM), can only solve problems that are linearly separable, i.e. where the points belonging to class 1 can be separated from the points belonging to class 2 by a hyperplane.

In many cases, a problem that is not linearly separable can be solved by applying a transform phi() to the data points; this transform is said to transform the points to feature space. The hope is that, in feature space, the points will be linearly separable. (Note: This is not the kernel trick yet... stay tuned.)

It can be shown that, the higher the dimension of the feature space, the greater the number of problems that are linearly separable in that space. Therefore, one would ideally want the feature space to be as high-dimensional as possible.

Unfortunately, as the dimension of feature space increases, so does the amount of computation required. This is where the kernel trick comes in. Many machine learning algorithms (among them the SVM) can be formulated in such a way that the only operation they perform on the data points is a scalar product between two data points. (I will denote a scalar product between x1 and x2 by <x1, x2>.)

If we transform our points to feature space, the scalar product now looks like this:

<phi(x1), phi(x2)>

The key insight is that there exists a class of functions called kernels that can be used to optimize the computation of this scalar product. A kernel is a function K(x1, x2) that has the property that

K(x1, x2) = <phi(x1), phi(x2)>

for some function phi(). In other words: We can evaluate the scalar product in the low-dimensional data space (where x1 and x2 "live") without having to transform to the high-dimensional feature space (where phi(x1) and phi(x2) "live") -- but we still get the benefits of transforming to the high-dimensional feature space. This is called the kernel trick.

Many popular kernels, such as the Gaussian kernel, actually correspond to a transform phi() that transforms into an infinte-dimensional feature space. The kernel trick allows us to compute scalar products in this space without having to represent points in this space explicitly (which, obviously, is impossible on computers with finite amounts of memory).
[Reference:](https://stackoverflow.com/questions/1148513/difference-between-a-linear-problem-and-a-non-linear-problem-essence-of-dot-pro)
