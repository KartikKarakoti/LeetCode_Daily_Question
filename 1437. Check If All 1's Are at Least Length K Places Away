class Solution {
public:
    bool kLengthApart(vector<int>& nums, int k) {
        int n=nums.size(), last=-1e9;
        for(int i=0; i<n; i++){
            if (nums[i]==1){
                if (i-last-1<k) return 0;
                last=i;
            }
        }
        return 1;
    }
};
