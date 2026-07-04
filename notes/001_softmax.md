# Softmax

Softmax is one of the widely used functions in ML and DL.

Softmax function based on **Natural exponent function** $e$

$e$ is a constant irrational number where $e=2.718...$

![Exponential Function Plot](~/dummy_rep/dummy_rep_for_review/assets/images/exponential_function_graph.png)

$e$ raised to the power aything is always a positive number. That is the reason it is used in probabilities as the probabilities are always positive.

This $e$ is the key to unlock the **softmax function**

$$
\sigma_i = \frac{e^{z_i}}{\sum{e^z}}
$$

lets consider an example 

$$
\begin{aligned}
z &= [1,2,3] \\[6pt]

e^z &= [e^1, e^2, e^3] \\
    &= [2.72, 7.39, 20.01] \\[6pt]

\sum e^z &= 2.72 + 7.39 + 20.01 \\
         &= 30.19 \\[6pt]

\sigma_1 &= \frac{2.72}{30.19} \\
         &= 0.09 \\[6pt]

\sigma_2 &= \frac{7.39}{30.19} \\
         &= 0.24 \\[6pt]

\sigma_3 &= \frac{20.01}{30.19} \\
         &= 0.67 \\[6pt]

\sigma &= [0.09, 0.24, 0.67]
\end{aligned}
$$


> [!NOTE]
> sum of $\sigma$ is equals to 1

Sum of the softmax function is always 1. So these necessarily can be considered as probabilities.

A softmax function takes some numbers as input and output can be identified as the probabilities of inputs occuring.

```python
import numpy as np

z = np.random.randint(-5, high=15, size=25)
num = np.exp(z)
den = np.sum(np.exp(z))
sigma = num/den

idx = np.argsort(z)
z_sorted = z[idx]
sigma_sorted = sigma[idx]
plt.plot(z_sorted, sigma_sorted, color='blue',
    marker='o')
plt.xlabel('z')
plt.ylabel('softmax')
plt.title('$\sum\sigma$ = %g' %np.sum(sigma))
plt.show()
```

![Sigmoid Function plot](~/dummy_rep/dummy_rep_for_review/assets/images/sigmoid_function_plot.png)