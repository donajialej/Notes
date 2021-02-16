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



# General to-do:

