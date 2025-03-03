class Solution(object):
    def pivotArray(self, nums, pivot):
        """
        :type nums: List[int]
        :type pivot: int
        :rtype: List[int]
        """
        n=len(nums)
        leftArr=[]
        rightArr=[]
        pivCnt=0

        # Traverse the array to count pivot elements and segregate elements
        for i in range(0, n):
            if nums[i]==pivot:
                pivCnt+=1
            elif nums[i]>pivot:
                rightArr.append(nums[i])                
            else:
                leftArr.append(nums[i])                
        
        return leftArr+[pivot]*pivCnt+rightArr
