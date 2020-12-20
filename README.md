# School District Analysis
This analysis reviews the differences and trends within schools, primarily looking how different grades, school sizes, and school types perform. The screenshot below shows a school level summary of most of the data of our concern. 

![school summary screenshot](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/school_summary_screenshot.png)

<br />

**What we want to know for our purposes is the following:**

* How does the school type affect outcome? (Charter vs District)
* How does school size affect outcome?
* How does funding per pupil affect outcome?
* How does each individual grade perform?

A secondary goal was to correct for tainted data, the reading & math scores for ninth graders in Thomas High School, which had to be corrected for. 

<br />
Code and analysis can be found [here](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/PyCitySchools_Challenge_testing.ipynb)

<br />

Source CSV file can be found [here](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/schools_complete.csv), 
and [here](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/students_complete.csv) 

---

## Results

Let's review the various summaries before and after they are corrected for the tainted group. It was discovered that the reading & math scores for ninth graders at Thomas High School had to be discounted. This resulted in 461 students/data points needing to be removed. 

### Results : District Summary
Those 461 students comprise 4.04% of the total ninth grade population and 1.17% of the overall student body. Consequently there isn't a drastic alteration in the performance outcomes. 

**Original District Summary**
![original district summary](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/district_summary_original.png)

<br />

**Corrected District Summary**
![corrected district summary](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/district_summary_corrected.png)

The change is not much more than a rounding error. A few key measures declined, indicating that the ninth grade cohort at Thomas High School was, in aggregate, marginally above average. 

* Avg Math : -0.1%
* % Passing Math : -0.2%
* % Passing Reading : -0.1%
* % Passing Overall : -0.3%

---
### Results : School Summary

Of course, a more immediate change was for Thomas High School itself. 

**Original School Summary**
![original school summary](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/thomas_HS_original.png)

**Corrected School Summary**
![corrected school summary](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/thomas_HS_corrected.png)

The above screenshots don't include labels, but the columns are "School Type", "Total Sudents", "Total School Budget", "Per Student Budget", "Average Math Score", "Average Reading Score", "% Passing Math", "% Passing Reading", and "% Overall Passing".

The differences are minute until the % passing columns. Unsurprisingly, they are all about a quarter lower. This is a bit of a statistical error, because those stats should refelct the percentage of tenth, eleventh and twelth graders passing. Instead, the numerator has been corrected, but the denominator hasn't.  

---

## Summary
