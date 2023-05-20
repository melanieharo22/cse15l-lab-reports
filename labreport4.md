# CSE 15L Lab Report 4 - Doing it All From the Command Line (Week 7)
**Melanie Haro** <br />

The first step is to ssh into your ieng6 account. <br /> 
During lab, we had to create ssh keys which ends up saving you so much time because you don't have to type a password every single time you want to log into the remove ieng6 server. If you want to consider saving yourself some time, you will want to create an ssh key. <br />
![Image](step-4.jpg) <br />
The next step is to clone the fork of the repository by using the git clone command. <br />
```
git clone https://github.com/melanieharo22/lab7.git
```
![Image](step-5.jpg) <br />
Next to test the JUnit tests, you're going to want to **cd** into the lab7 directory and compile both ListExamples and ListExamplesTests. After that you are going to run ListExamplesTests to now run the JUnit tests. <br />
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamples.java
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamplesTests.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

```
![Image](junit-tests-failing.jpg) <br />
This is what the tests look like after compiling both files and running **ListExamplesTests**. We can see the tests failing. <br />
