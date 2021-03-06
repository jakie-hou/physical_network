# DR_RNN in Tensorflow

Tensorflow implementation of [DR-RNN: A deep residual recurrent neural network for model reduction](https://arxiv.org/abs/1709.00939).

![convergence](./assets/convergence.png)
> convergence for DR_RNN_2 with Adam optimizer and learning rate = 0.1. We half lr every 500 iterations.

To execute the code, simply run:
```
$ python DR_RNN.py
```
To monitor the training process, run:
```
$ tensorboard --logdir=./saved_logs
```


# Result
Reproduced result of Fig.2 from [the paper](https://arxiv.org/abs/1709.00939)

![dist2](./assets/problem1_dist2.png)
![dist3](./assets/problem1_dist3.png)

Results for increasing time steps in DR-RNN

![increase_time_steps](./assets/increase_time_steps.png)

Extrapolation in time, from 10s to 20s.

![extrapolation_in_time](./assets/extrapolation_in_time.png)
> iter:744  train_cost: 1.49850947651e-07  test_cost: 0.00102584168781
extrapolation of y1

Sensitivity analysis. Partial derivative of predicted y w.r.t. x.

![sensitivity_y2](./assets/sensitivity_y2.png)
![sensitivity_y3](./assets/sensitivity_y3.png)
> This result is obtained from DR_RNN_2, at iter:1300, when train_cost=1.52661107222e-06 and test_cost=0.00327986711636

Parameter estimation. When parameter is unknown but fixed:

When parameter is an unknown distribution:

# Todo
- [x] extrapolation in time
- [x] larger time step
- [ ] parameter estimation
- [ ] scalability with y
- [ ] include mapping from x to y
- [x] compute sensitivity w.r.t x for control purpose
- [ ] adding external loading and see if it is predictable given observation in y
- [ ] partial observed
- [ ] Direct Acyclic Graph and Bayesian