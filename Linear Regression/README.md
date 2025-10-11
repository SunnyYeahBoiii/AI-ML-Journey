# Introduction to Satistical Learning:

## 3.7 Excercises
### Conceptual:

1.

Based on the table we can see that TV and radio have high impact to sales, but on the other hand newspaper doesn't. Theoretically, considerable predictions usally have $p$-value < 0.05, based on that, we can remove newspaper's coef from out model.

**Note:** p-value là giá trị kiểm định, < 0.05 là ổn. Trong trường hợp này, TV và radio có giá trị p-value nhỏ nên có tác động lớn đến sales nhưng newspaper lại có giá trị cao ~0.899 nên không ảnh hướng đến sales nhiều.

2.
- KNN-classifier takes the majority value for the prediction and the output is a qualitative value 
- KNN regression uses the formula to calculate the mean of the $K$ nearest neighbors and outputs a quantitive value 
$$f(X) = \frac{1}{K}\sum_{x_i \in N}{y_i}$$
3.

| ID  | $X_1$ = GPA | $X_2$ = IQ | $X_3$ = Level | $X_4$ = IE GPA-IQ | $X_5$ = IE GPA-Level |
| --- | ----------- | ---------- | ------------- | ----------------- | -------------------- |
| 1   | 20          | 0.07       | 35            | 0.01              | -10                  |

(a): The (iii) is the right answer. Considering the model:

$$f(X) = \beta_0 + \beta_1 \cdot X1 +\beta_2 \cdot X2 + \beta_3 \cdot X3 + \beta_4 \cdot X1 \cdot X2 + \beta_5 \cdot X1 \cdot X3$$

We see when IQ == GPA:
$$f(Level = 1) - f(Level = 0) = 35 - 10x$$
so that:
$$f(x)= \begin{cases} f(Level = 1) - f(Level = 0) \ge 0, & \text{if } x \ge 3.5\\ f(Level = 1) - f(Level = 0) < 0, & \text{otherwise} \end{cases}$$

(b) Plug GPA = 4.0 , IQ = 110 , Level = 1 into the model:

$$f(X_1) = 50 + 20 \cdot 4.0 +0.07 \cdot 110 + 35 \cdot 1 + 0.01 \cdot 4.0 \cdot 110 + -10 \cdot 4.0 \cdot 1$$

The results is $f(X_1) = 137.1$

4.

(a): Given the linearity in the relationship between X and Y, the linear regression should have a RSS greater than or equal to the cubic regression. Looking into the equations, since the true relationship between X and Y is linear, coeficent for $X^2$ and $X^2$ would be unnecessery and somewhat overfitting the trainning data leading to smaller RSS.

(b): Because of test data, overfitting would cause the RSS to be bigger than expected. Based on that, the cubic regression would likely have an RSS greater than or equal to the linear regression. 

(c): When the linearity in the relationship between X and Y is gone, the linear regression no longer have a better RSS than the cubic regression. This phenomenon is based on the coeficent of squared and cubic parameters, having these coeficent can fit better the trainning data than the linear regression.

(d): We have no infomation to conclude the better RSS in every scenario comparing between cubic regression and linear regression.

(5):
$$\hat{y_i} = x_i\cdot\beta$$
$$\hat{y_i} = x_i \cdot \frac{\sum^{n}_{j = 1}x_jy_j}{\sum_{j = 1}^{n}x_j^2}$$
$$\hat{y_i} = \frac{x_i}{\sum_{j = 1}^{n}x_j^2} \cdot \sum_{j = 1}^{n}(x_jy_j)$$
Define $C = \frac{x_i}{\sum_{j = 1}^{n}x_j^2}$:

$$\hat{y_i} = C \cdot \sum_{j = 1}^{n}(x_jy_j)$$

$$\hat{y_i} = \sum_{j = 1}^{n}(C \cdot x_j \cdot y_j)$$
$$\hat{y_i} = \sum_{j = 1}^{n}(\frac{x_i}{\sum_{k = 1}^{n}x_k^2} \cdot x_j \cdot y_j)$$

$$\hat{y_i} = \sum_{j = 1}^{n}(\frac{x_i\cdot x_j}{\sum_{k = 1}^{n}x_k^2} \cdot y_j)$$
We can see that it forms:

$$\hat{y_i} = \sum_{j = 1}^{n}a_j \cdot y_j$$
$$\Rightarrow a_j = \frac{x_i\cdot x_j}{\sum_{k = 1}^{n}x_k^2}$$
(6):

Consider:

$$f(y) = \beta_0 + \beta_1x$$

If the linear regression always pass the point ($\bar{x}$ , $\bar{y}$):
$$\bar{y} = \beta_0 + \beta_1 \cdot \bar{x}$$
$$\Rightarrow f(y) = \beta_0 + \beta_1 \cdot \bar{x}$$
$$\Leftrightarrow f(y) = \bar{y} - \beta_1 \cdot\bar{x} + \beta_1 \cdot\bar{x}$$
$$\Leftrightarrow f(y) = \bar{y}$$
So that using Least Square method, the Linear Regression always go pass the point ($\bar{x}$ , $\bar{y}$).

### Applied

All of the excersices are in the file [isl_chapter_3.ipynb](./isl_chapter_3.ipynb)

# Other Plays:

## Student Performance Dataset: [Originally on Kaggle](https://www.kaggle.com/datasets/nikhil7280/student-performance-multiple-linear-regression/data?select=Student_Performance.csv)

