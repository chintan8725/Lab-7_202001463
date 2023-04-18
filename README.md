## Name: Kanpariya Chintan Manishbhai

## Student ID: 202001463

## Date : 18-04-2023

---

# Section A

Consider a program for determining the previous date. Its input is triple of day, month and year with the
following ranges 1 <= month <= 12, 1 <= day <= 31, 1900 <= year <= 2015.The possible output dates would be
previous date or invalid date.

--> Design the Equivalence class test cases:

For Day:
    
| Equivalence class | Range | Status
| ----------------- | ----- | ------
| E1 | Between 1 and 31 | Valid
| E2 | Less than 1 | Invalid
| E3 | Greater than 31 | Invalid

For Month:
    
| Equivalence class | Range | Status
| ----------------- | ----- | ------
| E4 | Between 1 and 12 | Valid
| E5 | Less than 1 | Invalid
| E6 | Greater than 12 | Invalid

For Year:
    
| Equivalence class | Range | Status
| ----------------- | ----- | ------
| E7 | Between 1900 and 2015 | Valid
| E8 | Less than 1900 | Invalid
| E9 | Greater than 2015 | Invalid

Equivalence Partitioning Test Cases:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid input: day=1, month=1, year=1900</td>
    <td>Invalid date</td>
  </tr>
  <tr>
    <td>Valid input: day=31, month=12, year=2015</td>
    <td>Previous date</td>
  </tr>
  <tr>
    <td>Invalid input: day=0, month=6, year=2000</td>
    <td>An error message</td>
  </tr>
  <tr>
    <td>Invalid input: day=32, month=6, year=2000</td>
    <td>An error message</td>
  </tr>
  <tr>
    <td>Invalid input: day=29, month=2, year=2001</td>
    <td>An error message</td>
  </tr>
</table>

Boundary Value Analysis Test Cases:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid input: day=1, month=1, year=1900</td>
    <td>Invalid date</td>
  </tr>
  <tr>
    <td>Valid input: day=31, month=12, year=2015</td>
    <td>Previous date</td>
  </tr>
  <tr>
    <td>Invalid input: day=0, month=6, year=2000</td>
    <td>An error message</td>
  </tr>
  <tr>
    <td>Invalid input: day=32, month=6, year=2000</td>
    <td>An error message</td>
  </tr>
  <tr>
    <td>Invalid input: day=29, month=2, year=2000</td>
    <td>An error message</td>
  </tr>
  <tr>
    <td>Valid input: day=1, month=6, year=2000</td>
    <td>Previous date</td>
  </tr>
  <tr>
    <td>Valid input: day=31, month=5, year=2000</td>
    <td>Previous date</td>
  </tr>
  <tr>
    <td>Valid input: day=15, month=6, year=2000</td>
    <td>Previous date</td>
  </tr>
  <tr>
    <td>Invalid input: day=31, month=4, year=2000</td>
    <td>An error message</td>
  </tr>
</table>
</br>

### P1. The function linearSearch searches for a value v in an array of integers a. If v appears in the array a, then the function returns the first index i, such that a[i] == v; otherwise, -1 is returned.

    int linearSearch(int v, int a[])
    {
        int i = 0;
        while (i < a.length)
        {
            if (a[i] == v)
            return(i);
            i++;
        }
        return (-1);    
    }
    
    @Test
    public void test() {
        unittesting obj = new unittesting();
        int[] arr1 = {2, 4, 6, 8, 10};
        int[] arr2 = {-3, 0, 3, 7, 11};
        int[] arr3 = {1, 3, 5, 7, 9};
        int[] arr4 = {};
        
        assertEquals(0, obj.linearSearch(2, arr1));
        assertEquals(4, obj.linearSearch(10, arr1));
        assertEquals(-1, obj.linearSearch(3, arr2));
        assertEquals(4, obj.linearSearch(9, arr3));
        assertEquals(-1, obj.linearSearch(2, arr4));
    }
        
 
**Equivalence Partitioning:**
 
| Tester Action and Input Data     | Expected Outcome      | 
| ------------- | :---: | 
| v is present in a        | Index of v         | 
| v is not present in a         | -1         | 

**Boundary Value Analysis:**

| Tester Action and Input Data     | Expected Outcome      | 
| ------------- | :---: | 
| Empty array a        | -1         | 
| v is present at the first index of a         | 0         | 
| v is present at the last index of a length of a        | a-1         | 
| v is not present in a         | -1         | 

**Test suites:**

| Tester Action and Input Data | Value to be found | Expected Outcome |
|------------------------------|-------------------|------------------|
| **Valid partition:**                                                |
| [1, 2, 3, 4, 5]              | 3                 | 2                |
| [5, 10, 15, 20, 25]          | 5                 | 0                |
| [2, 4, 6, 8]                 | 5                 | -1               |
| [1, 3, 5, 7]                 | 4                 | -1               |
| **Boundary Value Analysis:**        |                   |                  |
| []          | 5                 | -1               |
| [5]          |5                  | 0               |
| [15]          | 5                 | -1               |
| [5, 10, 15, 20, 25]          | 5                 | 0                |
| [5, 10, 15, 20, 25]          | 25                | 4                |
| [2, 4, 6, 8]                 | 2.2               | Invalid input    |
| [2, 4, 6, 8]                 | a                 | Invalid input    |
| [1.1, c, 5, 7]               | 2                 | Invalid input    |
 
 
 
 

### P2. The function countItem returns the number of times a value v appears in an array of integers a.
    int countItem(int v, int a[])
    {
        int count = 0;
        for (int i = 0; i < a.length; i++)
            {
                if (a[i] == v)
                count++;
            }
        return (count);
    }
    
    public void testCountItem() {
        CountItems counter = new CountItems();
        int[] arr1 = {1, 2, 3, 4, 5};
        int[] arr2 = {1, 2, 3, 4, 5, 6, 7, 8, 9};
        int[] arr3 = {1, 2, 3, 4, 4, 4, 5, 6, 7, 8, 9};
        int[] arr4 = {};
        int v1 = 3;
        int v2 = 10;
        assertEquals(1, counter.countItem(v1, arr1));
        assertEquals(0, counter.countItem(v2, arr1));
        assertEquals(9, counter.countItem(v1, arr2));
        assertEquals(0, counter.countItem(v2, arr2));
        assertEquals(1, counter.countItem(v1, arr3));
        assertEquals(0, counter.countItem(v2, arr3));
        assertEquals(0, counter.countItem(v2, arr4));
    }
<br>

**Equivalence Partitioning:**

| Tester Action and Input Data     | Expected Outcome      | 
| ------------- | :---: | 
| v is present in a        | Number of times v appears in a         | 
| v is not present in a         | 0         | 

**Boundary Value Analysis:**

| Tester Action and Input Data     | Expected Outcome      | 
| ------------- | :---: | 
| Empty array a        | 0         | 
| v is present once in a         | 1         | 
| v is present multiple times in a        | Number of times v appears in a         | 
| v is not present in a         | 0        | 


**Test suites:**

| Tester Action and Input Data | Value to be found | Expected Outcome |
|------------------------------|-------------------|------------------|
| **Equivalence partition:**                                                |
| [1, 2, 3, 4, 5]              | 3                 | 1                |
| [5, 10, 15, 20, 25]          | 11                 | 0                |
| **Boundary Value Analysis:**        |                   |                  |
| []          | 5                 | 0               |
| [5]          |5                  | 1               |
| [15]          | 5                 | 0               |
| [5, 10, 5, 20, 25]          | 5                 | 2                |
| [2, 4, 6, 8]                 | 2.2               | Invalid input    |
| [2, 4, 6, 8]                 | a                 | Invalid input    |
| [1.1, c, 5, 7]               | 2                 | Invalid input    |
 
 

### P3. The function binarySearch searches for a value v in an ordered array of integers a. If v appears in the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned.
Assumption: the elements in the array a are sorted in non-decreasing order.

    int binarySearch(int v, int a[])
    {
        int lo,mid,hi;
        lo = 0;
        hi = a.length-1;
        while (lo <= hi)
        {
            mid = (lo+hi)/2;
            if (v == a[mid])
            return (mid);
            else if (v < a[mid])
            hi = mid-1;
            else
            lo = mid+1;
        }
        return(-1);
    }
    
    import static org.junit.Assert.assertEquals;
    import org.junit.Test;
    
    public class BinarySearchTest {
        @Test
        public void testBinarySearch() {
            BinarySearch bs = new BinarySearch();

            int[] arr1 = {1, 3, 5, 7, 9};
            assertEquals(0, bs.binarySearch(1, arr1)); // search for 1 in {1, 3, 5, 7, 9}
            assertEquals(2, bs.binarySearch(5, arr1)); // search for 5 in {1, 3, 5, 7, 9}
            assertEquals(4, bs.binarySearch(9, arr1)); // search for 9 in {1, 3, 5, 7, 9}
            assertEquals(-1, bs.binarySearch(4, arr1)); // search for 4 in {1, 3, 5, 7, 9}

            int[] arr2 = {2, 4, 6, 8, 10, 12};
            assertEquals(-1, bs.binarySearch(1, arr2)); // search for 1 in {2, 4, 6, 8, 10, 12}
            assertEquals(2, bs.binarySearch(6, arr2)); // search for 6 in {2, 4, 6, 8, 10, 12}
            assertEquals(5, bs.binarySearch(12, arr2)); // search for 12 in {2, 4, 6, 8, 10, 12}
            assertEquals(-1, bs.binarySearch(7, arr2)); // search for 7 in {2, 4, 6, 8, 10, 12}
        }
    }

**Equivalence Partitioning:**

| Tester Action and Input Data     | Expected Outcome      | 
| ------------- | :---: | 
| v is present in a        | Index of v         | 
| v is not present in a         | -1         | 

**Boundary Value Analysis:**

| Tester Action and Input Data     | Expected Outcome      | 
| ------------- | :---: | 
| Empty array a        | -1         | 
| v is present at the first index of a         | 0         | 
| v is present at the last index of a length of a        | a-1         | 
| v is not present in a         | -1         | 

**Test suites:**

| Tester Action and Input Data | Value to be found | Expected Outcome |
|------------------------------|-------------------|------------------|
| **Valid partition:**                                                |
| [1, 2, 3, 4, 5]              | 3                 | 2                |
| [5, 10, 15, 20, 25]          | 5                 | 0                |
| [2, 4, 6, 8]                 | 5                 | -1               |
| [1, 3, 5, 7]                 | 4                 | -1               |
| **Boundary Value Analysis:**        |                   |                  |
| []          | 5                 | -1               |
| [5]          |5                  | 0               |
| [15]          | 5                 | -1               |
| [1, 1, 1, 1, 1]          | 1                 | 0/1/2/3/4                |
| [5, 10, 15, 20, 25]          | 5                 | 0                |
| [5, 10, 15, 20, 25]          | 25                | 4                |
| [2, 4, 6, 8]                 | 2.2               | Invalid input    |
| [2, 4, 6, 8]                 | a                 | Invalid input    |
| [1.1, c, 5, 7]               | 2                 | Invalid input    |


### P4. The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). The function triangle takes three integer parameters that are interpreted as the lengths of the sides of a triangle. It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal), scalene (no lengths equal), or invalid (impossible lengths).

    final int EQUILATERAL = 0;
    final int ISOSCELES = 1;
    final int SCALENE = 2;
    final int INVALID = 3;
    int triangle(int a, int b, int c)
    {
        if (a >= b+c || b >= a+c || c >= a+b)
        return(INVALID);
        if (a == b && b == c)
        return(EQUILATERAL);
        if (a == b || a == c || b == c)
        return(ISOSCELES);
        return(SCALENE);
    }
    
    @Test
    public void testEquilateral() {
      assertEquals("Equal", unittesting.triangle(3, 3, 3));
    }

    @Test
    public void testIsosceles() {
      assertEquals("Isosceles", unittesting.triangle(5, 5, 6));

    }

    @Test
    public void testScalene() {
      assertEquals("Scalene", unittesting.triangle(3, 4, 5));
    }

    @Test
    public void testIncorrectInput() {
      assertEquals("Incorrect input", unittesting.triangle(1, 2, 3));

    }
    
**Equivalence Partitioning:**

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid input: a=3, b=3, c=3</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Valid input: a=4, b=4, c=5</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Valid input: a=5, b=4, c=3</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Invalid input: a=0, b=0, c=0</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=-1, b=2, c=3</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Valid input: a=1, b=1, c=1</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Valid input: a=2, b=2, c=1</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Valid input: a=3, b=4, c=5</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Invalid input: a=0, b=1, c=1</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=1, b=0, c=1</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=1, b=1, c=0</td>
    <td>INVALID</td>
  </tr>
</table>

**Boundary Value Analysis:**

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Invalid inputs: a = 0, b = 0, c = 0</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid inputs: a + b = c or b + c = a or c + a = b (a=3, b=4, c=8)</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Equilateral triangles: a = b = c = 1</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Equilateral triangles: a = b = c = 100</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Isosceles triangles: a = b ≠ c = 10</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Isosceles triangles: a ≠ b = c = 10</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Isosceles triangles: a = c ≠ b = 10</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Scalene triangles: a = b + c - 1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Scalene triangles: b = a + c - 1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Scalene triangles: c = a + b - 1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Maximum values: a, b, c = Integer.MAX_VALUE</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Minimum values: a, b, c = Integer.MIN_VALUE</td>
    <td>INVALID</td>
  </tr>
</table>
</br>

### P5. The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix of string s2 (you may assume that neither s1 nor s2 is null).
    public static boolean prefix(String s1, String s2)
    {
        if (s1.length() > s2.length())
        {
            return false;
        }

        for (int i = 0; i < s1.length(); i++)
        {
            if (s1.charAt(i) != s2.charAt(i))
            {
                return false;
            }
        }
        return true;
    }
    
    public void testPrefix() {
        String s1 = "hello";
        String s2 = "hello world";
        assertTrue(unittesting.prefix(s1, s2));

        s1 = "abc";
        s2 = "abcd";
        assertTrue(unittesting.prefix(s1, s2));

        s1 = "";
        s2 = "hello";
        assertTrue(unittesting.prefix(s1, s2));

        s1 = "hello";
        s2 = "hi";
        assertFalse(unittesting.prefix(s1, s2));

        s1 = "abc";
        s2 = "def";
        assertFalse(unittesting.prefix(s1, s2));
    }

**Equivalence Partitioning:**

| Tester Action and Input Data     | Expected Outcome      | 
| ------------- | :---: | 
| Empty string s1 and s2        | True         | 
| Empty string s1 and non-empty s2         | True         | 
| Non-empty s1 is a prefix of non-empty s2        | True         | 
| Non-empty s1 is not a prefix of s2         | False         | 
| Non-empty s1 is longer than s2         | False         | 

**Boundary Value Analysis:**

| Tester Action and Input Data     | Expected Outcome      | 
| ------------- | :---: | 
| Empty string s1 and s2        | True         | 
| Empty string s1 and non-empty s2         | True         | 
| Non-empty s1 is not a prefix of s2         | False         | 
| Non-empty s1 is longer than s2         | False         | 

**Test Suites**

| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| **Equivalence Partitioning**|
| s1= "abcd",s2 = "abcd" | true |
| s1 = "",s2 = "" | true |
| s1 = "ha",s2 = "hasrh" | true |
| s1 = "hcp",s2 = "hc" | false |
| s1 = "abc",s2 = "" | false |
| s1 = "",s2 = "abc" | true |
| s1 = "o",s2 = "ott" | true |
| s1 = "abc",s2 = "def" | false |
| s1 = "deg",s2 = "def" | false |
| **Boundary value analysis**|
| s1= "abcd",s2 = "abcd" | true |
| s1= "",s2 = "" | true |
| s1= "abcd",s2 = "" | false |
| s1= "",s2 = "abcd" | true |
| s1 = "aef",s2 = "def" | false |
| s1 = "def",s2 = "deg" | false |
| s1 = "a",s2 = "att" | true |
| s1 = "harsh",s2 = "patel" | false |


### P6: Consider again the triangle classification program (P4) with a slightly different specification: The programreads floating values from the standard input. The three values A, B, and C are interpreted asrepresenting the lengths of the sides of a triangle. The program then prints a message to the standard output that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled. Determine the following for the above program:

#### a) Equivalence Classes for program:

| Equivalence Class | Condition
| ----------------- | ---------
| E1:Invalid Inputs | A<=0 or B<=0 or C<=0
| E2:Invalid Triangle | A+B<C or B+C<A or A+C<B
| E3:Scalene Triangle | A!=B and B!=C and A!=C
| E4:Equilateral Triangle | A==B and B==C
| E5:Isoscels Triangle | A==B or B==C or A==C
| E6:Right-Angel Triangle | A^2=B^2+C^2 or B^2=A^2+C^2 or C^2=A^2+B^2
                                                
#### b) Test-cases for Equivalence classes:
                                                
| Test Case | Input Data | Expected Output | Equivalence class covered
| --------- | ---------- | --------------- | ---------------------
| 1 | A=7,B=7,C=7 | Equilateral Triangle | E4
| 2 | A=5,B=12,C=13 | Right-Angle Triangle | E6
| 3 | A=5,B=5,C=4 | Isoscels Triangle | E5
| 4 | A=4,B=5,C=7 | Scalene Triangle | E3
| 5 | A=1,B=2,C=3 | Invalid Triangle | E2
| 6 | A=-1,B=-2,C=3 | Invalid Triangle | E1

#### c) Boundary condition A + B > C(Scalene Triangle):
    
--> We have to check for three boundary condition where A+B<C and A+B>C and A+B==C
     
| Test Case | Input Data | Expected Output
| --------- | ---------- | --------------
| 1 | A=2,B=3,C=5 | Invalid Triangle
| 2 | A=2,B=3,C=6 | Scalene Triangle
| 3 | A=1,B=2,C=3 | Invalid Triangle

--> Here In 1st and 3rd test case we would think that it is Scalene Triangle but it is Invalid Triangles.

#### d) Boundary condition A = C(Isoscels Triangle):

--> We have to check for two boundary condition A=C and A!=C
    
| Test Case | Input Data | Expected Output
| --------- | ---------- | ---------------
| 1 | A=-1,B=2,C=-1 | Invalid Triangle
| 2 | A=1,B=2,C=1 | Invalid Triangle
| 3 | A=1,B=3,C=1 | Isoscels Triangle
| 4 | A=0.2,B=0.5,C=0.2 | Isoscels Triangle
    
--> Here In 1st and 2nd test-case we think that it is Isoscels Triangle but it is not.
                                                
 #### e) Boundary condition A = B = C (Equilateral Traingle):
    
 | Test Case | Input Data | Expected Output
 | --------- | ---------- | ---------------
 | 1 | A=-1,B=-1,C=-1 | Invalid Traingle
 | 2 | A=0,B=0,C=0 | Invalid Triangle
 | 3 | A=3,B=3,C=3 | Equilateral Triangle
 | 4 | A=0.2,B=0.2,C=0.2 | Equilateral Triangle
 
 #### f) Boundary condition $ A^2 + B^2 = C^2 $(Right-Angeled Triangle):
 
 | Test Case | Input Data | Expected Output
 | --------- | ---------- | ---------------
 | 1 | A=-3,B=-4,C=5 | Invalid Traingle
 | 2 | A=3,B=4,C=5 | Invalid Traingle
 | 3 | A=1,B=1,C=2 | Invalid Traingle
 | 4 | A=5,B=12,C=13 | Right-Angeled Traingle
    
 #### g) Non-Traingle Case :
    
 | Test Case | Input Data | Expected Output
 | --------- | ---------- | --------------
 | 1 | A=0.1, B=0.2, C=0.3 | Invalid Triangle
 | 2 | A=1,B=1,C=2 | Invalid Triangle
 | 3 | A=1.2,B=1.2,C=2.4 | Invalid Traingle
 | 4 | A=0,B=0,C=0 | Invalid Traingle
 
 #### h) Non-positive Inputs: 
    
 | Test Case | Input Data | Expected Output
 | ---------- | --------- | ------------
 | 1 | A=-1,B=-2,C=-3 | Invalid Triangle
 | 2 | A=-0.2,B=-0.2,C=-3.6 | Invalid Triangle
 | 3 | A=-1,B=-1,C=-2 | Invalid Triangle
 | 4 | A=-2,B=-2,C=-2 | Invalid Triangle
 
 # Section B
 ### 1. Convert the Java code comprising the beginning of the doGraham method into a control flow graph (CFG).
 
 ![image](https://user-images.githubusercontent.com/75677485/232744642-17e64d38-b1eb-48e9-b828-832efd735999.png)

### 2. Construct test sets for your flow graph that are adequate for the following criteria:
a. Statement Coverage.
b. Branch Coverage.
c. Basic Condition Coverage.

--> The following are the test cases and their corresponding coverages of statements
Test cases:   

#### 1) p=[(x=2,y=2),(x=2,y=3),(x=1,y=3),(x=1,y=4)]  
Statements covered = { 1,2,3,4,5,7,8}  

Branches covered = {5,8}  

Basic conditions covered = {5-false, 8-false}    

#### 2) p=[(x=2,y=3),(x=3,y=4),(x=1,y=2),(x=5,y=6)]  
Statements covered = { 1,2,3,4,5,6,7}  

Branches covered = {5,8}  

Basic conditions covered = {5-false,true, 8-false}  

#### 3) p=[(x=1,y=5),(x=2,y=7),(x=3,y=5),(x=4,y=5),(x=5,y=6)]  
Statements covered = { 1,2,3,4,5,6,7,8,9}  

Branches covered = {5,8}   

Basic conditions covered = {5-false,true, 8-false,true}   

####4) p=[(x=1,y=2)]   
Statements covered = { 1,2,3,7,8}   

Branches covered = {8}  

Basic conditions covered = {}   

#### 5) p=[]  
Statements covered = { 1,2,3}  

Branches covered = {}  

Basic conditions covered = {}   

Thus, the above 5 test cases are covering all statements, branches and conditions.
These 5 test cases are adequate for statement coverage,branch coverage and basic
condition coverage.
