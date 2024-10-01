# Welcome Students of 4156

Please follow the assignment specifications on Courseworks when completing this project.

## I1: Setup, Testing and Bug Fixing

### 1. Code Clean up

`mvn checkstyle:check` yields no warnings or violations.

### 2. Test Suite Creation

78% branch coverage achieved.

### 3. Bug Fixing

13 bugs discovered. Static bug finder [PMD](https://pmd.github.io/) can be run with the following command.

```bash
alias pmd="./pmd-bin-7.6.0/bin/pmd"
$ pmd check -d /IndividualProject/src -R rulesets/java/quickstart.xml -f text
```

## I2: Feature Implementation and Maintenance

### 1. Feature A Implementation

`/retrieveCourses` endpoint realized with robustness guarantee. 

### 2. Feature B Implementation

`/enrollStudentInCourse` endpoint realized with robustness guarantee. 

### 3. Maintaining the Codebase

All new branches tested with a 78% total branch coverage rate. Checkstyle requirements satisfied. 

## I3: Continuous Integration and Cloud Deployment

### 1. Continuous Integration Loop

CI action set up on GitHub to run all tests and block the merge if tests fail.

### 2. Maintaining the Codebase

Codebase maintained.

### 3. Deployment to the Cloud

Deployed to Google Cloud server `https://my-miniproject-437318.ue.r.appspot.com`.

### 4. Write a README



# 4156-Miniproject

This is the GitHub repository for the Individual Project associated with COMS 4156 Advanced Software Engineering developed with Java and Maven. 

## Building and Running a Local Instance

The following packages and environments are required to be installed to deploy the service on your local machine.

+ Maven 3.9.9. Simply use `brew install maven ` to install on macOS or follow the [guidelines](https://maven.apache.org/download.cgi) if you are on Windows. 
+ JDK 21. The download link for different variants of JDK is [here](https://www.oracle.com/java/technologies/downloads/). 
+ Visual Studio Code. This project vscode for development but you are free to use any other IDE that you feel comfortable with. `Extension Pack for Java` extension is recommended to be installed if using vscode.

Below are several basic steps that you need to compile and run the service.

- Clone the repository to your own workspace.

+ Navigate to `IndividualProject` Directory and run the command `mvn package` to compile the project.
+ In order to run the Application, you can either run the generated JAR file after building the project through `java -jar target/individual-project-0.0.1-SNAPSHOT.jar`, or directly run the in main class IndividualProjectApplication.java from your IDE.
+ If you wish to run the code style checker or run the tests, you can with `mvn checkstyle:check` and `mvn test` respectively.
+ Once the application is running, you can access it via a web browser or API client through url `http://localhost:8080`. Check the application endpoints and functionalities in the "Endpoints" section below. You should be able to send requests and view query results directly.

## Running a Cloud based Instance

This service is also deployed to the cloud leveraging Google Cloud Platform. You can access the service conveniently without setting it up locally through `https://my-miniproject-437318.ue.r.appspot.com`. 

Welcome to test and try the functionalities!

## API Endpoints

Below is a list of available API endpoints that this service provides. You can use these endpoints to interact with the application via HTTP requests.

### Base URL

- Local: `http://localhost:8080`
- Cloud Instance: `https://my-miniproject-437318.ue.r.appspot.com`

### Endpoints

#### 1. Welcome Endpoint

- URL: `/`, `/index`, `/home`
- Method: `GET`
- Description: Returns a welcome message with instructions on how to make API calls.

#### 2. Retrieve Department Details

- URL: `/retrieveDept`
- Method: `GET`
- Parameters:
  - `deptCode` (String) - The department code.
- Description: Retrieves the details of the specified department.

#### 3. Retrieve Course Details

- URL: `/retrieveCourse`
- Method: `GET`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
- Description: Retrieves the details of the specified course within a department.

#### 4. Check if Course is Full

- URL: `/isCourseFull`
- Method: `GET`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
- Description: Checks whether the specified course has reached its enrollment capacity.

#### 5. Get Major Count from Department

- URL: `/getMajorCountFromDept`
- Method: `GET`
- Parameters:
  - `deptCode` (String) - The department code.
- Description: Retrieves the number of majors in the specified department.

#### 6. Identify Department Chair

- URL: `/idDeptChair`
- Method: `GET`
- Parameters:
  - `deptCode` (String) - The department code.
- Description: Retrieves the name of the department chair for the specified department.

#### 7. Find Course Location

- URL: `/findCourseLocation`
- Method: `GET`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
- Description: Retrieves the location where the specified course is held.

#### 8. Find Course Instructor

- URL: `/findCourseInstructor`
- Method: `GET`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
- Description: Retrieves the instructor of the specified course.

#### 9. Find Course Time

- URL: `/findCourseTime`
- Method: `GET`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
- Description: Retrieves the time slot when the specified course meets.

#### 10. Add Major to Department

- URL: `/addMajorToDept`
- Method: `PATCH`
- Parameters:
  - `deptCode` (String) - The department code.
- Description: Attempts to add a student to the specified department's majors.

#### 11. Remove Major from Department

- URL: `/removeMajorFromDept`
- Method: `PATCH`
- Parameters:
  - `deptCode` (String) - The department code.
- Description: Attempts to remove a student from the specified department's majors.

#### 12. Drop Student from Course

- URL: `/dropStudentFromCourse`
- Method: `PATCH`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
- Description: Attempts to drop a student from the specified course.

#### 13. Set Enrollment Count

- URL: `/setEnrollmentCount`
- Method: `PATCH`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
  - `count` (int) - The new enrollment count.
- Description: Sets the number of enrolled students in the specified course.

#### 14. Change Course Time

- URL: `/changeCourseTime`
- Method: `PATCH`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
  - `time` (String) - The new time slot for the course.
- Description: Changes the time when the specified course meets.

#### 15. Change Course Instructor

- URL: `/changeCourseTeacher`
- Method: `PATCH`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
  - `teacher` (String) - The new instructor's name.
- Description: Changes the instructor of the specified course.

#### 16. Change Course Location

- URL: `/changeCourseLocation`
- Method: `PATCH`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
  - `location` (String) - The new location for the course.
- Description: Changes the location where the specified course is held.

#### 17. Retrieve Courses by Course Code

- URL: `/retrieveCourses`
- Method: `GET`
- Parameters:
  - `courseCode` (int) - The course code.
- Description: Retrieves all courses with the specified course code across all departments.

#### 18. Enroll Student in Course

- URL: `/enrollStudentInCourse`
- Method: `PATCH`
- Parameters:
  - `deptCode` (String) - The department code.
  - `courseCode` (int) - The course code.
- Description: Attempts to enroll a student in the specified course.

### Usage Example

Retrieve details of course `4156` in department `COMS` using a GET request:

- Local URL:

  ```
  http://localhost:8080/retrieveCourse?deptCode=COMS&courseCode=4156
  ```

- Cloud Instance URL:

  ```
  https://my-miniproject-437318.ue.r.appspot.com/retrieveCourse?deptCode=COMS&courseCode=4156 
  ```
