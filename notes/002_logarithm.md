# Logarithms

Logarithm function is also a very common function we come across ML/DL.

Same as how the softmax function can be linked to probability, sameway the log function also can be linked to optimization in ML.

Exponential function $e$ is always positive and never zero. 

But Logarithm function is a monotonic function, i.e, if $x$ goes up, $log(x)$ also goes up. So minimizinf $x$ means minimizing $log(x)$.

![Log Function Plot](/assets/images/log_function_plot.png)

If the plot is analyzed, we can observed that log function is streched out at lower values of $x$, whereas $e$ streches out at higher values of $x$

So when a log function is applied on exponential or vice-versa they cancel out each other.

![Log vs exp Plot](/assets/images/log_exp_cancel_out.png)

## To Remember
- Log is a monotonic function.
- Log function comes handy during minimization as it streches for lower values of $x$, distinguishing lower values better and also increasing precision at lower values of $x$. So loss values which are closer to 0 use log function to have numerical precision.
- Log also have bases like base %e%, 2, 10 etc. These only differ inslope in contect of ML/DL.