# SVM_Machine_Learning
---
---
# support vector Machine
Support Vector Machines (SVMs) are a type of supervised machine learning algorithm used for both regression and classification tasks.


1.   SVC [Support Vector Problem]
2.   SVR [Support Vector Problem]



- The main objective of SVM is to find a hyperplane that best separates the classes in a feature space.

- This hyperplane should have the largest margin,
( i.e., the maximum distance between the nearest data points of both classes.)


## how the actually this be done :

**Equation of line (Slope Intercept Form)**

**y = mx + c**
```

    y = β0 + β1x

    ax + by + c = 0 [intercept Form]
  
    y =  (-ax -c) / b

    y = (-ax / b) - (c / b)

  
  where

  (-ax / b) is coefficient
  
  (c / b) is Intercept
```
```

Now Again let the equation of line be:  ax1 + bx2 +c

can be written:   w1x1 + w2x2 + b = 0

                  [w1w2] transpose * [x1x2]

we will get        w1x1 + w2x2 + b = 0

                   w<sup>t</sup> x + b = 0


now if the intercept is 0:   w'  * x = 0
```
ILLUSTRATION:

- if we consider a plane π(pi) with vector W which is perpendicular to the line 

![Screenshot 2023-09-20 004345](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/914b17b8-d70c-4dd6-8134-f4d66d9a10cf)

To find the point we need to find the distance between d1 and d2




