class Solution {
public:
    vector<int> bucket[32];
    void radix_sort(vector<int>& nums) {
        // 1st round
        for (int x : nums)
            bucket[x&31].push_back(x);
        int i = 0;
        for (auto &B : bucket) {
            for (auto v : B)
                nums[i++] = v;
            B.clear();
        }
        // 2nd round
        for (int x : nums)
            bucket[x>>5].push_back(x);
        i=0;
        for (auto &B : bucket) {
            for (auto v : B)
                nums[i++] = v;
            B.clear();
        }
    }
    int n;
    //Use binary search to find number of nums[i]>=x
    inline int f(int x, vector<int>& nums){
        int i=lower_bound(nums.begin(), nums.end(), x)-nums.begin();
        return n-i;
    }
    inline int g(int x, vector<int>& nums){
        return f(x, nums)-x;
    }
    int specialArray(vector<int>& nums) {
        n=nums.size();
        radix_sort(nums);
        int l=0, r=n, m;
        
        // Binary search in the range [0, n]
        while (l <= r) {
            m = (l+r) / 2;
            int gm = g(m, nums);
            if (gm == 0) return m;
            else if (gm > 0) l = m+1;
            else r = m-1;
        }
        return -1;  
    }
};
