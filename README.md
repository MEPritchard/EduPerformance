# A high school has just finished a survey of its students.
# They are hoping to learn about what potential environmental factors could be contributing to the success or struggles of their students.
# The overall goal is to identify actionable items that increase the success of all students.


# Import Data From Github orginally from Kaggle.
https://www.kaggle.com/datasets/dillonmyrick/high-school-student-performance-and-demographics

school - student's school (binary: "GP" - Gabriel Pereira or "MS" - Mousinho da Silveira)

sex - student's sex (binary: "F" - female or "M" - male)

age - student's age (numeric: from 15 to 22)

address_type - student's home address type (binary: "Urban" or "Rural")

family_size - family size (binary: "Less or equal to 3" or "Greater than 3")

parent_status - parent's cohabitation status (binary: "Living together" or "Apart")

mother_education - mother's education (ordinal: "none", "primary education (4th grade)", "5th to 9th grade", "secondary education" or "higher education")

father_education - father's education (ordinal: "none", "primary education (4th grade)", "5th to 9th grade", "secondary education" or "higher education")

mother_job - mother's job (nominal: "teacher", "health" care related, civil "services" (e.g. administrative or police), "at_home" or "other")

father_job - father's job (nominal: "teacher", "health" care related, civil "services" (e.g. administrative or police), "at_home" or "other")

reason - reason to choose this school (nominal: close to "home", school "reputation", "course" preference or "other")

guardian - student's guardian (nominal: "mother", "father" or "other")

travel_time - home to school travel time (ordinal: "<15 min.", "15 to 30 min.", "30 min. to 1 hour", or 4 - ">1 hour")

study_time - weekly study time (ordinal: 1 - "<2 hours", "2 to 5 hours", "5 to 10 hours", or ">10 hours")

class_failures - number of past class failures (numeric: n if 1<=n<3, else 4)

school_support - extra educational support (binary: yes or no)

family_support - family educational support (binary: yes or no)

extra_paid_classes - extra paid classes within the course subject (Math or Portuguese) (binary: yes or no)

activities - extra-curricular activities (binary: yes or no)

nursery - attended nursery school (binary: yes or no)

higher_ed - wants to take higher education (binary: yes or no)

internet - Internet access at home (binary: yes or no)

romantic_relationship - with a romantic relationship (binary: yes or no)

family_relationship - quality of family relationships (numeric: from 1 - very bad to 5 - excellent)

free_time - free time after school (numeric: from 1 - very low to 5 - very high)

social - going out with friends (numeric: from 1 - very low to 5 - very high)

weekday_alcohol - workday alcohol consumption (numeric: from 1 - very low to 5 - very high)

weekend_alcohol - weekend alcohol consumption (numeric: from 1 - very low to 5 - very high)

health - current health status (numeric: from 1 - very bad to 5 - very good)

absences - number of school absences (numeric: from 0 to 93)

**These grades are related with the course subject, Math or Portuguese:**

grade_1 - first period grade (numeric: from 0 to 20)

grade_2 - second period grade (numeric: from 0 to 20)

final_grade - final grade (numeric: from 0 to 20, output target)


# Initial Findings: 
When comparing all available metrics to grades, there was a weak negative correlation (-.35 to -.36) between class_failures and grade_math(s) seen in dark blue on figure 2.
Meaning a higher class_failure is likely to result in lower math 1, 2 and final scores. 
A very weak negative correlation (-.2 to -.25) exists between absences_portuguese and grades_portuguese. 
There is a weak positive correlation (.21 and .19) seen in red in figure 2 was found between school_support and grade_1 of both math and Portuguese.
# Fig 1 General Correleation Heatmap
![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/6f66156b-291a-44cf-9d77-8b533532fdea)

# Fig 2 General Grade Specific Correlation Heatmap
![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/e01ec1f4-5907-40b1-bb94-d81821086c72)

# Fig 3 General Grade Specific Distribution Plot
![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/b5ac42c4-4dd8-4d63-8799-a128c89a4aa1)


# The goal is to increase the overall math and Portugese grades across the school.
Little was gleaned from the general analysis. Trying to bring the bottom up is a quick way to improve the statistical standing of a group. Figure 3 shows the disproprotioned lower tail. 
My plan is to create a sub-sample, grabbing the lowest 25% scored in grade 1 2 final math and the 25% lowest scores of grade 1 2 final Portuguese. With this sub-group identified specific actions can be taken to improve the distibution shape of the entire schools grades.
# Fig 4 Low Fruit Math Grade Heatmap
![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/5c94f3cc-98ca-4027-9602-0575f2218db1)

# Fig 5 Low Fruit Portuguese Grade Heatmap

![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/2158ac81-c7b3-4710-ab5e-a14fd746fd6e)
# There is extremely high correlation between one grade score to the next of the same type.
Grades score are stringly correlated (.6 to .81 and .69 to .84) across the timeframe, with grade_2 being the best predicting factor of grade final of both math and Portuguese seen in Figure 4 and Figure 5. This indicates the teachers and school provided a consitent learning environemnt accross the year.
Next steps will be to merge these datafames and re-examine the 'low hanging fruit' data set for trends in both math and Portuguese.
# Fig 6 Low Fruit Correleation Heatmap
![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/fe9e70a7-cd0c-409c-8164-0ff4af1bb85a)
There are some subtle differences between Fig 1 and Fig 6
# Fig 7 Low Fruit Grade Specific Correlation Heatmap
![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/e583b049-a2dd-4885-9efd-c4435a67e5f1)


# Actionable Items Math: 
  Do:Extra paid classes. Within the sub-group, students in the extra_paid_classes catagory have a small statistical advantaged in math scores. 
  
  Do Not: Have class_failures. What can faculty and parents do to reduce class failures?
  
# Actionable Items Portuguese:
  Do: Score well early. Scoring high on grade 1 has a high correlation to scoring similarly on grade final.
  
  Do Not: Miss class. Absences in a language class has small but significantly larger impact on grade scores when compared to math.

# Next meeting topics: 
What can parents, students and faculty do to reduce class failures?
What can parents, students and faculty do to mitigate lost learning from Portuguese absences?

# Potential issues:
A deeper dive should be conducted between sex and Portuguese grades. Sex has an equvilant negative correleation as absences to Portuguese grade scores. There could be a bias.
In an effort to improve math score school choice reason could be examined. This is a categorical column had a small emergence in the lowest scoring students. More environmental factors could be scrutinized.

# Comparative Study:
What is going on with the top 25%? Curiously there is an inverse relationship within the created sample between grade_1 .._2 .._final_math and grade_1 ..2.._final_protuguese which is contrary to the entire group.
Is there a combination of parameters that would be most likely to put someone in the bottom 25 of each grade?

# Things to explore: 
It appears that 75 absences may be an outlier but several other students also increase the std deviation of this metric. Meet with the team to understand what circumstances create this data.
What extra classes are being taken by the students in the low scoring catagory. Extra classes did not have such a powerful effect on the overall population.
School support had roughly .2 correlation to grade_1 in both Math and Portuguese broadly but non existent in this sub-sample.






