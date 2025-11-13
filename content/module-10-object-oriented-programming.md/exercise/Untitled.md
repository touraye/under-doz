Assign course to sister

```java
 // make sure the course name is not empty and the mark is not negative
        if (name.isEmpty() && mark < 0) return;

        // position cannot be negative or more than the size of course list
        if (position < 0 || position > courseList.length) return;

        // student cannot be assigned the same course twice
        boolean courseFound = false;
        for (int i = 0; i < courseList.length; i++) {
            if (name == courseList[i]) {
                courseFound = true;
                break;
            }
        }
        
        if (courseFound) return; // return the function call when a course is found

        // student course and mark cannot be overridden
        boolean hasCourse = courseList[position] != null; // position has course
        boolean hasMark = grades[position] != 0; // position has mark

        if (hasCourse | hasMark) return;

        // all checks alright:
        this.courseList[position] = name; // assign course
        this.grades[position] = mark; // assign mark
```

