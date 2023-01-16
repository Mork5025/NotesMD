# C

## Problem Statement

In a parallel universe, AtCoder holds AtCoder Big Contest, where 
$10^{16}$ problems are given at once.

The IDs of the problems are as follows, from the 1-st problem in order: A, B, ..., Z, AA, AB, ..., ZZ, AAA, ...

In other words, the IDs are given in the following order:

- the strings of length 1 consisting of uppercase English letters, in lexicographical order;
- the strings of length 2 consisting of uppercase English letters, in lexicographical order;
- the strings of length 3 consisting of uppercase English letters, in lexicographical order;
- ...

Given a string *S* that is an ID of a problem given in this contest, find the index of the problem. (See also Samples.)

## Constraints

- *S* is a valid ID of a problem given in AtCoder Big Contest.

## Code
```cpp
#include <cstdio>

int main()
{
    long long ans = 0;
    char ch;
    while ((ch = getchar()) != '\n' && ch != '\r' && ch != EOF)
        ans = ans * 26 + ch - 'A' + 1;
    printf("%lld\n", ans);

    return 0;
}

```