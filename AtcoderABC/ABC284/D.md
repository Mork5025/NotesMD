### Problem Statement

You are given a positive integer $N$. It is known that $N$ can be represented as $N=p^2q$ using two different prime numbers $p$ and $q$ .

You have $T$ test cases to solve.

### Constraints

- All values in the input are integers.
- $1≤T≤10$
- $1≤N≤9×10^{18}$
- *N* can be represented as $N=p^2q$ using two different prime numbers *p* and *q*.

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
  ios::sync_with_stdio(false);
  cin.tie(nullptr);
  int T;
  cin>>T;
  vector<bool>prime((int)3e6,true);
  prime[0]=prime[1]=false;
  for(long long i=2;i<3e6;i++){
    if(!prime[i])continue;
    for(long long j=i*i;j<3e6;j+=i){
      prime[j]=false;
    }
  }
  while(T--){
    long long N;
    cin>>N;
    long long p=0,q=0;
    for(int i=2;i<3e6;i++){
      if(!prime[i])continue;
      if(N%i==0){
        if(N/i%i==0){
          p=i,q=N/i/i;
        }else{
          q=i,p=sqrt(N/i);
          for(long long j=p-10,k=p+10;j<k;j++){
            if(j*j==N/i)p=j;
          }
        }
        break;
      }
    }
    cout<<p<<' '<<q<<'\n';
  }
}
```

