Problem Statement
In Max Consecutive Ones problem a binary array is given. We have to find the maximum number of consecutive ones present in the given array.
The input array will only contain 0 and 1.

Example
Input
[1,1,0,1,1,1]
Output
3

Explanation:
The first two digits or the last three digits are consecutive 1s.
The maximum number of consecutive 1s is 3.

Approach
To solve this problem we can iterate through the indices in the array in two nested while loop by following algorithm:

1. Create a variable maximum which will store the updated maximum consecutive 1s during traversing.
2. Create and initialize a variable i with first index.
3. Now run a while loop until i < array size.
4. Inside the loop we will check if number at current index i is 1 or not. If it is not equal to 1 then simply increment the index i. Else if it is equal to 1, then run a nested while loop by creating a count variable and initialize with 0. Then  traverse the array for consecutive 1s in that nested while loop. i.e. traverse array while num[i] is equal to 1, along with keep incrementing the count of current consecutive 1s  as shown in figure below:


Implementation
C++ Program for Max Consecutive Ones Leetcode Solution

#include <bits/stdc++.h>
using namespace std;
int findMaxConsecutiveOnes(vector<int>& nums) {
    int maximum=0;
    int i=0;
    while(i<nums.size())
    {
        int conOnes=0;
        while(i< nums.size() && nums[i]==1)
        {
            conOnes++;
            i++;
        }
        maximum=max(maximum,conOnes);
        i++;
    }
    return maximum; 
}
int main() 
{
    vector<int> nums={1,1,0,1,1,1};
    cout<<findMaxConsecutiveOnes(nums)<<endl;
  return 0; 
}
  
  
  
  
  
  
  
Time Complexity
O(N) : We are traversing the array from starting index to last index and visiting each index only once. Therefore time complexity will be linear O(N).

Space Complexity 
O(1) : We are not using any extra space, hence space utilized is constant.
  
