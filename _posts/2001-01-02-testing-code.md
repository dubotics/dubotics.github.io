---
layout: blog-post
title: Testing code
category: control-systems-team
author: Alice
code: true
---

Here is an example of what code would look like inline -- `std::cout << "Hello world" << std::endl;`.
There is, unfortunately, no syntax highlighting. You can use a code block instead:

```c++
#include <iostream>

int main() {
    std::cout << "Hello world" << std::endl;
    return 0;
}
```

<!--more-->

And now, for a larger code block. Here is some Python code:

```python
def factorial(n):
    return n * factorial(n - 1)
    
if __name__ == '__main__':
    print factorial(10)
```

Here is some Java code:

```java
public class Factorial {
    public static void main(String[] args) {
        System.out.println(factorial(10));
    }
    
    public static int factorial(int n) {
        return n * factorial(n - 1)
    }
}
```

