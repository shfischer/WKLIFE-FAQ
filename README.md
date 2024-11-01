# WKLIFE Frequently Asked Questions (FAQ) on the ICES data-limited methods

This page contains Frequently Asked Questions (FAQ) on the ICES data-limited methods and the responses from WKLIFE.

Most questions and responses are copied from the ICES WKLIFE XII report (Annex 6):

> ICES. 2023. Workshop on the Development of Quantitative Assessment Methodologies based on Life-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XII). ICES Scientific Reports. 5:103. 111 pp. (<https://doi.org/10.17895/ices.pub.24581343>).

However, WKLIFE XIII in 2024 reviewed these questions, and added new questions and responses.

The ICES technical guidelines for data-limited methods are available from:

> ICES. 2024. ICES Guidelines - Advice rules for stocks in category 2 and 3. Version 2. ICES Guidelines and Policies - Advice Technical Guidelines. 30 pp. <https://doi.org/10.17895/ices.pub.26056306>

## Category 2

### SPiCT (Stochastic surplus Production models in Continuous-Time)

<details>

<summary>

#### Is the generic SPiCT harvest control rule appropriate for long-lived species such as porbeagle shark?

</summary>

TODO

*Question source: WGEF for WKLIFE XII 2023*

</details>

## Category 3

### General questions:

<details>

<summary>

#### Does the "precautionary multiplier" $m$ of the ICES Category 3 advice rule reduce the advice over time?

</summary>

-   ICES uses three methods to calculate the advice for Category 3 data-limited stocks (excluding short-lived species). These are the "rfb rule" for species with slower individual growth, the "chr rule" for stocks with medium individual growth, and the "rb rule" for stocks for which no reliable length data from the catch are available. These three methods include a multiplier ($m$) in the calculation of the catch advice, which ensures that the catch advice leads to long-term precautionary management advice. Precautionary in this context means that the risk of the stock being depleted is reduced to a low level.
-   For the rfb rule and the chr rule, this multiplier does not lead to a continuous reduction of the catch advice every time the rules are applied. Instead, the multiplier acts as a correction factor and adjusts the management targets of these advice rules (rfb rule: $L_{F=M}$ , chr rule: $F_{proxy, MSY}$). If a stock is estimated to be below the respective corrected management target, the catch advice value will be reduced. However, if a stock is estimated to be at or above this management target. The multiplier itself does not reduce the advice further when applied over multiple years.

    The multiplier $m$ of the empirical harvest control rules is a tuning parameter that ensures that the advice follows the ICES precautionary approach. The components of the harvest control rules are multiplicative, this means that the multiplier can be thought of as adjusting the target of the harvest control rules, i.e. the reference length in component f of the rfb rule and the target harvest rate of the chr rule. This principle is illustrated in the following equation for the rfb rule:

    $$A_{y+1} = A_y\ r\ f\ b\ m = A_y\ r\ \frac{L_{y-1}}{L_{F=M}}\ b\ m = A_y\ r\ \frac{L_{y-1}}{L_{F=M}/m}\ b = A_y\ r\ \frac{L_{y-1}}{L'_{F=M}}\ b$$

    where $A_{y+1}$ is the new catch advice, $A_y$ is the previous catch advice, $r$, $f$, $b$, and the multiplier $m$ are the components of the rfb rule.  The component $f$ is the ratio of $L_{y-1}$, the mean catch length, and $L_{F=M}$, the MSY proxy reference length.

    Response copied from WKLIFE XI report (ICES, 2023, Section 2.2.8, page 28):

    * ICES. 2023. Eleventh Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XI). ICES Scientific Reports. 5:21. 74 pp. <https://doi.org/10.17895/ices.pub.22140260>.


-   The third advice rule, the rb rule, was only proposed as a method of last resort and should be avoided if possible. 
   
    This rule is used when no reliable length data are available and thereby uncertainty of stock status is large. Contrary to the rfb and chr rules, the rb rule does not include a management target and simply adjusts the catch advice based on the stock trend, as observed with the stock index. The rb rule likely reduces the catch advice over time with the multiplier $m$:
    $$A_{y+1} = A_y\ r\ b\ m$$
    The biomass trend $r$ (2-over-3 trend) would need to be larger than 2 to increase the advice, even if the biomass index itself is above the biomass threshold (i.e. $b=1$). Simulations showed, that this is needed to ensure that (1) the management advice is precautionary in the long term, (2) the depletion risk is not greater than for the other methods, and (3) the depletion risk does not increase over time. This situation can be avoided when length data are available that are representative of the catch of the stock. These length data allow the application of the rfb or chr rules, which do not lead to a continuous reduction in the catch advice. A single year of length data can be enough to move away from the rb rule to either the rfb or chr rule.


*Question source*: WGDEEP for WKLIFE XII 2023; Scottish Fishermen's Federation for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>

<details>

<summary>

#### Should there be more tests of the multiplier $m$ for elasmobranch species?

</summary>

The Category 3 empirical harvest control rules (rfb/rb/chr) were tested for a wide range of scenarios and stocks, including slow-growing and long-lived species as well as elasmobranchs. These methods were tuned to be precautionary in the long term, so there is no immediate need for additional testing. Stock-specific simulations for specific stocks are encouraged, and the ICES technical guidelines encourage such work. The WKLIFE roadmap and proposed ToRs for the next WKLIFE meeting (WKLIFE XIII 2024) also include work on specific life histories, including considerations for elasmobranchs.

*Question source*: WGEF for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>


<details>
    
<summary>

#### What to do if the estimated reference values change over time?

</summary>

The rfb, rb, and chr rules include reference values such as a trigger value for the biomass index ($I_\text{trigger}$), the length at first capture ($L_c$), a length reference value ($L_{F=M}$), or the target harvest rate $F_\text{proxy, MSY}$. In general, these reference values should be set when the methods are applied for the first time and should not be updated for every application. The values could be periodically re-evaluated every few years, similar to benchmarks for data-rich stocks. However, if the entire biomass index series is updated for a new application, for example by using delta gam modelled index, the reference values should be updated accordingly (while using the same historical period for $F_\text{proxy, MSY}$ and $I_\text{trigger}$ ).

*Response from*: WKLIFE XIII 2024

</details>

<details>

<summary>

#### What to do if new life-history parameters such as $L_\infty$ become available; is there a need to recalculate derived values back in time?

</summary>

There is no need to annually update life-history parameters. If new growth parameters are available and these are substantially different and more reliable from previous estimates, these new ones should be used to update the advice rule. To ensure consistency in the calculation, derived values such as the reference length $L_{F=M}$ should also be updated and the respective mean catch length should be compared to this new reference length. In general, growth parameters and derived metrics, such as the reference length $L_{F=M}$ and $F_{proxy, MSY}$, should be periodically re-evaluated, e.g. every 3-5 years, following a similar schedule to benchmarks for Category 1 data-rich stocks, but kept constant in-between unless there is compelling new evidence for a change.

*Question source*: WGDEEP for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>

<details>

<summary>

#### Which life-history parameters (or strategies) matter when the von Bertalanffy growth model might not be appropriate?

</summary>

The individual growth rate (von Bertalanffy $k$) is only used to decide which method or multiplier is used and a rough estimate is enough, e.g. is $k$ below $0.2\ \text{year}^{-1}$ or not. The only other growth parameter used for the rfb rule is the asymptotic length $L_\infty$, which is used in the calculation of the reference length $L_{F=M}$ but the actual shape of the growth curve is less important.

*Question source*: WGDEEP for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>

<details>
<summary>

#### Can the assumption of $M/k=1.5$ for the length-based indicator be changed?

</summary>

The assumption of $M/k=1.5$ is solely used for a simple calculation of the reference length $L_{F=M}$. This simplification of reality was shown to be appropriate in simulation testing even if the reality (operating model) was different and the parameterisation of the rfb rule with its multipliers accounts for potential deviations. Deviations from $M/k=1.5$ are possible following Jardim et al. (2015; Appendix A):

$$L_{F=γM,k=θM} = \frac{\theta L_\infty + L_c (\gamma + 1)}{\theta + \gamma + 1}$$

where $\gamma$ links the natural mortality $M$ to fishing mortality $F$ as the proxy for MSY ($\gamma$=1 for $L_{F=M}$), $L_c$ is the length at first capture and $L_\infty$ is the asymptotic length. $\theta$ links the von Bertlanffy $k$ to $M$ and can be adjusted to a stock-specific value.

The function for the calculation of the reference length in the `cat3advice` R package (`Lref()`) includes an argument (`Mk`) to change the $M/k$ ratio to any user-defined value.

*References* 

* Jardim, E., Azevedo, M., and Brites, N. M. 2015. Harvest control rules for data-limited stocks using length-based reference points and survey biomass indices. Fisheries Research, 171: 12–19. <https://doi.org/10.1016/j.fishres.2014.11.013>

*Question source*: WGDEEP for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>


### Questions on biomass indices:
<details>
    
<summary>  
    
#### What to do if the biomass index trigger ($I_\text{trigger}$) value changes over time?

</summary>

See the response to [changes to the reference values over time](#changes-to-the-reference-values-over-time) for a general response.

_Specific considerations for the biomass index trigger:_

The biomass safeguard $b$ of the rfb, rb, and chr rules is defined as:

$$b = \text{min} \left( 1, \frac{I_{y-1}}{I_\text{trigger}} \right)$$

where the current biomass index value ($I_{y-1}$) is compared to a trigger value ($I_\text{trigger}$). If the most recent biomass index value falls below $I_\text{trigger}$, the biomass safeguard reduces the advised catch. In the absence of further information, $I_\text{trigger}$ is generically defined based on lowest observed biomass index value ($I_\text{trigger}= 1.4I_\text{loss}$).

During the first application of the rfb/rb/chr rules, $I_\text{loss}$ is typically defined as the biomass index value in a specific historical year. In subsequent applications of the rfb/rb/chr rule, $I_\text{loss}$ (or $F_{proxy, MSY}$) should *NOT* be re-defined with biomass index values from new data years. Therefore, the reference values will stay constant as long as the historical biomass index time series is unchanged. 
However, some biomass indices are derived by modelling or standardising survey data. This means that the historical biomass index time series may change with additional years of data. In this case, the calculation of $F_{proxy,MSY}$ should be updated from the same historical reference period and $I_\text{trigger}$ should be based on the new value for $I_\text{loss}$ from the same historical reference year (defined during the first application of the rfb/rb/chr rule). The R package `cat3advice` allows the definition of $I_\text{trigger}$ based on a reference year (see the [package vignette](https://github.com/shfischer/cat3advice/blob/main/vignettes/cat3advice.md#biomass-safeguard-b) for more details):

```
library(cat3advice)
data(ple7e_idx) # example data
# define Itrigger with a reference year for Iloss
b(ple7e_idx, yr_ref = 2007)
```

The reference year for $I_\text{loss}$ should generally not be changed. In a modelled biomass index, historical index values can change with inclusion of additional years of data, and thereby the year in which $I_\text{loss}$ is observed may change to a different (historical) year. In such a case, the appropriateness of the biomass index to provide catch advice should be carefully considered. Should the change be caused by a correction of errors in historical survey data, this may warrant a change of $I_\text{loss}$ but will need to be documented (and possibly reviewed).

*Response from* WKLIFE XIII 2024

</details>
<details>

<summary>

#### Some stocks have an $I_\text{loss}$ near zero, which is at the start or end of the time series, so using $I_\text{trigger} = 1.4 I_\text{loss}$ is not appropriate. In such cases, WGNSSK and WGEF used the 20th quantile of the time series. Is this approach appropriate?

</summary>

ICES technical guidelines specify that $I_\text{trigger}$ is a value below which a stock’s productivity is thought to be impaired and offer a calculation based on the lowest observed index value, $I_\text{loss}$, if no other information is available. If index values are very low or questionable at the beginning, these values could be removed. Using the 20th percentile of the index time seems appropriate and will lead to a larger $I_\text{trigger}$. This means the biomass safeguard will already be applied at higher index values and is more precautionary than the default approach.

*Question source*: WGEF for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>


<details>

<summary>

#### What to do when there are missing index values, can values be interpolated?

</summary>

In general, interpolating missing index values is not recommended because this would imply information is available when it does not exist. This is an area that needs further consideration.

*Question source*: WGDEEP for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>

### Questions on length data:
<details>

<summary>

#### Should we avoid to bin length data while calculating the mean catch length 'Lmean'?

</summary>

There is no need to bin data for calculating Lmean. It more important to consider bin width for calculating the length at first capture $L_c$ when length distributions are noisy (e.g. with multiple modes).

*Response from*: WKLIFE XIII 2024

</details>
<details>

<summary>

#### When calculating the mean catch length, should the length class correspond to the length of first capture ($L_c$) be included?

</summary>

The ICES technical guidelines specify that only length classes above $L_c$ should be considered. Whether $L_c$ is included or not does not really matter as long as it is done consistently between years. The `cat3advice` R package function for calculating mean catch length (`Lmean`) includes $L_c$ by default, but this can be turned off by setting the argument `include_Lc=FALSE`.

*Question source*: WGEF for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>

<details>

<summary>

####  What is the procedure if length-frequency distributions are not representative ?

</summary>

-   to do

*Response from*: WKLIFE XIII 2024

</details>



<details>

<summary>

#### Should discards be included in the length data when discard survival is high?

</summary>

The simulations for developing the category 3 empirical harvest control rules were based on the total catch (which affects the stock, i.e. the dead catch). Therefore, the length data used in the rfb and chr rules should ideally be representative of the dead catch. This means that surviving discards could be excluded from the catch length data if this is thought to make the length data more representative of the dead catch.

However, it should be ensured that there is consistency in the length data over time (use the same metric over time) and consistency between the mean catch length and reference lengths ($L_c$, $L_{F=M}$).


*Question source*: WGEF to WKLIFE XIII 2024

*Response from*: WKLIFE XIII 2024

</details>
<details>

<summary>

#### What to do if new length data become available (e.g. for a new gear or discards)?

</summary>

The length data used should be representative of the underlying stock and fishery and the gears should ideally cover the entire fishery. 

If data from a new gear become available, but the gear has only a small or negligible contribution to the total catch, there is likely no need to include it. If the contribution is a major part of the fishery, then the previous use of the length data may be questioned.

For the use of discard data, see question XYZ.

When considering including new data into the length distribution, it is important to consider whether data are only available occasionally, for all historical years, and whether it will also be available in the future. This is because the use of length data should be consistent over time. If the new data make the length distribution more representative of the stock and fishery, they should be included. Such substantial changes to the length data will require updating references values ($L_c$, $L_{F=M}$) to ensure the mean catch length and reference values are consistent. Such changes may require a review.

For the rfb rule, including new length data is likely more straightforward because the rfb uses the most recent length data. On the other hand, the generic application of the chr rule uses historical length data to define the target harvest rate $F_\text{MSY proxy}$. Therefore, changes to the historical length data may cause changes to this target harvest rate.

*Question source*: WGEF to WKLIFE XIII 2024

*Response from*: WKLIFE XIII 2024

</details>




<details>

<summary>
    
#### Can survey length data be used instead of catch length data for stocks with sparse catch length data (e.g. only landings or no landing nor discard length data). 

</summary>

Some work on this issue was presented at WKLIFE XII (ICES, 2023). The conclusion was that it might be possible to use survey length data as a proxy if no or insufficient (commercial) length data are available. The survey length distributions should be representative of fisheries catch length distribution. Therefore, the length at first capture $L_c$ should still be estimated from catch data, because the $L_c$ from survey data might be too low and bias the reference length $L_{F=M}$. Furthermore, survey length distributions should also cover large individual lengths. It should be noted that the reference point $L_{F=M}$ is based on the assumption of knife-edged, asymptotic fisheries selectivity. 

*References* 

* ICES. 2023. Workshop on the Development of Quantitative Assessment Methodologies based on Life-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XII). ICES Scientific Reports. 5:103. 111 pp. <https://doi.org/10.17895/ices.pub.24581343>

*Question source*: WGEF for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343), clarification from WKLIFE XIII 2024

</details>

<details>

<summary>

#### In the absence of discard length data, is it better to use landings or survey length data?

</summary>

The length data used in the rfb rule should be representative of the underlying stock and fishery and the gears should ideally cover the entire fishery. In the absence of reliable catch length data, data from surveys can be used (see question ["Can survey length data be used instead of catch length data for stocks with sparse catch length data (e.g. only landings or no landing nor discard length data)."](#can-survey-length-data-be-used-instead-of-catch-length-data-for-stocks-with-sparse-catch-length-data-eg-only-landings-or-no-landing-nor-discard-length-data) for details). If there are neither reliable and representative length data from the catch nor from surveys, the rfb rule should not be used.

If discard survival is assumed to be high or discards are small or negligible compared to the landings, excluding discards is unlikely to have a big impact and length data from the landings could be used instead of length data from the total catch. If some discards occur at small lengths, which are likely below the length of first capture ($L_c$), removing these from length distributions is not an issue, because they will be removed anyway for the calculation of the mean catch length. If discards are substantial, excluding discards invalidates the data, as the reference points and mean length cannot be calculated correctly.

Importantly, the same data source should be used in consecutive applications of the rfb rule to ensure consistency in the length indicator over time. Should there be changes in the data source for the length data, length reference values may have to be re-evaluated.

The ICES technical guidelines set out the general principles for the application of the rfb rule and what data to use. WKLIFE is not in a position to comment on very specific examples. Questions such as whether data is representative should be addressed by the relevant experts in the assessment working groups with more knowledge about the stock and fishery.

*Question source*: WGEF to WKLIFE XIII 2024

*Response from*: WKLIFE XIII 2024

</details>

<details>

<summary>

#### When only landings length data are used: can $L_c$ be approximated to the smallest size in the data set?

</summary>

For considerations on using length data from landings instead of from the total catch, see question XYZ.

The length of first capture $L_c$ of the total catch cannot easily be estimated from landings data if discards are substantial. Whether the smaller lengths from landings are representative for total catches depends on the discard rate at length. In some specific cases, the lowest lengths in the landings may coincide with $L_c$ but this cannot be generalised.


*Question source*: WGEF to WKLIFE XIII 2024

*Response from*: WKLIFE XIII 2024

</details>




<details>

<summary>

#### Can length data be pooled from several years?

</summary>

The ICES technical guidelines ([ICES, 2024](https://doi.org/10.17895/ices.pub.26056306)) recommend pooling of length data over several years for the estimation of length reference points, such as $L_c$ (which in turn is used in the calculation of the reference length $L_{F=M}$). This can reduce the impact of noise in the data and give more reliable estimates.

However, component $f$ of the rfb rule based on the mean catch length, should generally be estimated with annual data so that changes in the fishing pressure can be observed. This also makes sure that the latest signal from the length data is used.

For some species (e.g. very slow-growing species), changes in the length may occur slowly after changes in the stock status. Pooling of data in the length indicator may be possible in such cases. However, drastic changes to the stock, e.g. removal of large individuals by the fishery can still cause fast changes in the length indicator. If length data are very noise, their appropriateness for use in the rfb rule might be questioned.

*References*

* ICES. 2024. ICES Guidelines - Advice rules for stocks in category 2 and 3. Version 2. ICES Guidelines and Policies - Advice Technical Guidelines. 30 pp. <https://doi.org/10.17895/ices.pub.26056306>

*Question source*: WGEF to WKLIFE XIII 2024

*Response from*: WKLIFE XIII 2024

</details>

<details>

#### How to plot the length indicator when length data are pooled or years are missing?

</summary>

Exactly what and how data are presented in an advice sheet is outside the scope of WKLIFE.

For considerations on pooling length data, see question "[Can length data be pooled from several years?](#can-length-data-be-pooled-from-several-years)". If length data are pooled, WKLIFE suggests that the points in the length indicator plot are not linked because they do not represent a continuous time series. The same applies if there are gaps in the time series. Different metrics (e.g. annual values and pooled data) should ideally not be shown in the same figure. 


*Question source*: WGEF to WKLIFE XIII 2024

*Response from*: WKLIFE XIII 2024

</details>





### Questions on the rfb rule:

<details>

<summary>

#### Why does the new rule (rfb) lead to even lower advice than the 2 over 3 rule?

</summary>

The 2 over 3 rule was implemented in 2012 as an interim measure based on the best available science at that time. Re-evaluation of this method through simulation has shown that the 2 over 3 rule does not sufficiently decrease the risk of stock depletion over time and does not follow the ICES precautionary approach. This means that the catch advice from the 2 over 3 rule in many cases was higher than it should have been. The new rfb rule was implemented after extensive simulation testing and review and was designed to explicitly follow the ICES precautionary approach and the MSY approach. The rule includes additional components (multipliers) and this means that the catch advice from the rfb rule may be lower than from the 2 over 3 rule, but this is required to follow ICES management objectives.

For details, see [Fischer et al. (2020)](https://academic.oup.com/icesjms/article/77/5/1914/5856265)

*Question source*: WGDEEP for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>

<details>

<summary>

#### Why does the catch advice go down even if the biomass index is going up?

</summary>

The previous 2 over 3 rule calculated catch advice based on the trend from a biomass index. In addition to this, the rfb rule also considers (1) the exploitation of the stock based on catch-length data and (2) includes a biomass safeguard that reduces the catch advice if the biomass index falls below a trigger value. The catch advice calculated with the rfb rule is a result of all these considerations combined. Furthermore, the trend in the biomass index is calculated by using data from the most recent five years, i.e. an increase in the index in a single year does not necessarily result in a positive biomass trend.

*Question source*: WGDEEP for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>

<details>

<summary>

#### Can the advice interval for the rfb rule (default: biennial) be changed?

</summary>

The ICES technical guidelines recommend the implementation of the rfb rule with a biennial advice interval ([ICES, 2022](https://doi.org/10.17895/ices.advice.19801564)). WKLIFE XI ([ICES, 2023](https://doi.org/10.17895/ices.pub.22140260)) was asked if the rfb rule could be applied on an annual basis and concluded that this is unlikely to increase the risk of stock depletion but has the undesirable feature of reducing the long-term catch and should only be used in exceptional cases when asked for by ICES advice requesters ([ICES, 2023](https://doi.org/10.17895/ices.pub.22140260), Section 2.2.4.1, page 21). Other advice intervals (from one to five years) were included in the generic testing of the rfb rule (Fischer et al., [2021a](https://doi.org/10.1093/icesjms/fsab018),[b](https://doi.org/10.1093/icesjms/fsab169)) but the biennial advice interval appeared to work best. Longer advice intervals can reduce the reactivity of the rfb rule and may increase the risk of stock depletion because the catch cannot be reduced fast enough.

*References* 

* Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021a. Using a genetic algorithm to optimize a data-limited catch rule. ICES Journal of Marine Science, 78: 1311–1323. <https://doi.org/10.1093/icesjms/fsab018> 

* Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021b. Application of explicit precautionary principles in data-limited fisheries management. ICES Journal of Marine Science, 78: 2931–2942. <https://doi.org/10.1093/icesjms/fsab169>

* ICES. 2022. ICES technical guidance for harvest control rules and stock assessments for stocks in categories 2 and 3. In Report of ICES advisory committee, 2022. ICES advice 2022, section 16.4.11. 20 pp. International Council for the Exploration of the Sea. <https://doi.org/10.17895/ices.advice.19801564>

* ICES. 2023. Eleventh Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XI). ICES Scientific Reports. 5:21. 74 pp. <https://doi.org/10.17895/ices.pub.22140260>

*Question source*: WGDEEP for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>

<details>

<summary>

#### If we are using discards and landings length data in the rfb calculation are we producing catch advice?

</summary>

The simulations for developing the category 3 empirical harvest control rules were based on the total catch (which affects the stock, i.e. the dead catch).

The component f of the rfb rule gives an indication about the fishing pressure on the stock and does not make any decision on whether to give landings or catch advice. Usually, the total catch (landings and discards) are used in the rfb rule and catch advice is given. The corresponding landings and discards can then be calculated with the (assumed) discard rate.

WKLIFE is not in the position to decide whether catch or landings advice is produced. Such a decision will depend on the level of discards compared to the total stock and discard survival.


*Question source*: WGEF to WKLIFE XIII 2024

*Response from*: WKLIFE XIII 2024

</details>


<details>

<summary>

#### Is the new rfb rule appropriate given the sensitivity of simulation outputs and estimated risk to a number of starting specification? Are the simulations wide enough? 

</summary>

The implementation of the new WKLIFE X methods for Category 3 stocks (rfb/rb/chr rules) is the culmination of more than five years of scientific work. The work has been developed and reviewed under the supervision of the WKLIFE workshops. Furthermore, the scientific work has been published in five scientific articles in internationally renowned peer-reviewed scientific journals (see reference list below). The simulations accounted for many scenarios, including different life histories, depletion scenarios, and sensitivity analyses. The methods were developed generically, so that they are applicable to any ICES stock without requiring extensive stock-specific information. In some cases, the catch advice might appear fairly low, but this was shown to be required to ensure management objectives are met in the long term. Additional more stock-specific data can be collected and used in case-specific analyses. However, this is a data and labour-intensive and expensive process but may lead to an advice rule better tuned to the specific stock.

*References*

-   Fischer, S. H., De Oliveira, J. A. A., & Kell, L. T. 2020. Linking the performance of a data-limited empirical catch rule to life-history traits. ICES Journal of Marine Science, 77: 1914-1926. <https://doi.org/10.1093/icesjms/fsaa054>

-   Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021a. Using a genetic algorithm to optimize a data-limited catch rule. ICES Journal of Marine Science, 78: 1311–1323. <https://doi.org/10.1093/icesjms/fsab018>

-   Fischer, S. H., De Oliveira, J. A. A., Mumford, J. D., & Kell, L. T. 2021b. Application of explicit precautionary principles in data-limited fisheries management. ICES Journal of Marine Science, 78: 2931–2942. <https://doi.org/10.1093/icesjms/fsab169>

-   Fischer, S. H., De Oliveira, J. A., Mumford, J. D., & Kell, L. T. 2022. Exploring a relative harvest rate strategy for moderately data-limited fisheries management. ICES Journal of Marine Science, 79: 1730-1741. <https://doi.org/10.1093/icesjms/fsac103>

-   Fischer, S. H., De Oliveira, J. A., Mumford, J. D., & Kell, L. T. 2023. Risk equivalence in data‐limited and data‐rich fisheries management: An example based on the ICES advice framework. Fish and Fisheries, 24: 231-247. <https://doi.org/10.1111/faf.12722>

-   ICES. 2017. Report of the ICES Workshop on the Development of Quantitative Assessment Methodologies based on Life-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks in categories 3-6 (WKLIFE VII). ICES CM 2017/ACOM:43.

-   ICES. 2018. Report of the Eighth Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE VIII). ICES CM 2018/ACOM:40.

-   ICES. 2019. Ninth Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE IX). ICES Scientific reports, 1:131. <https://doi.org/10.17895/ices.pub.5550>

-   ICES. 2020a. Tenth Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE X). ICES Scientific reports, 2:98, 72 pp. <https://doi.org/10.17895/ices.pub.5985>

-   ICES. 2022. ICES technical guidance for harvest control rules and stock assessments for stocks in categories 2 and 3. In Report of ICES advisory committee, 2022. ICES advice 2022, section 16.4.11. 20 pp. <https://doi.org/10.17895/ices.advice.19801564>

-   ICES. 2023a. Eleventh Workshop on the Development of Quantitative Assessment Methodologies based on LIFE-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XI). ICES Scientific Reports. 5:21. 74 pp. <https://doi.org/10.17895/ices.pub.22140260>

-   ICES. 2023b. Workshop on the Development of Quantitative Assessment Methodologies based on Life-history traits, exploitation characteristics, and other relevant parameters for data-limited stocks (WKLIFE XII). ICES Scientific Reports. 5:103. 111 pp. <https://doi.org/10.17895/ices.pub.24581343>

*Question source*: Scottish Fishermen's Federation for WKLIFE XII 2023

*Response from*: [WKLIFE XII 2023](https://doi.org/10.17895/ices.pub.24581343)

</details>

### Questions on the R package cat3advice:

<details>
<summary>

#### In the cat3advice package, option “excluding_Lc = TRUE” from  Lmean function  doesn’t work on bins value (e.g : rjn.27.8c)?
</summary>

*Response from*: WKLIFE XIII 2024
</details>

<details>
<summary>

#### Is there any reason to use the function : “floor” when bins are used? Would it be possible to add an option to let us choose the bins value?

</summary>
*Response from*: WKLIFE XIII 2024
</details>
