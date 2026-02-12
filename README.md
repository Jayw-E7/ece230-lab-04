# Lab 04 - SOP/POS and KMaps

In this lab, you’ve learned how to apply KMaps, Sum Of Products and Products of
sums to simplify digital logic equations. Then, you’ve proven out that they work
using an implemented design on your Basys3 boards.

## Rubric

| Item | Description | Value |
| ---- | ----------- | ----- |
| Summary Answers | Your writings about what you learned in this lab. | 25% |
| Question 1 | Your answers to the question | 25% |
| Question 2 | Your answers to the question | 25% |
| Question 3 | Your answers to the question | 25% |

## Lab Summary

We wrote a naive equation directly from the truth table in order to test the derived SoP and PoS functions from the K-map. We then tested this naive equation against the derived functions through Vivado to test and make sure that the output is the same. By running these tests, we can see if our minimized K-map functions are still correct while also minimizing the cost of the function in case we wanted to build it into actual hardware.

## Lab Questions

### Why are the groups of 1’s (or 0’s) that we select in the KMap able to go across edges?
The KMap models each row / column as a “Cylinder”, where the layout allows the grouping of edges, since they will have common inputs that match even though they don’t appear adjacent on a 2D K-map.

### Why are the names Sum of Products and Products of Sums?
It is called Sum of Products because one function involves adding together groups of products via OR gates where the terms themselves are formed by AND. It is called Product of Sums for the same reason but this time we are connecting the groups together via AND and thus multiplying them, while the terms themselves are formed together by OR and added together.

### Open the test.v file – how are we able to check that the signals match using XOR?

We can check that the signals match with XOR because in the test.v file, the errors get reported whenever both led[0] and led[1] are not equal to 0 and thus 1 and therefore the same as each other, and this is also the case when comparing led[0] and led[2]. XOR is only true when the outputs are different, so these conditionals will not be reached if XOR is true. Thus, we can use it to test if the program works properly and the outputs match the expected results.

