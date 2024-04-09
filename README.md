# Projet_M-thodes_Bay-siennes

Breslow and Clayton (1993) re-analyse 2 by 2 tables of cases (deaths from childhood cancer)and controls tabulated against maternal exposure to X-rays, one table for each of 120combinations of age (0-9) and birth year (1944-1964). The data may be arranged to the following
form.

Their most complex model is equivalent to expressing the log(odds-ratio) ψifor the table instratum i as

logψi = α + β1 * yeari + β2 * (yeari2- 22) + bi

bi ~ Normal(0, τ)

They use a quasi-likelihood approximation of the full hypergeometric likelihood obtained byconditioning on the margins of the tables.
We let r0i denote number of exposures among the n0i controls in stratum i, and r1i denotenumber of exposures for the n1i cases. The we assume r0i ~ Binomial(p0i, n0i), r1i ~ Binomial(p1i, n1i), logit(p0i) = µi and logit(p1i) = µi + logψi

Assuming this model with independent vague priors for the µi's provides the correct conditional likelihood.

Let's try to find these results with a gibbs sampler:

        mean         sd         MC_error  val2.5pc   median     val97.5pc 
alpha   0.579      0.062       0.001545   0.4587     0.5793     0.7037 
beta1  -0.04557    0.01553     3.929E-4  -0.07688   -0.0457    -0.01586 
beta2   0.007041   0.003084    8.953E-5   0.001018   0.007004   0.01314 
sigma   0.09697    0.06011     0.005036   0.02419    0.08059    0.2457 
