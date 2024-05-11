**A high School has just finished a survery of it's students hoping to learn about what potential enviornemtnal factors could be contributing to the success or struggles of their students. The over all goal is to identify actionable items that increase the success of all students.**


#Import Data From Github orginally from Kaggle
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
Summary: The only significant correlation found this this data set comparing all availibly metric to grades was a negative correlation between 'class_failures' and grade_x's. There is also a small negative corecation between absences_y and grades_y The largest postive correlation was found bewtwen the intent to 'higher ed', however this is not significant. Most correlations are negligible.

The best course of action to improve math grades is to reduce 'class_failures'.



![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/e01ec1f4-5907-40b1-bb94-d81821086c72)


![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/b5ac42c4-4dd8-4d63-8799-a128c89a4aa1)
#The goal of the school is to increase the overall math and portugese grades across the schoolw
# My plan is to create a Df of the lowest 25% in math and a Df in the lowest score of portu. inspect both then merge the two and remove duplicates

![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/2158ac81-c7b3-4710-ab5e-a14fd746fd6e)


![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/5c94f3cc-98ca-4027-9602-0575f2218db1)
#there is extremely high correlation between one score to the next, with the second test having the most power
#next steps will be to re-examine the data again with the low hanging fruit data set with class_failures, absences, and school_support

![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/fe9e70a7-cd0c-409c-8164-0ff4af1bb85a)


![image](https://github.com/MEPritchard/EduPerformance/assets/128252526/e583b049-a2dd-4885-9efd-c4435a67e5f1)


Actionalbe Items Math: 
  Do:Extra paid classes (What extra classes are being taken by these student esecially around grade 2. extra classes did not have such a powerful effect on the overall population)
  Do Not: have class_failures (What can faculty and parents do to reduce class failures)
Actionalbe Items Portugese:
  Do: Well on the first test. (school support had roughly .2 correleation to grade_1 in both math and portu but almost no existant in this sample )
  Do Not: miss class. (can faculty and parents explore a way to mitigate the damage of missing a language class?)

Things to explore Math: school choice reason. This is a catagorical column to be further explored by data and by faculty.
Things to explore Portu: What effects sex (m/f) is having on students' acedemic success. Is there a bias?
Things to explore: It appears that 75 absences may be an outlier but several other students also increase the std deviation of this metric. Meet with team to understand what circumstances create this data.

#Small Expansion: What is going on with the top 25%. There is an inverse relationship between the created sample between math and portuguese grades which is contrary to the entire group.
#AI Expansion: what combination of parameters would be most likley to put some one in the bottom 25 of each grade.



