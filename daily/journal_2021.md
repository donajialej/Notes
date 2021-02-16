# Daily notes
## Equivalence of Markov models 
Kylies model:  
@import "Kylie_model.png"

How about a simpler model? Just the green and red parts. 
@import "figures/2021-01-27_GMmeeting.png"

Read online that the simpler model doesn't have independence on the gates (Inactive comes only form open), and so it doesn't have a HH equivalent. 

But why can we say they are equivalent?

Mean field equations for 4 reations model:

$$ \frac{dC}{dt} = \delta CI + \beta O - (\alpha +\gamma)C \\
 \frac{dO}{dt} = \alpha C + \delta I - (\beta +\gamma)O \\
 \frac{dI}{dt} = \alpha CI + \gamma O - (\beta +\delta)I \\
 \frac{dCI}{dt} = \gamma C + \beta I - (\alpha +\delta)CI$$


Mean field equations for 3 reations model:

$$ \frac{dC}{dt} = \beta O - \alpha C \\
 \frac{dO}{dt} = \alpha C + \delta I - (\beta +\gamma)O \\
 \frac{dI}{dt} = \gamma O - \delta I $$

# General to-do:

