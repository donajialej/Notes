# Daily notes
# Equivalence of Markov models 
Kylies model:  
![Model](figures/Kylie_model.png)

How about a simpler model? Just the green and red parts. 
![Model](figures/2021-01-27_GMmeeting.png)

~~Read online that the simpler model doesn't have independence on the gates (Inactive comes only form open), and so it doesn't have a HH equivalent.~~ I was comparing the wrong models. 
~~Mean field equations for 3 reations model:~~ I erased since we aren't interested on it anymore.

Update on FEB 14th: need to compare 4 state model to 2 state model (a and r).

Mean field equations for 4 reations model:

$$ \frac{dC}{dt} = \delta CI + \beta O - (\alpha +\gamma)C \\
 \frac{dO}{dt} = \alpha C + \delta I - (\beta +\gamma)O \\
 \frac{dI}{dt} = \alpha CI + \gamma O - (\beta +\delta)I \\
 \frac{dCI}{dt} = \gamma C + \beta I - (\alpha +\delta)CI$$

And the the 2 state model:
$$ \frac{da}{dt} = \alpha(1-a) - \beta a \\ 
\frac{dr}{dt} = \delta(1-r) - \gamma r $$

So, if $ O= ar, C = r(1-a), I= a(1-r), CI = (1-a)(1-r)$, the 2 state model is equivalente (mean fied) to the 4 reaction model mean field.

How can I prove if they are also the same in distribution? Let;s get to simulations

# Simulating stoch systems with time varying rates

So, now the waiting times are not just $\alpha * C(t)$, but the integral from the previous time to the step time:
$$ \int_t^{t +\Delta t} \alpha_j(s) ds$$ 

And my model actually is sipler than thiers since we have explicit formula for V(t)and we have  $g_{Kr}$, and $E_K$  const, so no need do the DE part and model $I_{Kr}$ as:
$$I_{Kr}(t) = g_{Kr} O(t) (V(t)-E_K)$$

So this works for the mean field one, but does it work for the general case? like $O =$ number/fraction of open chanels at time t? 

Let's:
1. Sim O<->C with const rates (no I yet)
    - so the jump is $\alpha \Delta t X(\Delta t)$

1. Sim O<->C with step type V (no I)
    - Here, lets say: $$\alpha(t) =  \begin{cases} \alpha_1 & t<t^* \\  \alpha_2  &t>t^* \end{cases} $$
    So, the jump is: $$ =  \begin{cases} \alpha_1 \Delta t X(t+\Delta t) & t+  \Delta t <t^* \\ (\alpha_1 (t^*-t) +\alpha_2(t+\Delta t - t^*))X(t+\Delta t)  & t<t^* <t+\Delta t \\  \alpha_2 \Delta t X(t+\Delta t) &t>t^* \end{cases} $$

    So in this case we do need to stop and solve what is happening with $\Delta t$ with detail for all the possible reactions when we are "closed" to $t^*$.

1. Sim O<->C with sine V (no I)
    - Here we can integrate V(t) directly! Can we? I just remember that $\alpha$'s are of the form $\exp(kV(t))$ ... so will need to integrate this numerically 
    $$\int_t^{t+\Delta t} P_i \exp(P_{i+1} V(s)) X(s) ds $$

### References

I'm mainly looking at these references: 
-  Stochastic Representations of Ion Channel Kinetics and Exact Stochastic Simulation of Neuronal Dynamics, David F. Anderson et al, 2017 (arxiv version)
- Simulation of biochemical reactions with time-dependent rates by the rejection-based algorithm Vo Hong Thanh and Corrado Priami, 2015, J of Chem phys. DOI: https://doi.org/10.1063/1.4927916
- RELATIONSHIP BETWEEN MEMBRANE EXCITABILITY AND SINGLE CHANNEL OPEN-CLOSE KINETICS, JOHN R. CLAY AND LOUIS J. DEFELICE, J biophy, 1983
- Spontaneous Action Potentials due to Channel Fluctuations, Carson C. Chow and John A. White, Biophy J, 1996
- A modified next reaction method for simulating chemical systems with time dependent propensities and delays, David F. Anderson, J. Chem. Phys. 127, 214107 (2007); DOI: https://doi.org/10.1063/1.2799998 
    - _More for delayed systems, for the time dependent explains only the basic idea of waiting integral amount of time_


Extras:
- Strong Error Analysis of the -Method for Stochastic Hybrid Systems, Martin G. Riedler and Girolama Notarangelo, 2018, arxiv version
- Modeling the Stochastic Gating of Ion Channels, Ch 11 of some book, Gregory D. Smith
- A perturbation analysis of spontaneous action potential initiation by stochastic ion channels, James P. Keener and Jay M. Newby
- Breakdown of fast-slow analysis in an excitable system with channel noise Jay M. Newby, Paul C. Bressloff and James P. Keener, 2013, arxiv version
- Mathematical and Computational Study of Markovian Models of Ion Channels in Cardiac Excitation, Tomáš Starý, their thesis, Exeter 2016
- A Gillespie Algorithm for Non-Markovian Stochastic Processes, Naoki Masuda Luis E. C. Rocha, 2018 SIAM, DOI. 10.1137/16M1055876








