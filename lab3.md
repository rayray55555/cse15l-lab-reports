# Lab Report 3  
# Part 1 - Bugs  
Provide:  
- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)  
-An input that doesnʼt induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)  
-The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)  
-The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown) Briefly describe why the fix addresses the issue.  
1. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown).
 
JUnit Test:  
![Image](lab31.png)

Associated Code:  
![Image](lab32.png) 

2. An input that doesnʼt induce a failure, as a JUnit test and any associated code (write it as a
code block in Markdown)
  JUnit Test:
![Image](lab33.png)

Associated Code:  
![Image](lab32.png)   

3. -The symptom  
![Image](lab34.png)  

4. The Bug.  
Before Code:  
   ![Image](lab32.png)  
After Code:  
  ![Image](lab36.png)

Briefly describe why the fix addresses the issue.  
The problem with the code lies in its limitation to only modify the first half of the array. This occurs due to its reliance on the expression arr[arr.length - i - 1], which results in altering the array beginning from the last element towards the first, sequentially. Consequently, this approach leads to an issue where it inadvertently replaces values with those previously replaced. For instance, transforming an array like {1,2,3,4} initially to {4,2,3,4} and then to {4,3,3,4}, the final two elements remain unchanged because it substitutes the value at index 2 with that at index 1, and the value at index 3 with that at index 0, effectively leaving the array with 3 replacing 3 and 4 replacing 4, thus only the first half of the array appears to be reversed. To rectify this, a solution was implemented involving the creation of a temporary array to hold the original array's values. This allows for the reversal of each segment of the array from this temporary storage, ensuring the use of unmodified values for replacement in the actual array based on indices derived from the temporary array. This step is crucial for achieving the desired array reversal without the aforementioned issue.  
