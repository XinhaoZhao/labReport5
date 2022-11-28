```
# Create your grading script here
libPath=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar"
file="ListExamples.java"

rm -rf student-submission
git clone $1 student-submission

cp TestListExamples.java student-submission/
cd student-submission
echo 'Finished cloning'

if [[-e $file]] 
then
  echo "found the requested file"
else 
  echo "could not find the requested file"
  exit 1
fi

javac -cp $libPath*.java

if [[-f $file]]
then
  echo "the submittd file is a file"
else
  echo "the submitted file is not a file"
  exit 1
fi

java -cp $libPath  org.junit.runner.JUnitCore TestListExamples > errors.txt







```
