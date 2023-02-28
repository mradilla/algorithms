## **Big O**

Is a way to categorize your algorithms time or memory requirements based on input.

Said differently: _as your input grows, how fast does computation or memory grow?_

Simplest trick and all of it is just simply look for loops: _where do you loop over the input?_

## Examples

### **O(1) - Constant time**

Constant time algorithms will always take same amount of time to be executed. 
The execution time of these algorithm is independent of the size of the input. 
A good example of O(1) time is accessing a value with an array index.

```java
int[] array = new int[]{1, 2, 3, 4, 5};
int n = array[3]; // 2
```
The operation to access an index is always calculated as:

`array + width * offset`

where:

```
array = memory address
width = data type size (4 bytes for an int)
offset = the index
```

### **O(N) - Linear time**

---

This method is O(N) because iterates over the input once, growing linearly:

```java
int sumCharCodes(String n) {
    int sum = 0;
    for (int i = 0; i < n.length(); i++) {
    sum += n.charAt(i);
    } return sum;
}
```

The following one uses two for loops, seems like O(2N)…

```java
int sumCharCodes(String n) {
    int sum = 0;
    for (int i = 0; i < n.length(); i++) {
        sum += n.charAt(i);
    }
    for (int i = 0; i < n.length(); i++) {
        sum += n.charAt(i);
    }
    return sum;
}
```

but it is O(N), this is because in big O notation we drop the constants.

Now, this method has a loop and finish the loop once we find a Capital E… O(N-1)? O(N-2)?

```java
int sumCharCodes(String n) {
    int sum = 0;
    for (int i = 0; i < n.length(); i++) {
        char charCode = n.charAt(i);
        // Capital E
        if (charCode == 69) {
            return sum;
        }
        sum += n.charAt(i);
    }
    return sum;
}
```

Still O(N), because we consider the worst case scenario, which is `n` being a string without an E or with an E at the end, we are going to go through all of it.

### O(N^2) - Quadratic time

---

In the following example, for every single character in the string, we are going to go over every single character in the string, it is like computing the area of a square.

```java
int sumCharCodes(String n) {
    int sum = 0;
    for (int i = 0; i < n.length(); i++) {
        for (int j = 0; j < n.length(); j++) {
            sum += n.charAt(i);
        }
    }
    return sum;
}
```

### O(N^3) - Cubic time

---

```java
int sumCharCodes(String n) {
    int sum = 0;
    for (int i = 0; i < n.length(); i++) {
        for (int j = 0; j < n.length(); j++) {
            for (int k = 0; k < n.length(); k++) {
                sum += n.charAt(i);
            }
        }
    }
    return sum;
}
```

Another example would be [multiplying a matrix](https://www.baeldung.com/cs/matrix-multiplication-algorithms#2-time-complexity-analysis).

### O(n log n)

---

[Quicksort](https://big-o.io/algorithms/comparison/quicksort/)

### O(log n) - Logarithmic time

---

Binary search trees

## Important concepts

1. Growth is with respect to the input
2. Constants are dropped
3. Worst case is usually the way we measure

## Alternatives

- Stata
- [Little Omega](https://www.geeksforgeeks.org/analysis-of-algorithems-little-o-and-little-omega-notations/)