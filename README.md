# leetcode_bugfree

Subarray Sum Equals K 
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
        int ret = 0;
        int sums[nums.size()];
        sums[0] = nums[0];
        for(int i = 1; i < nums.size(); i++) {
            sums[i] = sums[i -1] + nums[i];
        }
        
        for(int i = 0; i < nums.size(); i++) {
            //if(nums[i] == k) {
                //ret++;
            //}
            
            for(int j = 0; j < i; j++) {
                if(k == sums[i] - sums[i]) {
                    ret++;
                }
            }
        }
        
        return ret;
    }
};
