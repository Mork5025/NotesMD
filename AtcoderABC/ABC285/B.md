# B

## Problem Statement

You are given a string *S* of length *N* consisting of lowercase Englishletters. The *x*-th (1≤*x*≤N)character of *S* is $S_{x}$.

For each *i*=1,2,…,*N*−1, find the maximumnon-negative integer *l* thatsatisfies all of the following conditions:

- *l+i≤N*, and
- for all integers *k* such that 1≤*k*≤l, it holds that $S_{k}$!=$S_{k+1}$.


Note that *l*=0 always satisfies the conditions.

## Constraints
- *N* is an integer such that 2≤*N*≤5000.
- *S* is a string of length 
*N* consisting of lowercase English letters.

## Code
```cpp
#include <stdio.h>

const int MAX = 7500;

int N, Ans;
char in[MAX];

int main() {
	int i, u;

	scanf("%d%s", &N, in);
	for (i = 1; i < N; i++) {
		for (u = Ans = 0; u + i < N; u++) if (in[u] == in[u + i]) break;
		printf("%d\n", u);
	}

	return 0;
}

```