# School District Analysis
The primary goal of this analysis was to analyze school data by type (charter vs district), size, spending per pupil, and grade level. Within this overall goal, there was a need to correct for some tainted data (Thomas High School's 9th grade data) and seeing how that affected the aforementioned analyses.  

![school summary screenshot](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/school_summary_screenshot.png)

<br />

**What we want to know for our purposes is the following:**

* How does the school type affect outcome? (Charter vs District)
* How does school size affect outcome?
* How does funding per pupil affect outcome?
* How does each individual grade perform?

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

The differences are minute until the % passing columns. Unsurprisingly, they are all about a quarter lower. This is a bit of a statistical error, because those stats should reflect the percentage of tenth, eleventh and twelth graders passing. Instead, the numerator has been corrected, but the denominator hasn't.  

Interestingly, this error doesn't show up in the math & reading averages. This is because when compromised values are corrected to be NaN (like we did in this study), calculations within the data series run perfectly fine, and we can see that the differences are quite minute between the two. The issue comes when you are using the data series with the NaN in more complex functions that incorporate other data series, which is the case when calculating % Passing Math, % Passing Reading and % Overall Passing. 

---
### Results : Grade Summary

The correcting Thomas High School's data did not affect the grade level averages, as they are all self-contained data series and were not subject to the error described earlier. As you can see from the image below, the only difference between the two (left : corrected, right : uncorrected) is the ninth grade column for Thomas High School

![thomas HS](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/grade_level_summary.png)

The above image displays the reading scores per grade per school, corrected and uncorrected versions. For the sake of saving space I only included one example, but the same is true for similar dataframes displaying the math and overall passing data - only Thomas High School's ninth grade data is affected. 

---
### Results : Spending Summary

The phenomenon repeats itself with the spending per pupil summary. In this analyses, all the schools were grouped into 4 tranches based on how much they spent per pupil. Our school in question, Thomas High School, fell into the $630 - $644 tranche (or bin in coding parlance). 

As you can see below, only the percentage passing math, reading and overall are affecting, all of which are a bit lower. Corrected version on the left, uncorrected on the right. 

![spending per pupil](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/funding_per_pupil.png)

---
### Results : Size Summary

Unsurprisingly, only the range in which Thomas High School belonged (medium sized school) was affected, and only the % Passing Math, Reading and Overall Columns. All of which were slightly lower. Corrected data on the left, uncorrected on the right.

![size summary](https://github.com/carlosjennings1991/School_District_Analysis/blob/main/Resources/size_analysis.png)

---

## Conclusion
