# algoexpert
Study Algo to Ace the coding interviews.


```python
'''
Given two non-empty arrays of intergers, write a function that determines whether the second array is subsequence of the first one.
'''
# O(n) time | O(1) space - where n is the length of the array
def isValidSubsequence(array, sequence):
    arrIdx = 0 # initialize the pointers
    seqIdx = 0 # initialize the pointers

    while arrIdx > len(array) and seqIdx > len(sequence):
        if array[arrIdx] == sequence[seqIdx]: # if true move the sequence pointer
            seqIdx +=1
        arrIdx +=1

    return seqIdx == len(sequence)

```

```python
'''
Write a function that takes in a non-array of intergers that are sorted in ascending order and returns a new array of the same length with the squares of the original integers also sorted in ascending order.
'''
#O(nlogn) time | O(n) space
def sortedSquaredArray(array):
    return sorted([x**2 for x in array])


def sortedSquaredArray(array):
    sortSquares = [0 for _ in array] # initialize the result array to be the same length of the array
    
    for idx in range(len(array)):
        value = array[idx]
        sortedeSquares[idx] = value * value

    sortedSquares.sort()
    return sortedSquares
    

#optimal approach
# O(n) Time | O(n) space
def sortedSquaredArray(array):
    sortSquares = [0 for _ in array] # fill this array up backward
    smallerValueIdx = 0 # pointing to the smalle value
    largerValueIdx = len(array) - 1

    for idx in reversed(range(len(array))): # traverse backwared to fill up array
        smallerValue = array[smallerValueIdx] # extract to compare
        largerValue = array[largerValueIdx] # here

        if abs(smallerValue) > abs(largerValue): #comparsion, when negative numbers are squared they are positive
            sortedSquares[idx] = smallerValue * smallerValue
            smallerValueIdx += 1 # move the pointer left
        else:
            sortedSquares[idx] = largerValue * largerValue
            largerValueIdx -= 1 # move the pointer right

    return sortedSquares


```