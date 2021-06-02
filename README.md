# ENERCON
1. Describe an uncertainty quantification method, as Monte Carlo Method, Polynomial Chaos, Stochastic Collocation, Latin Hypercube
## Uncertainty Quantfication Method
Uncertainty quantification studies about the characteristics and reduction of uncertainties in computational and real world applications. In other words, say, some parameters of the model are not exactly known, and how likely other certain outcomes are determined and what are propagated erros of the outcomes; uncertainty quantification deals with this. In real world applications, uncertainties arise in measurement in various ways. Few of them are unknown parameters, varaibility in parameters, lack of knowledge of the system or ignorace of certain parameters in the proposed model, numerical approximations, and not to mention experimental uncertainty. Let's discuss UQ for different methods.



### Monte Carlo Method
It is a simulation based, probabilistic approach. Monte Carlo simulation transfers not only the original uncertainties into the final result with some statistical noise added, but also under some general conditions MC simulation transfers the original distribution of the data uncertainty into the final distribution of the results, with the same functional form, which becomes the basis for uncertainty quantification (UQ).



### Polynomial Chaos
Similar to Monte Carlo, it is also probabilistic approach, but it is not simulation based, rather functional-expansion based method. The idea is to approximate $ f(x) $ by series of polynomials
<img src="https://render.githubusercontent.com/render/math?math=x_{1,2} = \frac{-b \pm \sqrt{b^2-4ac}}{2b}">
Hello


### Stochastic Collocation




### Latin Hypercube
