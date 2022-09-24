# [Lecture 3.2 Learning parameters](https://www.youtube.com/watch?v=0Me1ywSlJE8)

![image](images/FeedForwardNN.png)

___

## Algorithm: `gradient_descent()`

___
$$
\begin{align}
&t \leftarrow 0; \\
&max\_iterations \leftarrow 1000; \\
&Initialize \enspace w_0, b_0; \\
& \mathbf{while} \enspace t \text{++}  \lt max\_iterations \enspace \mathbf{do} \\
    & \quad w_{t+1} \leftarrow w_t -\eta \nabla w_t \\
    & \quad b_{t+1} \leftarrow b_t -\eta \nabla b_t \\
& \mathbf{end}
\end{align}
$$

We can concisely write it as:

___

## Algorithm: `gradient_descent()`

___
$$
\begin{align}
& t \leftarrow 0; \\
& max\_iterations \leftarrow 1000; \\
& Initialize \enspace \theta_0 = [w_0, b_0]; \\
& \mathbf{while} \enspace t \text{++}  \lt max\_iterations \enspace \mathbf{do} \\
    & \quad\theta_{t+1} \leftarrow \theta_t -\eta \nabla \theta_t \\
& \mathbf{end}
\end{align}
$$
where $\Large \nabla \theta_t = [\frac{\partial \mathscr{L}(\theta)}{\partial w_t}, \frac{\partial \mathscr{L}(\theta)}{\partial b_t}]^T$

- Now, in this feedforward neural network, instead of $\theta = [w, b]$ we have $\theta = [W_1, W_2,...,W_L, b_1, b_2,...,b_L]$
- We can still use the same algorithm for learning the parameters of our model.

___

## Algorithm: `gradient_descent()`

___
$$
\begin{align}
& t \leftarrow 0; \\
& max\_iterations \leftarrow 1000; \\
& Initialize \enspace \color{red}{\theta_0 = [W_1^0,...,W_L^0, b_1^0,...,b_L^0];} \\
& \mathbf{while} \enspace t \text{++}  \lt max\_iterations \enspace \mathbf{do} \\
    & \quad\theta_{t+1} \leftarrow \theta_t -\eta \nabla \theta_t \\
& \mathbf{end}
\end{align}
$$
where $\color{red}{\Large \nabla \theta_t = [\frac{\partial \mathscr{L}(\theta)}{\partial W_{1,t}},...,\frac{\partial \mathscr{L}(\theta)}{\partial W_{L,t}},\frac{\partial \mathscr{L}(\theta)}{\partial b_{1,t}},...,\frac{\partial \mathscr{L}(\theta)}{\partial b_{L,t}}]^T}$

- Thus $\nabla \theta$ is composed of:
  - $\nabla W_1, \nabla W_2,..., \nabla W_{L-1} \in \mathbb{R}^{n \times n}, \nabla W_L \in \mathbb{R}^{k \times n}$
  - $\nabla b_1, \nabla b_2,..., \nabla b_{L-1} \in \mathbb{R}^n, \nabla b_L \in \mathbb{R}^k$
