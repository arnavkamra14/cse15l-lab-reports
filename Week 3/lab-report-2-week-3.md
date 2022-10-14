# Week 3 Lab Report
## **Part 1: Simplest Search Engine**

**SearchEngine.java Code:**

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.lang.*;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> wordList = new ArrayList<String>();
    String matches = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format(
                    "Welcome to the Search Engine!\nUse the 'add' path to add an string to the list and 'search' to query the list of strings");
        } else {
            if (url.getPath().contains("/add")) {

                String[] parameters = url.getQuery().split("=");

                if (parameters[0].equals("s")) {
                    wordList.add(parameters[1]);
                    return String.format("%s has been added to the list!", parameters[1]);
                }
            }
            if (url.getPath().contains("/search")) {
                System.out.println(wordList);
                String[] parameters = url.getQuery().split("=");
                ArrayList<String> matchStor = new ArrayList<String>();

                if (parameters[0].equals("s")) {
                    for (int i = 0; i < wordList.size(); i++) {
                        if (wordList.get(i).contains(parameters[1])) {
                            matchStor.add(wordList.get(i));
                        }
                    }
                }

                if (matchStor.size() > 0) {
                    return String.format("The search term matches the following strings in the list: %s",
                            matchStor.toString());
                } else {
                    return String.format("No strings matched '%s'", parameters[1]);
                }

            } else {
                return "404 Not Found!";
            }
        }

    }
}

class SearchEngine {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
**Adding using SearchEngine.java (1):**
![Apply](AddApply.png)
**Adding using SearchEngine.java (2):**
![Reject](AddReject.png)
**Adding using SearchEngine.java (3):**
![Applications](AddApplications.png)
* Whenever values are added, the URL of the server is updated, and therefore the Handler class containing the handleRequest function is run
* Based on the URL path (which contains add in this case), the URL's contents are divided to isolate the word to be added
* The word is then added to an arraylist (to be stored for the query feature), and a success message is returned to the server
* This same process is repeated for each of the add URLs above, as shown by the message returned to the server

**Query using SearchEngine.java:**
![Search](SearchApp.png)
* The query feature relies on 'search' appearing in the server URL, similar to 'add' when adding.
* When a string is queried for, a for loop is run through the list of added words
* Any matches containing the requested string will be added to a new ArrayList
* If the size of the new List is greater than 0, the queried list is displayed. If not, a message indicating no matches found will be returned to the server

---

## **Part 2.1: Testing ArrayExamples.java**
**Failure-inducing Input 1:** 
```
@Test
public void testReverseInPlaceValues() {
    int[] input1 = { 1, 3, 5, 7 };
    ArrayExamples.reverseInPlace(input1);
    int[] expected = { 7, 5, 3, 1 };
    assertArrayEquals(expected, input1);
}
```
**Symptom 1:**
```
2) testReverseInPlaceValues(ArrayTests)
arrays first differed at element [2]; expected:<3> but was:<5>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReverseInPlaceValues(ArrayTests.java:23)
        ... 30 trimmed
Caused by: java.lang.AssertionError: expected:<3> but was:<5>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 36 more
```


**Bug 1 Fix:**
```
for(int i = 0; i < arr.length/2; i += 1) {
      arr[i] = arr[arr.length - i - 1];
}
```
* Change bounds of the for loop from arr.length to arr.length/2

**Connection between Symptom and Bug 1:**

* After reaching the halfway point of the for loop responsible for reversing the array, the logic of the loop is no longer applicable
* Therefore, only half of the values in the array get accurately switched

**Failure-inducing Input 2:**
```
@Test
  public void sameValueAverage() {
    double[] input1 = { 1, 1, 1, 2, 4 };
    double expected = 4;
    assertEquals(expected, ArrayExamples.averageWithoutLowest(input1), 0.0);
}
```

**Symptom 2:**
```
1) sameValueAverage(ArrayTests)
java.lang.AssertionError: expected:<4.0> but was:<1.5>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:555)
        at org.junit.Assert.assertEquals(Assert.java:685)
        at ArrayTests.sameValueAverage(ArrayTests.java:37)
```

**Bug 2 Fix:**
```
static double averageWithoutLowest(double[] arr) {
    doubl4 count = 0;
    if(arr.length < 2) { 
        return 0.0; 
    }
    double lowest = arr[0];
    for(double num: arr) {
        if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
        if(num != lowest) {
            count = count + 1; 
            sum += num; 
        }
    }
    return (sum / count);
}
```
* Add a count variable to accurately keep track of how many values are added to the sum (in case the value equals the lowest value)
* Divide the sum by that count variable to get the average

**Connection between Symptom and Bug 2:**
* The function is intended to take the average of the values in the array, excluding the lowest value in the array. However, the method does not take into account multiple of the lowest value (ie. multiple 1s shown in the test case)
* Creating a seperate count for the values added to the sum ensures that the lowest value is never added to the sum, and that the right value count is used

---

## **Part 2.2: Testing ListExamples.java**
**Failure-inducing Input:**
```
@Test
public void filterTest() {
    List<String> input1 = new ArrayList<>();
    input1.add("Hello");
    input1.add("My");
    input1.add("Name");
    List<String> expected = new ArrayList<>();
    expected.add("Hello");

    assertArrayEquals(expected.toArray(), ListExamples.filter(input1, new IsHello()).toArray());

}
```

**Symptom:**
* Before Interface Implementation:
    ```
    ListTests.java:16: error: StringChecker is abstract; cannot be instantiated
        assertArrayEquals(expected.toArray(), ListExamples.filter(input1, new StringChecker()).toArray());
    1 error
    ```

* After Interface Implementation:
    ```
    arnavkamra@Arnavs-MacBook-Pro lab3 % java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListTests
    JUnit version 4.13.2
    .
    Time: 0.004

    OK (1 test)
    ```
**Bug Fix:**
* In order for this test to pass, I had to implement the following class for the StringChecker interface:
    ```
    class IsHello implements StringChecker {
        public boolean checkString(String s) {
            return (s.contains("Hello"));
        }
    }
    ```

**Connection between Symptom and Bug:**
* The interface for StringChecker in ListExamples.java was not implemented. Therefore, it could not be instantiated and have objects of it created.
* In order for the filter function to work, it needs to be able to create an object for the StringChecker class (as it is a parameter of the method)
* Once implemented, the method works as expected, proving that this error was implementation based


