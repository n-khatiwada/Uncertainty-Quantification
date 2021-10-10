# Simple Monte Carlo Simulation and Other Uncertainty Quantification Method
1. Describe an uncertainty quantification method, as Monte Carlo Method, Polynomial Chaos, Stochastic Collocation, Latin Hypercube
## Uncertainty Quantfication Method
Uncertainty quantification studies about the characteristics and reduction of uncertainties in computational and real world applications. In other words, say, some parameters of the model are not exactly known, and how likely other certain outcomes are determined and what are propagated erros of the outcomes; uncertainty quantification deals with this. In real world applications, uncertainties arise in measurement in various ways. Few of them are unknown parameters, varaibility in parameters, lack of knowledge of the system or ignorace of certain parameters in the proposed model, numerical approximations, and not to mention experimental uncertainty. Let's discuss UQ for different methods.



### Monte Carlo Method
It is a simulation based, probabilistic approach. Monte Carlo simulation transfers not only the original uncertainties into the final result with some statistical noise added, but also under some general conditions MC simulation transfers the original distribution of the data uncertainty into the final distribution of the results, with the same functional form, which becomes the basis for uncertainty quantification (UQ).



### Polynomial Chaos
Similar to Monte Carlo, it is also probabilistic approach, but it is not simulation based, rather functional-expansion based method. The idea is to approximate
<img src="https://render.githubusercontent.com/render/math?math=f(t, \omega)"> by series of polynomials.

<img src="https://render.githubusercontent.com/render/math?math=f(t, \omega) = \sum_{n=0}^{\infty}\hat{f_n}(t)\phi_n(\omega) "> 

where <img src="https://render.githubusercontent.com/render/math?math=\phi_n(\omega)"> are orthgonal polynomials of degree <img src="https://render.githubusercontent.com/render/math?math=n"> such as Legendre polynomials, Hermite polynomials, and <img src="https://render.githubusercontent.com/render/math?math=\hat{f_n}(t)"> are coefficeints.
Specifying the type of polynomials w.r.t input distributions, computing <img src="https://render.githubusercontent.com/render/math?math=\hat{f_n}(t)">, and choosing maximum order size, the statistical properties (including uncertainties) of <img src="https://render.githubusercontent.com/render/math?math=f(t, \omega)"> can be computed based on this approximation.

### Stochastic Collocation
Stochastic Collocation treats the given function as a black box which is evaluated at a fixed set of realizations. Outputs at these realizations are then used for approximation. Let <img src="https://render.githubusercontent.com/render/math?math=X"> be a random variable with probability density <img src="https://render.githubusercontent.com/render/math?math=F: \Omega \rightarrow \mathbb{R}"> and <img src="https://render.githubusercontent.com/render/math?math=f"> be a function <img src="https://render.githubusercontent.com/render/math?math=f: \Omega \rightarrow \mathbb{R}">. Then <img src="https://render.githubusercontent.com/render/math?math=\mathbb{E}[f]=\int_\Omega f(X)FdX"> with quadrature points <img src="https://render.githubusercontent.com/render/math?math=X_k"> for <img src="https://render.githubusercontent.com/render/math?math=k = 1, ..., N_q"> and correponding qudrature weights <img src="https://render.githubusercontent.com/render/math?math=w_k"> via <img src="https://render.githubusercontent.com/render/math?math=\mathbb{E}[f] \approx \sum_{k=1}^{N_q} w_kf(X_k)F(X_k)">.
The values of <img src="https://render.githubusercontent.com/render/math?math=f(X_k)"> are determined by treating the implementations of <img src="https://render.githubusercontent.com/render/math?math=f"> as a black box, which is evaluated at all <img src="https://render.githubusercontent.com/render/math?math=N_q"> collocation points.


### Latin Hypercube
It is a sampling approach to recreate the input distribution through less samples. The key to this method is stratification of the input probability distribution. Stratification divided the cumulative curve into equal intervals. A sample is then randomly taken from each interval of "stratification".


2. Let <img src="https://render.githubusercontent.com/render/math?math=X"> be a random variable which is normal distribution with <img src="https://render.githubusercontent.com/render/math?math=\bar{X}=0, \sigma=2">. Estimate mean and standard deviation of <img src="https://render.githubusercontent.com/render/math?math=X^2">.

For a normal distribution <img src="https://render.githubusercontent.com/render/math?math=\sim N(0, \sigma=2)">, <img src="https://render.githubusercontent.com/render/math?math=E[X] = \bar{X} = 0, E[X^4] = 3\sigma^4 = 48">.

Using relation, <img src="https://render.githubusercontent.com/render/math?math=Var(X) = E[X^2] - E[X]^2">, we get <img src="https://render.githubusercontent.com/render/math?math=E[X^2] = 4">

Similarly, <img src="https://render.githubusercontent.com/render/math?math=Var(X^2) = E[X^4] - E[X^2]^2 = 48 - 4^2 = 32">.

Thus the mean and standard deviation of <img src="https://render.githubusercontent.com/render/math?math=X^2"> are 4 and <img src="https://render.githubusercontent.com/render/math?math=4\sqrt{2}"> respectively.

Let's do this using **Monte-Carlo** method. See Jupyter Notebook above.
