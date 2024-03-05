#### Link: https://cses.fi/problemset/task/1069/

#### Time limit: 1.00 s
#### Memory limit: 512 MB


You are given a DNA sequence: a string consisting of characters A, C, G, and T. Your task is to find the longest repetition in the sequence.
This is a maximum-length substring containing only one type of character.

#### Input
The only input line contains a string of n characters.

#### Output
Print one integer: the length of the longest repetition.

#### Constraints

                                                     1 < n < 10^6

### Example

#### Input:
ATTCGGGA

#### Output:
3

## Solution

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
  
  string s;cin>>s;
  
  ll max1=0,max2=0;
  
  for(ll i=1;i<s.size();i++){
    if(s[i]==s[i-1]){
      max2 = max2 + 1;
    }
    else if(s[i]!=s[i-1]){
      max2 = 0;
    }
    
    if(max1<max2){
      max1=max2;
    }
  }
  
  cout<<max1+1<<"\n";
}

int main(){
    ios_base::sync_with_stdio(false), cin.tie(nullptr); 
    solve();
}

```
