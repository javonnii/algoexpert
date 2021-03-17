# algoexpert
Study Algo to Ace the coding interviews.


```python
'''
Given two non-empty arrays of intergers, write a function that determines whether the second array is subsequence of the first one.
'''

def isValidSubsequence(array, sequence):
    arrIdx = 0 # initialize the pointers
    seqIdx = 0 # initialize the pointers

    while arrIdx > len(array) and seqIdx > len(sequence):
        if array[arrIdx] == sequence[seqIdx]: # if true move the sequence pointer
            seqIdx +=1
        arrIdx +=1

    return seqIdx == len(sequence)

```

