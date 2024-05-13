# A high School has just finished a survery of it's students hoping to learn about what potential enviornemtnal factors could be contributing to the success or struggles of their students. The over all goal is to identify actionable items that increase the success of all students.**


# Import Data From Github orginally from Kaggle
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



![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/6f66156b-291a-44cf-9d77-8b533532fdea)

![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/e01ec1f4-5907-40b1-bb94-d81821086c72)
# Initial Findings: The only significant correlation in this data set, when comparing all available metrics to grades, was a negative correlation between 'class_failures' and grade_math's. Meaningin a higher class_failure is likely to result in lower math 1, 2 and final scores. A small negative correlation exists between absences_portuguese and grades_portuguese. The largest positive correlation was found bewtwen 'school_support' and grade_1 of both math and Portuguese.

#  This data suggests reducing 'class_failures' will postively incrase math grades 1 2 and final.

![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/b5ac42c4-4dd8-4d63-8799-a128c89a4aa1)
# The goal of the school is to increase the overall math and Portugese grades across the school. Little was gained from the general analysis. 
# Trying to bring the bottom up is a quick way to timprove the statistical standing of a group.
# My plan is to create a sample DataFrame, grabbing the lowest 25% scored in grade_1_2_final_math and a DataFrame of the 25% lowest scores of grade_1_2_final_portuguese. 

![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/2158ac81-c7b3-4710-ab5e-a14fd746fd6e)


![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/5c94f3cc-98ca-4027-9602-0575f2218db1)
# There is extremely high correlation between one score to the next. We can say grades are consitent across the timeframe, with grade_2 being the best predicting factor of grade final.
# Next steps will be to re-examine the 'low hanging fruit' data set for trends in both math and Portuguese.

![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/fe9e70a7-cd0c-409c-8164-0ff4af1bb85a)


![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/e583b049-a2dd-4885-9efd-c4435a67e5f1)


# Actionable Items Math: 
  Do:Extra paid classes. Within this sample group, students in the extra_paid_classes catagory are statisticallt advantaged in math scores. 
  
  Do Not: Have class_failures
  
# Actionable Items Portuguese:
  Do: Score well on the first test. 
  
  Do Not: miss class. 

Things to explore Math: school choice reason. This is a categorical column to be further explored by data and by faculty.
Things to explore Portu: What effects sex (m/f) is having on students' academic success. Is there a bias?
Things to explore: It appears that 75 absences may be an outlier but several other students also increase the std deviation of this metric. Meet with the team to understand what circumstances create this data.
(What extra classes are being taken by these students. extra classes did not have such a powerful effect on the overall population)
(school support had roughly .2 correlation to grade_1 in both Math and Portuguese broadly but non existent in this sample)
 (What can faculty and parents do to reduce class failures)
 (can faculty and parents explore a way to mitigate the damage of missing a language class?)

#What is going on with the top 25%? Curiously there is an inverse relationship within the created sample between grade_1 .._2 .._final_math and grade_1 ..2.._final_protuguese which is contrary to the entire group.
# Is there a combination of parameters that would be most likely to put someone in the bottom 25 of each grade?




