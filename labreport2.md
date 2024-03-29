# CSE 15L Lab Report 2 - Servers and Bugs (Week 3)
**Melanie Haro** <br />
**A17390371** <br />

## Part 1
This is how I wrote a web server called StringServer. <br />
I actually went ahead and drew inspiration from the wavelet file we used during Lab 2 to get a better understanding of how to structure my code.
![Image](2FD34FE2-5403-41F7-94C5-A256CAA47180.jpeg) \n
<br />
Here I wrote a Handler class that implements the **URLHandler** interface. I created a method called **handleRequest** that takes in a url. Within this method I included the code necessary to support the path and behavior described in the writeup. It basically says: if the path of the url says "/add-message", split the query (everything after the ? before the anchor) by its delimiter "=" and take those elements, put them into an array, and if the first element of the array is equal to s, then the second element of the array is equal to the message that will be displayed.
![Image](8396A585-A563-46C9-A221-49A259B1AA8A.jpeg) <br />
<br />
This is my code for the actual StringServer class which was actually the same exact thing as the NumberServer class from lab 2.
![Image](B066ECCD-013C-44D9-A494-87E97F0E6A06.jpeg) <br />
<br />
This is the result of compiling and running the code. <br />
I compiled it by using the following command: <br />
```
mharomendoza@Melanies-MacBook-Air-2 wavelet %  javac Server.java StringServer.java 
```
and then running:
```
mharomendoza@Melanies-MacBook-Air-2 wavelet % java StringServer 8080
```
**Which methods in your code are called? ->** handleRequest() is being called <br />
**What are the relevant arguments to those methods, and the values of any relevant fields of the class? ->** handleRequest takes in a url and if the path is "/add-message" then the query is separated into 2 different elements in an array where the first one should be "s", and if "s", then the message will be displayed. In this case: Hello <br />
**How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why. ->** the values of the relevant fields did not change, everything worked as it was supposed to: take in a url and if the url had the add message part, return a message. The message changed each time according to the message in the url. <br />

![Image](332A7966-FCA4-4CA6-9CBB-3DA8955B3E7D.jpeg) <br />
Here I did the same thing as above except with a different message. <br />
**Which methods in your code are called? ->** handleRequest() is being called <br />
**What are the relevant arguments to those methods, and the values of any relevant fields of the class? ->** handleRequest takes in a url and if the path is "/add-message" then the query is separated into 2 different elements in an array where the first one should be "s", and if "s", then the message will be displayed. In this case: Hello How are you <br />
**How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why. ->** the values of the relevant fields did not change, everything worked as it was supposed to: take in a url and if the url had the add message part, return a message. The message changed each time according to the message in the url. <br />

## Part 2
In lab this week, we created JUnit tests to identify bugs in the code provided. I tried to directly find out what was wrong with the methods but found that actually writing the tests in order to find out what was wrong with the program was more helpful. <br />
**Failure-inducing input for the buggy program (ReverseInPlace() method) proven by JUnit test**

```
@Test 
    public void testReversed2() {
    int[] arr = {1, 2, 3, 4, 5};
    int[] reversed = ArrayExamples.reversed(arr);
    assertArrayEquals(new int[] {5, 4, 3, 2, 1}, reversed);
    }
```
This test shows that there is an error in the program since it failed the test, meaning that we the actual value was not the same as the expect.
**Input that doesn’t induce a failure for the buggy program (also reverseInPlace() method) proven by JUnit test**
```
@Test 
    public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
    }
```

**Before the fix:**
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```
**After the fix:**
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
      int[] newArray = reversed(arr);
      for(int i = 0; i < arr.length; i += 1) {
          arr[i] = newArray[i];
      }
  }
```
The fixes address the issue since the original array is not being reversed in place correctly but after the fix, it reverse the way it is supposed to. Without changing the assignment of the array indices, the new array would not be filled with the reversed elements correctly.




**Symptoms** <br/>
*A symptom is a faulty program behavior you can see and in the image you can see that we can visibly see where our errors are occuring* <br />
![Image](0FFB09D9-4E80-4882-AEF5-E09AABEEA513.jpeg)
In this image, I compiled and ran a total of 3 tests but only 2 of them tested **reverseInPlace()** as you can see, there was 1 failure which was from the buggy program since it did not do what we wanted it to do (logical error). The other test that doesn't induce a failure for the program passed.
**Failure-inducing input for the buggy program (reverseInPlace() method) proven by JUnit test**


## Part 3
Before labs 2 and 3 I didn't know about URIs, I was unsure what the URI keyword was doing before url as a parameter
![Image](402A6F08-A160-4460-BFF5-45466796409A.jpeg) <br />
After lecture and reading the [documentation](https://docs.oracle.com/javase/8/docs/api/java/net/URI.html), I learned a few things:
- URI represents a Uniform Resource Identifier (URI) reference which is part of the Java libary 
- Is a character sequence that identifies a logical or physical resource connected to the internet
- A URI provides a simple, extensible way to identify internet resources
- URIs can identify different types of resources like webpages, images, electronic documents, etc.
