### 1. How do you swap two values?

* Two values are swapped as easy as this:
    ```a, b = b, a```

* To swap three values, we would write:
    ```a, b, c = b, c, a```

* The swap operation in Go is guaranteed from side effects. The values to be assigned are guaranteed to be stored in temporary variables before starting the actual assigning, so the order of assignment does not matter. The result of the following operation: ```a := 1; b := 2; a, b, a = b, a, b``` is still ```a = 2``` and ```b = 1```, without the risk of changing the value ```a``` to the new re-assigned value. This is useful to rely on in many algorithm implementations.

For example, a function that reverses a slice of integers in place:

```
func reverse(s []int) {
        for i, j := 0, len(s)-1; i < j; i, j = i+1, j-1 {
                s[i], s[j] = s[j], s[i]
        }
}

func main() {
    a := []int{1, 2, 3}
    reverse(a)
    fmt.Println(a)
    // Output: [3 2 1]
}
```

### 2. What is the difference, if any, in the following two slice declarations, and which one is more preferable?```var a []int``` and ```a := []int{}```

* The first declaration does not allocate memory if the slice is not used, so this declaration method is preferred.


