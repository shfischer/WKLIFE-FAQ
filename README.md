# WKLIFE Frequently Asked Questions (FAQ) on the ICES data-limited methods

This page contains Frequently Asked Questions (FAQ) on the ICES data-limited methods and the responses from WKLIFE.

So far, the questions and responses are copied from the ICES WKLIFE XII report (Annex 6):

> ICES. 2023. Workshop on the Development of Quantitative Assessment Methodologies based on Life-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XII). ICES Scientific Reports. 5:103. 111 pp. (<https://doi.org/10.17895/ices.pub.24581343>).

## Category 2

### SPiCT

<details>

<summary>

#### Is the generic SPiCT harvest control rule appropriate for long-lived species such as por-beagle shark?

</summary>

TODO

*Question source: WGEF for WKLIFE XII 2023*

</details>

## Category 3

### General comments

<details>

<summary>

#### The "precautionary multiplier" of the ICES Category 3 advice rule reduces the advice over time

</summary>

-   ICES uses three methods to calculate the advice for Category 3 data-limited stocks (excluding short-lived species). These are the "rfb rule" for species with slower individual growth, the "chr rule" for stocks with medium individual growth, and the "rb rule" for stocks for which no reliable length data from the catch is available. These three methods include a multiplier in the calculation of the catch advice, which ensures that the catch advice leads to long-term precautionary management advice. Precautionary in this context means that the risk of the stock being depleted is reduced to a low level.
-   For the rfb rule and the chr rule, this multiplier does not lead to a continuous reduction of the catch advice every time the rules are applied. Instead, the multiplier acts as a correction factor and changes the management targets of these advice rules. If a stock is estimated to be below this corrected management target, the advice value will be reduced. However, if a stock is estimated to be at or above this management target, the multiplier does not reduce the advice further.
-   The third advice rule, the "rb rule", was only proposed as a method of last resort and should be avoided if possible. This rule is used when no reliable length data are available. Contrary to the rfb and chr rules, the rb rule does not include a management target and simply adjusts the catch advice based on the stock trend, as observed with the stock index. The rb rule likely reduces the catch advice over time with the multiplier. This is needed to ensure that (1) the management advice is precautionary in the long term, (2) the depletion risk is not greater than for the other methods, and (3) the depletion risk does not increase over time. This situa-tion can be avoided when length data are available that are representative of the catch of the stock. These length data allow the application of the rfb or chr rules, which do not lead to a continuous reduction in the catch advice. A single year of length data can be enough to move away from the rb rule to either the rfb or chr rule.

*Question source: Scottish Fishermen's Federation for WKLIFE XII 2023*

</details>

<details>
    
<summary>

#### Changes to the reference values over time

</summary>

The rfb, rb, and chr rules include reference values such as a trigger value for the biomass index ($I_\text{trigger}$), the length at first capture ($L_c$), a length reference value ($L_{F=M}$), or the target harvest rate $F_\text{proxy,MSY}$. In general, these reference values should be set when the methods are applied for the first time and should not be updated for every application. The values could be periodically re-evaluated every few years, similar to benchmarks for data-rich stocks. However, if the entire biomass index series is updated for a new application, for example by using delta gam modelled index, the reference values should be updated accordingly (while using the same historical period for $F_\text{proxy,MSY}$ and ($I_\text{trigger}$)).

_Response from WKLIFE XIII 2024_

</details>

<details>
    
<summary>  
    
#### Changes to the biomass index trigger ($I_\text{trigger}$) value over time

</summary>

See the response to [changes to the reference values over time](#changes-to-the-reference-values-over-time) for a general response.

_Specific considerations for the biomass index trigger:_

The biomass safeguard $b$ of the rfb, rb, and chr rules is defined as

$$b = \text{min} \left( 1, \frac{I_{y-1}}{I_\text{trigger}} \right)$$

where the current biomass index value ($I_{y-1}$) is compared to a trigger value ($I_\text{trigger}$). If the most recent biomass index value falls below $I_\text{trigger}$, the biomass safeguard reduces the advised catch. In the absence of further information, $I_\text{trigger}$ is generically defined based on lowest observed biomass index value ($I_\text{trigger}= 1.4I_\text{loss}$).

During the first application of the rfb/rb/chr rules, $I_\text{loss}$ is typically defined as the biomass index value in a specific year. In subsequent applications of the rfb/rb/chr rule, $I_\text{loss}$ should *NOT* be re-defined with biomass index values from new data years.

Some biomass indices are derived by modelling or standardising survey data. This means that the biomass index time series may. In this case, the calculation of $I_\text{trigger}$ should be based on the new value for $I_\text{loss}$ from the same reference year (defined during the first application of the rfb/rb/chr rule). The R package `cat3advice` allows the definition of $I_\text{trigger}$ based on a reference year (see the [package vignette](https://github.com/shfischer/cat3advice/blob/main/vignettes/cat3advice.md#biomass-safeguard-b) for more details):

```
library(cat3advice)
data(ple7e_idx) # example data
# define Itrigger with a reference year for Iloss
b(ple7e_idx, yr_ref = 2007)
```

The reference year for $I_\text{loss}$ should generally not be changed. In a modelled biomass index, the year in which $I_\text{loss}$ is observed may change to a different (historical) year. In such a case, the appropriateness of the biomass index to provide catch advice should be carefully considered. Should the change be caused by a correction of errors in historical survey data, this may warrant a change of $I_\text{loss}$ but will need to be documented (and possibly reviewed).

_Response from WKLIFE XIII 2024_

</details>

<details>

<summary>

#### Length-frequency distributions: what if they are not representative

</summary>

-   to do

*Response: WKLIFE XIII 2024*

</details>


### rfb rule

<details>

<summary>

#### Does the multiplier m reduce the advice over time?

</summary>

There is sometimes the incorrect perception that the multiplier of the rfb and chr rules continuously decreases the catch advice over time. The multiplier of the empirical harvest control rules is a tuning parameter that ensures that the advice follows the ICES precautionary approach. The components of the harvest control rules are multiplicative, this means that the multiplier can be thought of as adjusting the target of the harvest control rules, i.e. the reference length in component f of the rfb rule and the target harvest rate of the chr rule. This principle is illustrated in the following equation for the rfb rule:

$$A_{y+1} = A_y\ r\ f\ b\ m = A_y\ r\ \frac{L_{y-1}}{L_{F=M}}\ b\ m = A_y\ r\ \frac{L_{y-1}}{L_{F=M}/m}\ b = A_y\ r\ \frac{L_{y-1}}{L'_{F=M}}\ b$$

where $A_{y+1}$ is the new catch advice, $A_y$ is the previous catch advice, $r$, $f$, $b$ and the multiplier $m$ are the components of the rfb rule,  the multiplier, $L_{y-1}$ the mean catch length, and $L_{F=M}$ the MSY proxy reference length.

Response copied from WKLIFE XI report (ICES, 2023, Section 2.2.8, page 28): 
* ICES. 2023. Eleventh Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XI). ICES Scientific Reports. 5:21. 74 pp. (<https://doi.org/10.17895/ices.pub.22140260>).

*Question source: WGDEEP for WKLIFE XII 2023*

</details>

<details>

<summary>

#### Criticism that the new rule (rfb) leads to even lower advice than the 2 over 3 rule

</summary>

The 2 over 3 rule was implemented in 2012 as an interim measure based on the best available science at that time. Re-evaluation of this method through simulation has shown that the 2 over 3 rule does not follow the ICES precautionary approach and can increase the risk of stock depletion over time. This means that the catch advice from the 2 over 3 rule in many cases was higher than it should have been. The new rfb rule was implemented after extensive simulation testing and review and was designed to explicitly follow the ICES precautionary approach and the MSY approach. This means that the catch advice from the rfb rule may be lower than from the 2 over 3 rule but this is required to follow ICES management objectives.

*Question source: WGDEEP for WKLIFE XII 2023*

</details>

<details>

<summary>

#### Why does the advice go down even if the index is going up?

</summary>

The previous 2 over 3 rule calculated catch advice based on the trend from a bio-mass index. In addition to this, the rfb rule also considers (1) the exploitation of the stock based on catch-length data and (2) includes a biomass safeguard that reduces the catch advice if the biomass index falls below a trigger value. The catch advice calculated with the rfb rule is a result of all these considerations combined. Furthermore, the trend in the biomass index is calculated by using data from the most recent five years, i.e. an increase in the index in a single year does not necessarily result in a positive biomass trend.

*Question source: WGDEEP for WKLIFE XII 2023*

</details>

<details>

<summary>

#### What to do if new life-history parameters such as $L_\infty$ are found; is there a need to recalculate things back in time?

</summary>

There is no need to annually update life-history parameters. If new growth pa-rameters are available and these are substantially different from previous esti-mates, these new ones should be used. To ensure consistency in the calculation, derived values such as the reference length LF=M should also be updated and the historical mean catch length compared to this new reference length. Growth parameters and derived metrics such as the reference length should be periodically reevalu-ated, e.g. every 3-5 years, following a similar schedule to benchmarks for Catego-ry 1 data-rich stocks, but kept constant in-between unless there is compelling new evidence for a change.

*Question source: WGDEEP for WKLIFE XII 2023*

</details>

<details>

<summary>

#### Which life-history parameters (or strategies) matter when the von Bertalanffy growth model might not be appropriate

</summary>

-   The individual growth rate (von Bertalanffy $k$) is only used to decide which method or multiplier is used and a rough estimate is enough, e.g. is $k$ below $0.2\ year^{-1}$ or not. The only other growth parameter used for the rfb rule is the asymptotic length L∞, which is used in the calculation of the reference length $L_{F=M}$ but the actual shape of the growth curve is less important.

*Question source: WGDEEP for WKLIFE XII 2023*

</details>

<details>

<summary>

#### Can the advice interval for the rfb rule (default: biennial) be changed?

</summary>

-   The ICES technical guidelines recommend the implementation of the rfb rule with a biennial advice interval (ICES, 2022). WKLIFE XI (ICES, 2023) was asked if the rfb rule could be applied on an annual basis and concluded that this is unlike-ly to increase the risk of stock depletion but has the undesirable feature of reduc-ing the long-term catch and should only be used in exceptional cases when asked for by ICES advice requesters (ICES, 2023, 2.2.4.1, page 21). Other advice intervals (from one to five years) were included in the generic testing of the rfb rule (Fischer et al., 2021a,b) but the biennial advice interval appeared to work best. Longer advice intervals can reduce the reactivity of the rfb rule and may increase the risk of stock depletion because the catch cannot be reduced fast enough.

*References* 

* Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021a. Using a genetic algorithm to optimize a data-limited catch rule. ICES Journal of Marine Science, 78: 1311–1323. (<https://doi.org/10.1093/icesjms/fsab018>). 

* Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021b. Application of explicit precautionary principles in data-limited fisheries management. ICES Journal of Marine Science, 78: 2931–2942. (<https://doi.org/10.1093/icesjms/fsab169>). 

* ICES. 2022. ICES technical guidance for harvest control rules and stock assessments for stocks in categories 2 and 3. In Report of ICES advisory committee, 2022. ICES advice 2022, section 16.4.11. 20 pp. International Council for the Exploration of the Sea. (<https://doi.org/10.17895/ices.advice.19801564>). 

* ICES. 2023. Eleventh Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XI). ICES Scientific Reports. 5:21. 74 pp. (<https://doi.org/10.17895/ices.pub.22140260>).

*Question source: WGDEEP for WKLIFE XII 2023*

</details>

<details>

<summary>

#### Allow changes to the assumption of $M/k=1.5$ for the length-based indicator

</summary>

The assumption of $M/k=1.5$ is solely used for a simple calculation of the reference length $L_{F=M}$. This simplification of reality was shown to be appropriate in simulation testing even if the reality (operating model) was different and the parameterisation of the rfb rule with its multipliers accounts for potential deviations. Deviations from $M/k=1.5$ are possible following Jardim et al. (2015; Appendix A):

$$L_{F=γM,k=θM} = \frac{\theta L_\infty + L_c (\gamma + 1)}{\theta + \gamma + 1}$$

where $\gamma$ links the natural mortality $M$ to fishing mortality $F$ as the proxy for MSY (set to 1 for $L_{F=M}$), $\theta$ links the von Bertlanffy $k$ to $M$, $L_\infty$ is the asymptotic length and $L_c$ is the length at first capture.

The function for the calculation of the reference length in the `cat3advice` R package (`Lref()`) includes an argument (`Mk`) to change the $M/k$ ratio to any user-defined value.

*References* 

* Jardim, E., Azevedo, M., and Brites, N. M. 2015. Harvest control rules for data-limited stocks using length-based reference points and survey biomass indices. Fisheries Research, 171: 12–19. (<https://doi.org/10.1016/j.fishres.2014.11.013>).

*Question source: WGDEEP for WKLIFE XII 2023*

</details>

<details>

<summary>

#### What to do when there are missing index values, can values be interpolated?

</summary>

In general, interpolating missing index values is not recommended because this would imply information is available when it does not exist. This is an area that needs further consideration.

*Question source: WGDEEP for WKLIFE XII 2023*

</details>

<details>

<summary>

#### When calculating the mean catch length, should the length class corresponding to the length of first capture ($L_c$) be included?

</summary>

The ICES technical guidelines specify that only length classes above $L_c$ should be considered. Whether $L_c$ is included or not does not really matter as long as it is done consistently between years. The `cat3advice` R package function for calculating mean catch length (`Lmean`) includes $L_c$ by default, but this can be turned off by setting the argument `include_Lc=FALSE`.

*Question source: WGEF for WKLIFE XII 2023*

</details>

<details>

<summary>

#### For some stocks, catch length data can be sparse (e.g. only landings, not discards or nei-ther). Could survey length data be used instead?

</summary>

Some work on this issue was presented at WKLIFE XII (ICES, 2023). The conclusion was that it might be possible to use survey length data as a proxy if no or insufficient (commercial) length data are available. The length at first capture $L_c$ should still be estimated from catch data to account for fisheries selectivity because the $L_c$ from survey data might be too low and bias the reference length $L_{F=M}$ (which is on the assumption of knife-edged fisheries selectivity).

*References* 

* ICES. 2023. Workshop on the Development of Quantitative Assessment Methodologies based on Life-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XII). ICES Scientific Reports. 5:103. 111 pp. (<https://doi.org/10.17895/ices.pub.24581343>).

*Question source: WGEF for WKLIFE XII 2023*

</details>

<details>

<summary>

#### Some stocks have an $I_{loss}$ near zero, which is at the start or end of the time series, so using $I_{trigger} = 1.4 I_{loss}$ is not appropriate. In such cases, WGNSSK and WGEF used the 20th quantile of the time series. Is this approach appropriate?

</summary>

ICES technical guidelines specify that $I_{trigger}$ is a value below which a stock’s productivity is thought to be impaired and offer a calculation based on the lowest observed index value, $I_{loss}$, if no other information is available. If index values are very low or questionable at the beginning, these values could be removed. Using the 20th percentile of the index time seems appropriate and will lead to a larger $I_{trigger}$. This means the biomass safeguard will already be applied at higher index values and is more precautionary than the default approach.

*Question source: WGEF for WKLIFE XII 2023*

</details>

<details>

<summary>

#### Should there be more tests of the multiplier $m$ for elasmobranch species?

</summary>

The Category 3 empirical harvest control rules (rfb/rb/chr) were tested for a wide range of scenarios and stocks, including slow-growing and long-lived species and elasmobranchs. These methods were tuned to be precautionary in the long term, so there is no immediate need for additional testing. Stock-specific simulations for specific stocks are encouraged, and the ICES technical guidelines encourage such work. The WKLIFE roadmap and proposed ToRs for the next WKLIFE meeting also include work on specific life histories, including considerations for elasmobranchs.

*Question source: WGEF for WKLIFE XII 2023*

</details>

<details>

<summary>

#### Concerns over the appropriateness of the new rfb rule with the risk derived from simulations. \| Are the simulations wide enough? \| The WKLIFE X report mentioned that outputs were sensitive to a number of starting specification

</summary>

The implementation of the new WKLIFE X methods for Category 3 stocks (rfb/rb/chr rules) is the culmination of more than five years of scientific work. The work has been developed under the supervision of the WKLIFE workshops, where it has also been reviewed (see reference list below). Furthermore, the scientific work has been pub-lished in five scientific articles in internationally renowned scientific journals, where the work was peer-reviewed by several independent reviewers (see reference list below). The simulations accounted for many scenarios, including different life histories, depletion scenarios, and sensitivity analyses. The methods were developed generically so that they are applicable to any ICES stock without requiring extensive stock-specific information. The catch advice might appear fairly low, but this is required to ensure management objectives are met in the long term. Additional more stock-specific data can be collected and used in case-specific analyses. However, this is a data and labour-intensive and expensive process but may lead to a higher catch advice.

*References*

-   Fischer, S. H., De Oliveira, J. A. A., & Kell, L. T. 2020. Linking the performance of a data-limited empirical catch rule to life-history traits. ICES Journal of Marine Science, 77: 1914-1926. (<https://doi.org/10.1093/icesjms/fsaa054>).

-   Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021a. Using a genetic algorithm to optimize a data-limited catch rule. ICES Journal of Marine Science, 78: 1311–1323. (<https://doi.org/10.1093/icesjms/fsab018>).

-   Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021b. Application of explicit precautionary principles in data-limited fisheries management. ICES Journal of Marine Science, 78: 2931–2942. (<https://doi.org/10.1093/icesjms/fsab169>).

-   Fischer, S. H., De Oliveira, J. A., Mumford, J. D., & Kell, L. T. 2022. Exploring a relative harvest rate strategy for moderately data-limited fisheries management. ICES Journal of Marine Science, 79: 1730-1741. (<https://doi.org/10.1093/icesjms/fsac103>).

-   Fischer, S. H., De Oliveira, J. A., Mumford, J. D., & Kell, L. T. 2023. Risk equivalence in data‐limited and data‐rich fisheries management: An example based on the ICES advice framework. Fish and Fisheries, 24: 231-247. (<https://doi.org/10.1111/faf.12722>).

-   ICES. 2017. Report of the ICES Workshop on the Development of Quantitative Assessment Methodologies based on Life-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks in categories 3-6 (WKLIFE VII). ICES CM 2017/ACOM:43.

-   ICES. 2018. Report of the Eighth Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE VIII). ICES CM 2018/ACOM:40.

-   ICES. 2019. Ninth Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE IX). ICES Scientific reports, 1:131. (<https://doi.org/10.17895/ices.pub.5550>)

-   ICES. 2020a. Tenth Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE X). ICES Scientific reports, 2:98, 72 pp. (<https://doi.org/10.17895/ices.pub.5985>).

-   ICES. 2022. ICES technical guidance for harvest control rules and stock assessments for stocks in categories 2 and 3. In Report of ICES advisory committee, 2022. ICES advice 2022, section 16.4.11. 20 pp. (<https://doi.org/10.17895/ices.advice.19801564>).

-   ICES. 2023a. Eleventh Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XI). ICES Scientific Reports. 5:21. 74 pp. (<https://doi.org/10.17895/ices.pub.22140260>).

-   ICES. 2023b. Workshop on the Development of Quantitative Assessment Methodologies based on Life-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XII). ICES Scientific Reports. 5:103. 111 pp. (<https://doi.org/10.17895/ices.pub.24581343>).

*Question source: Scottish Fishermen's Federation for WKLIFE XII 2023*

</details>
