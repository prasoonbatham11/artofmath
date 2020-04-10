---
layout: page
title: Toolkit
description:
---

# GCD

```java
public static long gcd(long a, long b) {
    if (b==0) {
        return a;
    }
    else {
        return gcd(b, a%b);
    }
}
```

# Sieve of Eratosthenes

```java
public static int[] sieve(int size) {
    boolean sieve[]=new boolean[size];
    Arrays.fill(sieve,true);
    sieve[0]=sieve[1]=false;
    int p,j,i=1;
    int[] prime = new int[size];
    for(p=2;p*p<size;p++) {
        if(sieve[p]) {
            for(j=p*p;j<size;j+=p) {
                sieve[j]=false;
            }
        }
    }
    for(j=2;j<sieve.length;j++) {
        if(sieve[j]) {
            prime[i++] = j;
        }
    }
    return prime;
}
```