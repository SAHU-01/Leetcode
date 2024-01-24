/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
 #pragma GCC optimize("O3", "unroll-loops")
class Solution {
public:
    int ans=0;
    void dfs(TreeNode* node, bitset<10> parity){
        if (!node) return;
        int x=node->val;
        parity[x]=~parity[x];
        if (!node->left && !node->right){
            if(parity.count()<=1) ans++;
            return ;
        }
        dfs(node->left, parity);
        dfs(node->right, parity);
    }
    int pseudoPalindromicPaths (TreeNode* root) {
        bitset<10> parity=0;
        dfs(root, parity);
        return ans;
    }
};

auto init = []()
{ 
    ios::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);
    return 'c';
}();
