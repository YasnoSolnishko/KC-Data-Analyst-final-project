# Karpov Courses final project
   
## Task 1. A/B Testing <a class="anchor" id="task"></a>

**1.1 Description**

During the testing of one hypothesis, a new payment mechanism for services on the website was proposed to the target group, while the control group retained the basic mechanism. As a task, you need to analyze the results of the experiment and make a conclusion whether to launch the new payment mechanism for all users.

**1.2 Input Data**

As input data, you have 4 csv-files:

-   [**groups.csv**](https://disk.yandex.ru/d/58Us0DWOzuWAjg) - a file with information about the user's belonging to the control or experimental group (A - control, B - target group) 
-   [**groups_add.csv**](https://disk.yandex.ru/d/3aARY-P9pfaksg) - an additional file with users that was sent to you 2 days after the data was provided
-   [**active_studs.csv**](https://disk.yandex.ru/d/prbgU-rZpiXVYg) - a file with information about the users who logged into the platform during the days of the experiment. 
-   [**checks.csv**](https://disk.yandex.ru/d/84hTmELphW2sqQ) - a file with information about user payments during the days of the experiment. 

**1.3 Questions**

We suggest that you answer the following questions:

-   What metrics do you look at during analysis and why?
-   Are there any differences in the indicators and what can they be related to?
-   Are these differences statistically significant?
-   Should the new mechanism be launched for all users?

This list of questions is not mandatory, and you can rely on your own plan in your answer.

**1.4 Requirements for the Answer**

-   When performing the test task, it is necessary to use the Python programming language. 
-   The file must have comments on the actions that you perform with the data. 
-   The file should be a complete report with conclusions made during the research.

## Task 2. SQL 

**2.1 Very diligent students.**

**2.1.1 Condition**

Educational courses consist of various lessons, each of which consists of several small tasks. Each such small task is called a "pea".

Let's call a very diligent student a user who has correctly solved 20 peas at least once this month.

**2.1.2 Task**

Given the default.peas table:

| Attribute name | Attribute type | Semantic value                           |
|----------------|----------------|------------------------------------------|
| st_id          | int            | Student ID                               |
| timest         | timestamp      | Time of solving the task                 |
| correct        | bool           | Whether the pea was solved correctly     |
| subject        | text           | Discipline in which the pea is located   |

You need to write an **optimal query** that will provide information about the number of very diligent students.
  
NB! By a diligent student we mean a student who has correctly solved 20 tasks this month.  

**2.2 Funnel optimization**

**2.2.1 Condition**

The educational platform offers students courses using the trial model: a student can solve only 30 peas for free per day. To get unlimited tasks in a particular discipline, a student must purchase full access. The team conducted an experiment where a new payment screen was tested.

**2.2.2 Task**

Given the default.peas and default.studs tables:

| Attribute name | Attribute type | Semantic value                          |
|----------------|----------------|-----------------------------------------|
| st_id          | int            | Student ID                               |
| test_grp       | text           | Label of the student in this experiment |

and default.final_project_check:

| Attribute name | Attribute type | Semantic value                                |
|----------------|----------------|-----------------------------------------------|
| st_id          | int            | Student ID                                    |
| sale_time      | timestamp      | Purchase time                                 |
| money          | int            | The price at which this course was purchased  |
| subject        | text           | Discipline for which full access was purchased|

You need to provide the following information about user groups in one query:

-   ARPU
-   ARPAU
-   Purchase conversion rate
-   Conversion rate of an active user to purchase
-   Conversion rate of a user who is active in mathematics (subject = 'math') to purchase a mathematics course

ARPU is calculated relative to all users who have been grouped.

A user is considered **active** if they have correctly solved **more than** 10 tasks in any discipline over their entire history.

A user is considered **active in mathematics** if they have correctly solved **2 or more** tasks in mathematics over their entire history.

**All data is in tabular form in Clickhouse**

## Task 3. Python

**3.1 Task**

1. Implement a function that will automatically load information from the additional file `groups_add.csv` (headers may differ) and recalculate metrics based on additional parameters.
2. Implement a function that will plot graphs based on the obtained metrics.
