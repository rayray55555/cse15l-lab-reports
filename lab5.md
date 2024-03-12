# Lab Report 5 - Putting it All Together (Week 9)
## Part 1 – Debugging Scenario
### Studentʼs post
Hi, I have a problem when I am working on the List-Examples-Grader, and I cannot find out how to
resolve the issue. I have a few guesses of what might cause the failure.
Here is the output of the error:  
![Image](.png)   
Here is the code for the grade.sh file:  
```java
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission
rm -rf grading-area

mkdir grading-area

git clone $1 student-submission
echo 'Finished cloning'


# Draw a picture/take notes on the directory structure that's set up after
# getting to this point

# Then, add here code to compile and run, and do any post-processing of the
# tests
files=`find student-submission/*.java`
for file in $files
do
    if [[ -f $file ]] && [[ $file == *ListExamples* ]]
    then echo 'Correct file is submitted.'
    else echo 'File NOT submitted correctly!!!'
    fi 
done

cp student-submission/ListExamples.java grading-area
cp TestListExamples.java grading-area
cp -r lib/ grading-area
cd grading-area
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java 2> feedback.txt
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples >output.txt
```
