# Assignment 3

This function/method below should assign a course to a `studentCourseList` array. Before adding adding course make sure certain criteria are met. The function/method already have some checks, but you still need to add some additional checks.  

Check in the code "Your task begins here"



```java
// assign course to a student
    public void assignCourse(int position, String name, int mark) {
        // check for null - name
        if (name.length() <= 3) return;

        // check for student mark
        if (mark < 0 || mark > 100) return;

        // check position
        if (position < 0 || position > numberOfCourses - 1) return;
        
        // Your task begins here:

        /*
         * After passing all the checks, let's assign a course to a student.
         * A Student cannot be assigned the same course twice
         */

        boolean courseFound = false;
        // Iterate over courseList, check whether the input name is found
        // within the courseList array. If so, assign `courseFound` to true and
        // break the loop

        // check whether courseFound is true of false: if ture return

        // add course to input course name to courseList array using the position
        // add course to input course mark to grades array using the position
    }


//update your toString method with:
 public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age= '" + age + '\'' +
                ", department= '" + department + '\'' +
                ", courseList= " + Arrays.toString(courseList) +
                "grades= " + Arrays.toString(grades) + '\'' +
                '}';
    }
```

Test your application by creating a `Student` object and assigning grades:

* Create at least three students
* Use `toString()` to print their info

Happy coding!