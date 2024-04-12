# QUESTION : 42. Trapping Rain Water

Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.


## Example 1: <br>
Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]<br>
Output: 6<br>
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.<br>

## Example 2:<br>
Input: height = [4,2,0,3,2,5]<br>
Output: 9<br>


```
class Solution {
public:
    int trap(vector<int>& arr) {
        int n =  arr.size();
        int lmax = 0, rmax = 0;
        int l = 0, r = n-1;
        int res = 0;
        while(l<=r){
            if(arr[l]<=arr[r]){
                if(lmax<arr[l]) lmax = arr[l];
                else res = res+ (lmax-arr[l]);
                l++;

            }else{
                if(rmax<arr[r]) rmax = arr[r];
                else res = res+(rmax-arr[r]);
                r--;
            }
      }
        return res;

    }
};
```
