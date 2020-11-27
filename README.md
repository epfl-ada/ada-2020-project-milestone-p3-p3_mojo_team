# **Housing, Health and Happiness: a true causality ?**

## Abstract
In Housing, Health and Happiness, Cattaneao and team set out to determine the impact of replacing dirt floors with cement floors on child health and adult happiness. We have already established that some of their results are reproductible. In the next part of the project, we seek to answer an additional question regarding the impact of replacing dirt floor with cement. Namely, we will determine if the presence of cement flooring in the household, prior to the start of the study, mitigates the causality relationship previously established (cofounder).  

## Research Questions
> How does the share of cement flooring in the household, prior to the study, affect the causality relationship previously established between the replacement of dirt floor with cement and child health and maternal happiness ? How does the treament effect change based on the initial share of cement flooring in the household ? 

## Proposed dataset
[Both datasets](https://www.openicpsr.org/openicpsr/project/114542/version/V1/view;jsessionid=B4B1AAA8597E1F070A0C683C49E2A11C?path=/openicpsr/114542/fcr:versions/V1/PisoFirme_AEJPol-20070024_STATA-replication-code.do&type=file) used here were made available by the authors of the study. We previously mentioned that we will use analysis strategies different from the ones used by the authors. In line with that approach, we will process the data differently as well (handling of missing values, comparison of houselholds through different caliper matching strategies etc). 
- *PisoFirme_AEJPol-20070024_household.dta*: dataset with information at the household level. Includes data from both the 2000 Mexican Census and the 2005 Survey. 
- *PisoFirme_AEJPol-20070024_individual.dta*: dataset with information at the individual level. Includes data from the 2005 Survey.

## Methods
### Feature engineering
1. We create a dummy variable for the final outcome (called *HappyHealthy*): it will encompass both health and happiness features that are present in the data. To construct it, we will use a logistic regression that will give a probability of being "happy and health" with a threshold to be defined. 
2. We create a dummy variable (called *Cement*) identifying households with a certain share of cement floor prior to the study: if the household *Share of rooms with cement floors in 2000*  > median for the feature *Share of rooms with cement floors in 2000*, we consider it to be 1, otherwise 0. 

### Propensity scores calculation (2 different possibilities)
3. *2 possible solutions*
    a) We create a propensity score to have a share of rooms with cement floors above the median, based on household income, years of education etc. Match households with similar propensity scores to have more than the median share of rooms with cement, but who do not belong to the same group in terms of the *Cement* feature. The propensity score would be computed in a logistic regression fashion, using only the statistically significant features. 
    
    b) We create a similarity score that uses all other available features to determine how "alike" two households belonging to different *Cement* classes. To do so, we are considering using NN algorithm without replacement and while minimizing global balance over all matches. As the computational cost could be too high, we might first use a PCA and only the resulting features for the NN matching. 
 
### Treatment effect assessment
4. Assess the average treatment effect of having more than the median in terms of share of rooms with cement prior to the study on the final outcome *HappyHealthy*. 
5. Expected results would be that the Piso project is less impactful on happiness and health for households belonging to the *Cement* group. 

## Proposed timeline
1. **By 29.11.20 :** Decide how to feature enginneer the *HappyHealthy* variable (what already existing features do we use, how we encompass the effect on all of them at once...).
2. **By 05.12.20 :** Processing of data and caliper matching; matching of households based on cement share prior to study (and maybe additional features)
3. **By 15.12.20 :** Establishing the causality relationship between initial presence of cement floor, replacement of dirt floors and child health/maternal happiness. Based on obtained results, define which kind of report we set out to make (scientific report or datastory) and begin writing it. The workload for the report will be split equally between us.
4. **By 18.12.20 :** Complete final report/datastory for P4 submission.
5. **By 23.12.20 :** Video pitch recording. 

## Organization within the team
- Feature engineering will be done by the whole team together to ensure our dummy variables are defined correctly. 
- Propensity/similarity scores will be done by Dorian and Myriam individually as to compare the matching obtained by each. 
- Assessment of the results will be performed by David. 
- Datastory/report writing TBD. Will depend on how teammates' other projects are progressing. 
- Video recording by teammate with best english accent (TBD)... :-) 

## Questions for TAs
> Do you have any recommendations as to how to compute the propensity score ? 
> Do you recommend using the propensity score as explained in 3a) or the similarity score as explained in 3b) ? 
