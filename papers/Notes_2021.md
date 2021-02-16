
# Cardiac Noise 

---

## Nonstationary Noise Analysis and Application

Paper by  STEFAN H. HEINEMANN and FRANCO CONTI

### Some notes


Non-stationary fluctuations on the macro-scale can tell you about the single-channel dynamics
- Uses whole-cell recordings with high signal to noise ratio
- Also acount the analysis for patch-clamps transient artifacts and drift. by:
    1. account & estimate recordings variances
    1. rigorous variance vs current fitting
    1. objective discard of load fits.

**Bio-model:** bovine adrenal chromatin cells -> to estimate temperature and presure dependence of the conductence of V-activated ion channels

**Non-statonary annalysis**

Scales: $i$ -> micro, $I$ -> macro, $\gamma$ -> macro.

- Asume a binomial dist. for the number of open channels with parameters $N, p_\text{open}$. 
- $i$ single channel current
- $I(t) = iNp_o(t)$  mean current 
- $\sigma^2(t)= iNp_o(t)(1-p_o(t))$ variance
    -  Writing the variance on terms of N and current: $\sigma^2(I)= Ii-I/N$
    - you can fit $i$ and $N$ from here!
- In a sense, you calculate $\sigma^2, I$ from experiments, and $i,N$ parameters estimates.
- Also, relate the single channel current w/ conductance: $\gamma =\frac{i}{E_{com}-E_{rev}}$
    - $\implies i$<->V linear $\iff \gamma$ constant
    - $E_{com}$ voltage-clamp potential
    - $E_{rev}$ reversal potential

_BEGGING parenthesis:_ **Effect of series resitance**
- $R_s$ = series resistance, determined by the electrical access from the pipette electrode to the cell membrane.
    - Can be compensated for but not perfectly
    - Could cause arthificial interactions between the single channels, hence breaking the independence assumption => need small errors here.
    - I found: 
        - For voltage clamps: $V_{out} = \frac{E_{com}R_m + V_mR_s}{R_s+R_m}$, where $E_com$ is the command voltage (the voltage-clamp), $R_m$ membrane resitance, $V_m$ resting potential, $R_s$ series resistance
        - $R_s << R_m \implies V_{out} \approx E_{com}$ -> the voltage clamp "controls"
        - $R_s >> R_m \implies V_{out} \approx V_m$ -> we don't get any info.
- Tge $R_s$ limits how quickly the cell can change the capacitance by the pippette $C_p$, limiting the results for fast voltage changes.

_END parenthesis_

- For small values of $IR_s$: $i=i^*-\gamma^*IR_s$, where * referes ideal measures
    - Similar equation for the variance: $\sigma^2(I)= Ii^*-I/N^*$, but this N is not the same
    - The papers gives the correction for this case: **$R_s$ causes the wrong estimate of the number of channels by the factor $(1+N\gamma R_s)^{-1}$** 

### What I want to do:
- Use the above formula to check how the variance works

So I need: 
- Mean currents and variances
- For the variance and assuming the drift has been corrected:
    - $\sigma^2_I= E(\delta \xi (t)^2)/2$, where $\delta\xi(t)$ is difference of consecutive records 
        - with same I ?
        - not sure if $\delta\xi(t)$  is the difference or the square differences

### My questions to Gary:

Older paper. *Have experimental things changed since for single sodium channels?*
- fixed temperature -> apparently not
- narrow voltage ranges (⇒ a frequency of channels opening)  -> Aplies to Na+, not our case.
- background noise -> Gary didn't mention much here

### Interesting references

Membranes, channels & noise, book, 1984
- Ch Non stat. noise analysis by F. J. Sig worth → feels like a nice fill in of the current chapter
- Ch. Info of single channel data -> estimation of N (page 221), binomial asumption,



---
---

## Kylie's sine protocol

### Paper

**Math models of cardiac electro phsio @ core of protocols to replace human clinical trials!**

Short informative protocols: Rather than traditional square-wave voltage clamps, we fitted a model to the current evoked by a novel sum-of-sinusoids voltage clamp that was only 8 s long. All exp. data from a single cell

They found great variability in the fits even when comparing models for the same conditions. fig 1.
The traditional approach dates to HH model (1952) and fits peak currents to fixed voltages

- AIM: with the 8s sum of sinusoids V clamps will explore & characterise the kinetics of hERG
    1. create the protocol
    1. recod currents from CHO
    1. parameterize math models
    1. predict other V clamps.


It asks for a conceptual shift: channel kinetics, summarized by math models instead of I-V and $\tau$-V curves.

Folow up problem: may need ore complex model to campture the exp. behaviour.

#### My questions to Gary:
_why did you pick sinosoidal wave?_ A  bit of a random choise by someone else @ the team pick it, maybe related to Fourier Transforms.

_Summary curves?_ Read Michael's 4 ways of fitting paper

_Has it been done in myocites?_ No, there is no way to isolated Myocytes yet ... Hence use of  animal, stem cells, etc

The parameter posteriors here were narrow, but maybe the vaviability of parameter value, among cells comes from experimental errors, or others -> so Chon continued this with a paper on V clamps arthifacts, ie, we need to fill out the details of the data generativos process

### Model and data

@import "figures/Kylie_model.png"


Kylies new protocol: 
@import "figures/Kylie_protocol.png"

Other protocols:
@import "figures/Kylie_otherProtocls.png"
@import "figures/Kylie_otherProtocls.png"


_how do I simulate that?_
_how do I measuer the noise?, correlations?_

---
---


## Biology "dictionary"

- **I$_{kr}$**: Potassium current. Rapid delayed rectifier. Related to **KCNH2 gene ==hERG**. Traditionally name by the currents, now more about the genes.  Ikr is best know as a re polarising cardiac ion current but also important role, @ brain, gastro track, uterie contractions, cell proliferation + apoptosis,and cancer progression. Suceptible to pharma compounds, which are related to drug-induce pro-arrhythmic risk.

- **CHO cells**  Chinee Hamster Ovary cells. It is a cell line that oer-express **hERG1a**. hERGa == One of the gene products of hERG.

---
---
## Markdown tutorial

---
Text attributes _italic_, **bold**, `monospace`. 

Horizontal rule:


Strikethrough: ~~strikethrough~~


Bullet list:
- apples
- oranges
    - hola
* pears
    * hola

Numbered list: 
1. lather 
1. rinse 
1. repeat

$$ x=1 $$
