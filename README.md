# **Housing, Health and Happiness: a true causality ?**

## Abstract
In Housing, Health and Happiness, Cattaneao and team set out to determine the impact of replacing dirt floors with cement floors on child health and adult happiness. We have already established that some of their results are reproductible. In the next part of the project, we seek to answer an additional question regarding the impact of replacing dirt floor with cement. Namely, we will determine if the presence of cement flooring in the household, prior to the start of the study, mitigates the causality relationship previously established (cofounder).  

## Research Questions
> How does the share of cement flooring in the household, prior to the study, affect the causality relationship previously established between the replacement of dirt floor with cement and child health and maternal happiness ? How does the treament effect change based on the initial share of cement flooring in the household ? 

## Proposed dataset
[Both datasets](https://www.openicpsr.org/openicpsr/project/114542/version/V1/view;jsessionid=B4B1AAA8597E1F070A0C683C49E2A11C?path=/openicpsr/114542/fcr:versions/V1/PisoFirme_AEJPol-20070024_STATA-replication-code.do&type=file) used here were made available by the authors of the study. We previously mentioned that we will use analysis strategies different from the ones used by the authors. In line with that approach, we will process the data differently as well (handling of missing values, comparison of houselholds through different caliper matching strategies etc). 
- *PisoFirme_AEJPol-20070024_household.dta*: dataset with information at the household level. Includes data from both the 2000 Mexican Census and the 2005 Survey. 
- *PisoFirme_AEJPol-20070024_individual.dta*: dataset with information at the individual level. Includes data from the 2005 Survey.

## Proposed timeline
1. **By 05.12.20 :** Processing of data and caliper matching; matching of households based on cement share prior to study (and maybe additional features)
3. **By 15.12.20 :** Establishing the causality relationship between initial presence of cement floor, replacement of dirt floors and child health/maternal happiness. 
4. **By 18.12.20 :** Complete final report for P4 submission.

## Questions for TAs
> We want to match households which received the treatment (Piso Firme) to households that did not based on a "similarity score". The latter could be simply based on the share of cement present in the household prior to the project, or on more complexe features. However, we are not sure on how we should proceed to compute such a score. Do you have any suggestions ? 
