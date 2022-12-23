### Task 6kyu:

The Padovan sequence is the sequence of integers defined by the initial values 
P(0) = P(1) = P(2) = 1 and the recurrence relation P(n) = P(n-2) + P(n-3) 
Your task is to write a method that returns nth Padovan number

[Task link](https://www.codewars.com/kata/5803ee0ed5438edcc9000087/train/java)

#### Solution:
```
public class Solution {
  public static long padovan(int n) {
    var a = new long[n + 3];
    a[0] = 1;
    a[1] = 1;
    a[2] = 1;
    for (var i = 2; i < n; i++) {
      a[i + 1] = a[i - 1] + a[i - 2];
    }
    return a[n];
  }
}   
```

#### Fav solution:
```
public class Solution {
  public static long padovan(int n) {
    var a = new long[n + 3];
    a[0] = 1;
    a[1] = 1;
    a[2] = 1;
    for (var i = 2; i < n; i++) {
      a[i + 1] = a[i - 1] + a[i - 2];
    }
    return a[n];
  }
} 
```

#### Comment:
My solution is compact and easy to understand. The task is easier than 6kyu.


### Task 6kyu:

Write a function, persistence, that takes in a positive parameter num and returns its multiplicative persistence,
which is the number of times you must multiply the digits in num until you reach a single digit.

[Task link](https://www.codewars.com/kata/56269eb78ad2e4ced1000013/train/java)

#### Solution:
```
class Persist {
 public static int persistence(long n) {
    int count = 0;
  while (n > 9){
      int p = 1;
      long k = n;
      while(k >= 1){
        p *= k % 10;
        k /= 10;
      }
      count += 1;
      n = p;
    }
    return count;
 }
} 
```

#### Fav solution:
```
class Persist {
	public static int persistence(long n) {
		long m = 1, r = n;

    if (r / 10 == 0)
      return 0;

    for (r = n; r != 0; r /= 10)
      m *= r % 10;

    return persistence(m) + 1;
    
	}
}
```

#### Comment:
It was interesting to count the cycle, the task is not particularly difficult.
