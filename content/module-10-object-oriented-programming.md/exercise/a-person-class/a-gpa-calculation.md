# Exercise 

Create a function that will determine the Grade Point Average (GPA) of a student. This function should receive a mark of a course and return the GPA value for the course.

**Step 1** - The table below consists of **grading scale**: 

| Percentage range | latter grade | grade point |
| ---------------- | ------------ | ----------- |
| 90-100           | A            | 4.0         |
| 85-89            | A-           | 3.7         |
| 80-84            | B+           | 3.3         |
| 75-79            | B            | 3.0         |
| 70-74            | B-           | 2.7         |
| 65-69            | C+           | 2.3         |
| 60-64            | C            | 2.0         |
| 55-59            | D+           | 1.3         |
| 50-54            | D            | 1.0         |
| Below 50         | F            | 0.0         |
|                  |              |             |

**Step 2** - Test your function with the value below. Given the student's marks

```java
90, 55, 89, 75, 85, 80
```

| Score | Grade | Grade Point |
| ----- | ----- | ----------- |
| 90    | A     | 4.0         |
| 55    | D+    | 1.3         |
| 89    | A-    | 3.7         |
| 75    | B     | 3.0         |
| 85    | A-    | 3.7         |
| 80    | B+    | 3.3         |

**Step 3:** Compute GPA

GPA = (Sum of Grade Points) ÷ (Number of Courses)

**Tips:** A Student is taking six courses, so therefore, the grade values should be six as seen in **step 2**.

**Rubrics:** 

* Your function should accept only positive integer values between the range: `100 - 0`. Add some validation to make sure only valid grades are passed to the function. 
* Print the result of the grade value is a well-formatted way. Use step 2 as a reference.
