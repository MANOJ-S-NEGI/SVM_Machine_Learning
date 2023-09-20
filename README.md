# SVM_Machine_Learning
---
---
# Support vector Machine
Support Vector Machines (SVMs) are a type of supervised machine learning algorithm used for both regression and classification tasks and outlier detection.
It works by finding a hyperplane in a high-dimensional feature space that best separates classes.


1.   SVC [Support Vector Problem]
2.   SVR [Support Vector Problem]



- The main objective of SVM is to find a hyperplane that best separates the classes in a feature space.

- This hyperplane should have the largest margin,
( i.e., the maximum distance between the nearest data points of both classes.)


## How the actually be done :
to understand the concept we need to look into basic alzebric equation.

**Equation of line (Slope Intercept Form)**

**y = mx + c**
```

    y = β0 + β1x

    ax + by + c = 0 [intercept Form]
  
    y =  (-ax -c) / b

    y = (-ax / b) - (c / b)

  
  where,

  (-ax / b) is coefficient
  
  (c / b) is Intercept
```
```

Now Again let the equation of line be:  ax1 + bx2 +c

can be written:   w1x1 + w2x2 + b = 0

                  [w1w2] transpose * [x1x2]

we will get       w1x1 + w2x2 + b = 0

```

w<sup>t</sup> x + b = 0


now if the intercept is 0: i.e. the line passing through the origin

let's consider "w_transpose" to be w' 
 
  w'  * x = 0

<br>

- if we consider a plane π(pi) with vector W which is perpendicular to the line 

![Screenshot 2023-09-20 004345](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/914b17b8-d70c-4dd6-8134-f4d66d9a10cf)

To find the point we need to find the distance  d1:

let's consider "w_transpose" to be w' 

d = (w'p1) / ||w||

```
the reason we are dividing "w" is to get the unit vector

   A unit vector is a vector that has a magnitude (or length) of exactly 1. In other words, it is a vector that has been normalized to have unit length.
   For example: The magnitude of the number 8 is 8 and -8 is also 8 (spread from the origin)

```


ILLUSTRATION:
let's say a right-angle triangle with base 3 and height 4 so using Pythagoras the hypotenuse 5 
let's say the hypotenuse is the distance (d) and convert it into a unit vector  "d-hat"

"d-hat" = d / ||d||

✓((9/25) + (16/21))

= ✓(1.122) => 1


---
---
so if we expand d = (w'p1) / ||w||

we will get the algebraic expression

**||w|| ||p|| cosθ**

- if we replace the θ(theta) between 0-90 (zero to 90) degrees the value we get is always positive
- the value will be ranging between 0 to 1


  ![CamScanner 09-20-2023 01 37](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/7b9e278a-e414-4106-be84-4db7be4fb8db)


  - if any point lies at an angle less than 90 degrees and greater than 0 (zero) then it is positive so we can say that values p1 is positive while above 90 degrees p2 is negative.
    
 
  ---
  ---

  ## Geometric intuition behind Support Vector Machine

  SUPPORT VECTOR CLASSIFIER :
  
![download_svm](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/68f62c57-087f-47c9-80e5-5535d1b730b3)


  - It performs the same task as logistic regression.
  - In SVC we also find the best-fit line along with the marginal plane on both sides which will be created from the nearest point from the best-fit line.
  - the distance d should be the maximum distance for the clear separation of the point.
  - The nearest points are known as support vectors.

    Note: In real-world scenarios, a clear distinction is not possible but if it happens then we call it a hard margin similarly with no clear distinction we call it a soft margin.

![download_svm_mordified](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/8cb69c81-fe28-49cc-9d1c-b4207921a042)


    
- In this figure  d = maximus

  ```
  
  let's consider "w_transpose" to be w'

  w'x1 + b = 1  equation ----1
  w'x2 + b = -1   equation ----2

  subtracting eq_2 from eq_1
  w'(x1-x2) = 2

  so, w'(x1-x2) / ||w||  = 2 /||w||
  ```
so, my cost function will be maximum (w,b) 2 / ||w||  to get the max dis between the marginal plain

if we get the distance  2 / ||w|| we will be able to make marginal plane 
 - along the margin, we will add constraints if  **w'x + b  >= 1** our value will be positive.
   ```
constraints : Truth Points -> y_prediction *  **w'x + b  >= 1
   ```

similarly,

To minimize the distance by inversing we will get a loss function to reduce the margin error.

the cost function will be: min (w,b)
```

(||w|| / 2) + 	Ci ∑<sup>w</sup><sub>i=1</sub> ζi

where
- Ci ∑<sup>w</sup><sub>i=1</sub> ζi is called Hinge Loss.
- ζi (zeta) is the submission of the distance of the incorrect data point from the marginal plane
   i.e. distance between the best-fit line and the marginal plane.
- ci is how many points we can ignore for misclassification. (datapoints inside the marginal plane as shown in the figure)

![download_svm 2](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/8135b235-1b5f-4c38-9ccd-a0b97074cf48)



![downloadsvm 3d](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/cc005a43-f357-435d-8d8f-451840427e82)


---
---

# Support Vector Regression 

- In Support Vector Regression (SVR), the goal is to find a hyperplane that minimizes the error while still staying within a certain margin of tolerance (epsilon). This involves considering the distance of data points from the best-fit line (or hyperplane) as well as the distance from the marginal plane.

**The cost function for SVR typically includes two main components:**

- Loss Function for Fitting Data:
    - This term measures the error between the predicted output and the actual output for each data point. Common loss functions used in SVR include the epsilon-insensitive loss or the squared loss.
Regularization Term:

This term is added to the loss function to prevent overfitting. It penalizes the complexity of the model. It is typically proportional to the magnitude of the weights (parameters) in the model.



```
Putting it together, the cost function for SVR can be written as:

Min(w,b)  ∥w∥ / 2 + C * ∑ ζi  
 
constraint:
 
Min(w,b) |"y-hat" - y|  ≤ ε + ζi    

where,

w and b are the weights and bias of the hyperplane, respectively.
ϵ is a parameter that determines the size of the margin (ε  is the epsilon the  distance between the best-fit and marginal plane (gap in marginal error))
|"y-hat" - y| is the absolute predicted output sub  y, the actual output 
 ζi distance of the point from the marginal plane (error above margin)
    
```

![download_svmepsiolon](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/678133cb-caeb-40dd-bce4-defb2fd36f13)
---
---

# SVM Kernel

- One of the key components of an SVM is the kernel function.
-  The kernel function allows SVMs to operate in a high-dimensional feature space without explicitly calculating the coordinates of the data points in that space, which can be computationally expensive.

  ## Types of Kernel 
- Polynomial Kernel:
      - The polynomial kernel computes the dot product, but with an additional user-defined degree and optional coefficient. It allows for non-linear separation of data.

![download1d](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/177fef77-14ec-44fc-8ab7-8e4809024153)

  

- Radial Basis Function (RBF) Kernel:
      - The RBF kernel is very popular. It considers all possible polynomials of all degrees and infinite dimensions. It is suitable for cases where the decision boundary is not easily represented by a straight line or a plane.

![svm 2d](https://github.com/MANOJ-S-NEGI/SVM_Machine_Learning/assets/99602627/40faed46-1e8c-4645-8dee-d4906d5da0d2)



- Sigmoid Kernel:
    - The sigmoid kernel is based on the hyperbolic tangent function. It's suitable for neural networks and other non-linear models, but it's not as commonly used in SVMs.


