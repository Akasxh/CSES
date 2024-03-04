### Link: https://cses.fi/problemset/task/1083

#### Time limit: 1.00 s
#### Memory limit: 512 MB



You are given all numbers between 1,2...n except one. Your task is to find the missing number.

### Input
The first input line contains an integer n.

The second line contains n-1 numbers. Each number is distinct and between 1 and n (inclusive).
### Output
Print the missing number.

### Constraints

2 <= n <= 2 . 10^5

### Example
#### Input:
5

2 3 1 5

#### Output:
4

## Approach:
### Brute force:
We can calculate using a summation function till n and subtract the elements we are fed. The number remaining will be the missing number.

### Smart move:
We can use number theory, where it states that summation of a number K from 1 to a finite digit n can be given as : 

                                                          n(n+1)/2

Using this formula we can get the summation in a easier way and do the same as brute force ie subtracting the elements we are being fed now.

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
  ll n;cin>>n;
  ll p= (n*(n+1))/2;
  for(ll i=0;i<(n-1);i++){
    ll x;cin>>x;
    p = p-x;
  }
  cout<<p<<"\n";
}
 
int main(){
    ios_base::sync_with_stdio(false), cin.tie(nullptr); 
    solve();
}
```
