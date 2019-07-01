# Overview

This repo includes code for a census tract level analysis of racial bias in uses of force by the Cincinnati police department. The analysis uses a multilevel model to allow for 'random effects' aka 'partial pooling' in the estimates for census tract level effects. The code includes data cleaning, modeling, and visualization.

This analysis takes inspiration from Prof. Andrew Gelman's paper ["An Analysis of the New York City Police Department’s “Stop-and-Frisk” Policy in the Context of Claims of Racial Bias"](http://www.stat.columbia.edu/~gelman/research/published/frisk9.pdf).

### Model Description

Our main variable of interest is the number of use-of-force incidents involving each racial group in each census tract.  I exclude racial groups that represent less than 5% of the total use-of-force incidents.  As control variables, I include measures of the percentage of the census tract (not race-specific) that lives below the federal poverty line, the percentage of the tract's population that is black, and the number of mandated for federal reporting "part-1" crimes (again, not race-specific). The list of part-1 crimes can be found [here](https://www.ucrdatatool.gov/offenses.cfm). Population of each racial group in each census track is used as an offset, e.g. the count of uses of force against white people is predicted with a offset provided by the total population of white people in the census tract.

I build a basic multi-level model measuring the relative rates of use-of-force for the racial groups included. The dependent variable should be the *count* of uses of force against each racial group in each census tract. I build several more complex models using the following control variables: poverty, percent black, and part 1 crimes. 

Note: Census tracts begin with the state and county fips code in the ACS dataset. The fips code for Ohio is 39, and the fips code for Hamilton county is 061.



Link to notebook of the code [here](./Noah_s_Final_Submission.pdf).