# Lab Report 3  
# Part 1 - Bugs  
Provide:  
- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)  
-An input that doesnʼt induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)  
-The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)  
-The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown) Briefly describe why the fix addresses the issue.  
1. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown).
   @Test
    public void testReverseInPlace2() {
        int[] input1 = { 3, 2, 1, 0 };
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{ 0, 1, 2, 3 }, input1);
    }
}
