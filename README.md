# faq-test

## Category 2

## Category 3

### rfb rule

<details>
<summary>

#### Does the multiplier m reduce the advice over time?

</summary>

There is sometimes the incorrect perception that the multiplier of the rfb and chr rules continuously decreases the catch advice over time. The multiplier of the empirical harvest control rules is a tuning parameter that ensures that the advice follows the ICES precautionary approach. The components of the harvest control rules are multiplicative, this means that the multiplier can be thought of as adjusting the target of the harvest control rules, i.e. the reference length in component f of the rfb rule and the target harvest rate of the chr rule. This principle is illustrated in the following equation for the rfb rule:

$$A_{y+1} = A_y  r f b x = A_y  r L_{y-1}/L_{F=M}$$


$$
A_(y+1)=A_y  r f b x=A_y  r L_(y-1)/L_(F=M)  b x=A_y  r L_(y-1)/(〖L'〗_(F=M)/x) b=A_y  r L_(y-1)/〖L'〗_(F=M)  b
$$

where $A_{y+1}$ is the new catch advice, $A_y$ the previous catch advice, $r$, $f$, and $b$ the components of the rfb rule, $x$ the multiplier, $L_{y-1}$ the mean catch length, and $L_{F=M}$ the MSY proxy reference length.

Response copied from WKLIFE XI report (ICES, 2023, Section 2.2.8, page 28):
* ICES. 2023. Eleventh Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XI). ICES Scientific Reports. 5:21. 74 pp. (https://doi.org/10.17895/ices.pub.22140260).

</details>

<details>
<summary>

#### Criticism that the new rule (rfb) leads to even lower advice than the 2 over 3 rule

</summary>

The 2 over 3 rule was implemented in 2012 as an interim measure based on the best available science at that time. Re-evaluation of this method through simulation has shown that the 2 over 3 rule does not follow the ICES precautionary approach and can increase the risk of stock depletion over time. This means that the catch advice from the 2 over 3 rule in many cases was higher than it should have been. The new rfb rule was implemented after extensive simulation testing and review and was designed to explicitly follow the ICES precautionary approach and the MSY approach. This means that the catch advice from the rfb rule may be lower than from the 2 over 3 rule but this is required to follow ICES management objectives.

</details>

<details>
<summary>

#### Why does the advice go down even if the index is going up?

</summary>

* The previous 2 over 3 rule calculated catch advice based on the trend from a bio-mass index. In addition to this, the rfb rule also considers (1) the exploitation of the stock based on catch-length data and (2) includes a biomass safeguard that reduces the catch advice if the biomass index falls below a trigger value. The catch advice calculated with the rfb rule is a result of all these considerations combined. Furthermore, the trend in the biomass index is calculated by using data from the most recent five years, i.e. an increase in the index in a single year does not necessarily result in a positive biomass trend.
</details>

<details>
  <summary>  
    
  #### What to do if new life-history parameters such as L∞ are found; is there a need to recalculate things back in time?
  
  </summary>
  
  * There is no need to annually update life-history parameters. If new growth pa-rameters are available and these are substantially different from previous esti-mates, these should be used. To ensure consistency in the calculation, derived values such as the reference length LF=M should also be updated and the historical mean catch length compared to this new reference length. Growth parameters and derived metrics such as the reference length should be periodically reevalu-ated, e.g. every 3-5 years, following a similar schedule to benchmarks for Catego-ry 1 data-rich stocks, but kept constant in-between unless there is compelling new evidence for a change.
</details>

<details>
  <summary>  
    
  #### Which life-history parameters (or strategies) matter when the von Bertalanffy growth model might not be appropriate

  </summary>
  * The individual growth rate (von Bertalanffy k) is only used to decide which method or multiplier is used and a rough estimate is enough, e.g. is k below 0.2/year or not. The only other growth parameter used for the rfb rule is the as-ymptotic length L∞, which is used in the calculation of the reference length LF=M but the actual shape of the growth curve is less important.
</details>

<details>
<summary>  
    
#### Can the advice interval for the rfb rule (default: biennial) be changed?

</summary>

* The ICES technical guidelines recommend the implementation of the rfb rule with a biennial advice interval (ICES, 2022). WKLIFE XI (ICES, 2023) was asked if the rfb rule could be applied on an annual basis and concluded that this is unlike-ly to increase the risk of stock depletion but has the undesirable feature of reduc-ing the long-term catch and should only be used in exceptional cases when asked for by ICES advice requesters (ICES, 2023, 2.2.4.1, page 21). Other advice intervals (from one to five years) were included in the generic testing of the rfb rule (Fischer et al., 2021a,b) but the biennial advice interval appeared to work best. Longer advice intervals can reduce the reactivity of the rfb rule and may increase the risk of stock depletion because the catch cannot be reduced fast enough.

_References_
* Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021a. Using a genetic algorithm to optimize a data-limited catch rule. ICES Journal of Marine Science, 78: 1311–1323. (https://doi.org/10.1093/icesjms/fsab018).
* Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021b. Application of explicit precautionary principles in data-limited fisheries management. ICES Journal of Marine Science, 78: 2931–2942. (https://doi.org/10.1093/icesjms/fsab169).
* ICES. 2022. ICES technical guidance for harvest control rules and stock assessments for stocks in categories 2 and 3. In Report of ICES advisory committee, 2022. ICES advice 2022, section 16.4.11. 20 pp. International Council for the Exploration of the Sea. (https://doi.org/10.17895/ices.advice.19801564).
* ICES. 2023. Eleventh Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XI). ICES Scientific Reports. 5:21. 74 pp. (https://doi.org/10.17895/ices.pub.22140260).

</details>
