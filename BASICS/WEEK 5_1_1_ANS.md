#### 1 Solution:
```c
#include <stdio.h>

int main() {
    int num = 10;
    int *ptr = &num;
    
    printf("Value of num: %d\n", *ptr);
    
    return 0;
}
```

#### 2 Solution:
```c
#include <stdio.h>

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int *ptr = arr;
    
    for(int i = 0; i < 5; i++) {
        printf("Element %d: %d\n", i, *(ptr + i));
    }
    
    return 0;
}
```

#### 3 Solution:
```c
#include <stdio.h>

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 5, y = 10;
    
    printf("Before swap: x = %d, y = %d\n", x, y);
    swap(&x, &y);
    printf("After swap: x = %d, y = %d\n", x, y);
    
    return 0;
}
```

#### 4 Solution:
```c
#include <stdio.h>

int main() {
    int num = 20;
    int *ptr = &num;
    int **ptr_ptr = &ptr;
    
    printf("Value of num: %d\n", **ptr_ptr);
    
    return 0;
}
```

#### 5 Solution:
```c
#include <stdio.h>

void sum(int *a, int *b, int *result) {
    *result = *a + *b;
}

int main() {
    int x = 3, y = 7, result;
    
    sum(&x, &y, &result);
    printf("Sum: %d\n", result);
    
    return 0;
}
```

#### 6 Solution:
```c
#include <stdio.h>

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int (*ptr)[5] = &arr;
    
    for(int i = 0; i < 5; i++) {
        printf("Element %d: %d\n", i, (*ptr)[i]);
    }
    
    return 0;
}
```

#### 7 Solution:
```c
#include <stdio.h>

int main() {
    char *str = "Hello, World!";
    
    printf("String: %s\n", str);
    
    return 0;
}
```