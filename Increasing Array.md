### Link: https://cses.fi/problemset/task/1094/

#### Time limit: 1.00 s
#### Memory limit: 512 MB



You are given an array of n integers. You want to modify the array so that it is increasing, i.e., 
every element is at least as large as the previous element.
On each move, you may increase the value of any element by one. What is the minimum number of moves required?

### Input
The first input line contains an integer n: the size of the array.

Then, the second line contains n integers x1,x2...xn : the contents of the array.

### Output
Print the minimum number of moves.

### Constraints

1 < n < 2 . 10^5
1 < xi < 10^9

### Example

#### Input:
5

3 2 5 1 7

#### Output:
5

## Approach:
We need to check if "I" and "i+1" are **atleast equal**. For that specific iteration, steps to make them equal is given by:

                                          x = arr[i] - arr[i+1]

where x is the number of steps for this specific iteration. Now as they can be made equal just make :
                                         
                                           arr[i+1] = arr[i]

By doing this you are changing the i+1 element inside the array.


## Solution:

```cpp
#include<bits/stdc++.h>
#include <iostream>
#include <vector>
#include <algorithm>
#include <numeric>
#define ll long long

using namespace std;

#pragma GCC optimize ("O3")
#pragma GCC target ("sse4")


void solve(){
  
  int n;cin>>n;
  vector<int> arr;
  for(int i=0;i<n;i++){
    int num;cin>>num;
    arr.push_back(num);
  }
  

  ll steps=0; 
  
  for(int i=0;i<n-1;i++){
    if(arr[i+1]<arr[i]){
      steps = steps + (arr[i]-arr[i+1]);
      arr[i+1]=arr[i];
    }
  }
  
  cout<<steps <<"\n";
  
}

int main(){
    ios_base::sync_with_stdio(false), cin.tie(nullptr); 
    solve();
}
```



