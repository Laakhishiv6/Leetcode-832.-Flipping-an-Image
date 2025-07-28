# Leetcode-832.-Flipping-an-Image
# Description
Given an n x n binary matrix image, flip the image horizontally, then invert it, and return the resulting image.

To flip an image horizontally means that each row of the image is reversed.

For example, flipping [1,1,0] horizontally results in [0,1,1].
To invert an image means that each 0 is replaced by 1, and each 1 is replaced by 0.

For example, inverting [0,1,1] results in [1,0,0].
# Solution
In the given problem statement we have to flip the rows .

This can be done by converting 0 to 1 and 1 to 0 .

Example:

Input: image = [[1,1,0],[1,0,1],[0,0,0]]
Output: [[1,0,0],[0,1,0],[1,1,1]]

[[0,1,1],[1,0,1],[0,0,0]] reversible form is [[1,0,0],[0,1,0],[1,1,1]]

# Algorithm
1. Start from the first index of the array.
2. Assume the current index is the minimum.
3. Loop through the rest of the array to find the actual minimum element.
4. If a smaller element is found, update the minimum index.
5. After the inner loop ends, swap the current index element with the minimum element.
6. Repeat steps 2–5 for all indices except the last one.
7. After the loop ends, the array is sorted in ascending order.

# Code
Python

class Solution:

    def flipAndInvertImage(self, image: List[List[int]]) -> List[List[int]]:
        for row in image:
            row.reverse()
            for i in range(len(image)):
                row[i]^=1
        return image
