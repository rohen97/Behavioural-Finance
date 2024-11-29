# Behavioural-Finance
Simulated consumption growth and calculate equilibrium values of the dividend-price ratio and expected market returns using Barberis, Huang, and Santos (2001) utility, plotting price-dividend ratios and equity premiums against  𝑏 0 b  0 ​  .



# Consider a Barberis, Huang and Santos (2001) economy with the following parameter choices 
# for the investor's utility function:
# delta = 0.99, gamma = 1, lambda = 2

Consumption growth has a lognormal distribution:
ln(g) = 0.02 +0.02*epsilon
where epsilon is a standard normal random variable. 

With these parameter choices, the risk-free rate is constant at 1.0303 per year. 
Simulate the distribution for consumption growth with at least 10,000 random draws for epsilon. 

Define x as one plus the dividend-price ratio for the market portfolio:
x = (1+P/D)*(D/P) = 1+D/P

and define the error term:
e(x) = 0.99 * b0 * E[nvhat(x*g)] + 0.99*x - 1
where utility from financial gain or loss is given by:
nvhat(R) = R - 1.0303 for R>=1.0303
nvhat(R) = 2 * (R - 1.0303) for R <1.0303

Calculate the equilibrium values of x for b0 in the range [0, 10], using an iterative procedure known as bisection search:
Step1:
    Set x– = 1 and x+ = 1.1. Use the simulated distribution of consumption growth to confirm that e(x–) < 0 and e(x+) > 0. 
    Hence solution for x must lie between x– and x+.
 Step2: 
     Set x = 0.5*(x– + x+), and use the simulated distribution of consumption growth to calculate e(x).
 Step3: 
     If |e(x)| < 10–4, then x is (close enough to) the solution.
 Step4:
     Otherwise, if e(x) < 0, then the solution lies between x and x+, so repeat the procedure from step 2 with x– = x.
 Step5:
     Otherwise, if e(x) > 0, then the solution lies between x– and x, so repeat the procedure from step 2 with x+ = x.

 Use x to calculate the price-dividend ratio for the market portfolio:
 P/D = 1/(x-1)
 Plot the price-dividend ratio (on the vertical axis) vs b0 (on the horizontal axis). 

 Also, calculate the expected market return:
 E[R(m)] = E[x*g]
 Plot the equity premium (on the vertical axis) vs b0 (on the horizontal axis). 

Briefly explain the economic significance of the investor's utility function for financial gain or loss [i.e., nuhat(R)], 
as well as the economic significance of the parameters b0 and lambda.
