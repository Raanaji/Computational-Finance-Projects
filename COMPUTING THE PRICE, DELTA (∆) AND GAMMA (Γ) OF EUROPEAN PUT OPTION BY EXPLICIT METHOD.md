## COMPUTING THE PRICE, DELTA (∆) AND GAMMA (Γ) OF EUROPEAN PUT OPTION BY EXPLICIT METHOD

1. We price a European Put option under GBM with the parameters below by solving the BS PDE directly with appropriate boundary conditions and compare our solutions with the option prices computed using the matlab built in function `blsprice`.

$$
S(0) = 100,r = 0.03,q = 0.05,σ = 0.2,K = 100,T = 1.
$$



The price of the option $$V (S, τ )$$ should satisfy the PDE below with the initial

condition $$(τ = T − t)$$ being the payoff of the option:
$$
∂V =\frac{1}{2} \frac{\partial^2V}{\partial S^2}\sigma^2S^2+(r−q)S\frac{\partial V}{\partial S} −rV
$$

$$
V (S, 0) = max (K − S, 0)
$$

Using the boundary condition below for European put option:
$$
V(S_{min},τ)=e^{−rτK}, V(S_{max},τ)=0.
$$

2. After having computed all put option prices $V (S, T )$ on the domain, for $j =1,...,N +1$.

$$
D=\bigg(S_j =S_{min}+(j−1) × dS; \;dS=\frac{(S_{max}−S_{min})}{N},\bigg)
$$

we then compute ∆ and Γ of the above put option using the approximation below and compare our numbers with ∆ and Γ computed using the matlab built in functions` blsdelta` and `blsgamma`.
$$
∆(S_j)=\frac{V(S_{j+1},T)−V(S_{j−1},T)}{2×dS}, j=2,...,N.
$$

$$
Γ(S_j) = \frac{V(S_{j+1},T)−2V(S_{j−1},T)+V(S_{j−1},T)}{dS^2}, j = 2,...,N
$$



3.  Finally we plot both $\Delta$ and $\Tau$ agains the stock price $S$.