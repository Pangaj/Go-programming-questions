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
###3. Does Go support type inheritance?
* No support for type inheritance.

###4. Does Go support operator overloading?
* No support for operator overloading.

###5. Does Go support method overloading?
* No support for method overloading.

###6. Does Go support pointer arithmetics?
* No support for pointer arithmetic.

###7. Is Go a case sensitive language?
* Yes! Go is a case sensitive programming language.

###8. What is static type declaration of a variable in Go?
* Static type variable declaration provides assurance to the compiler that there is ***one variable existing with the given type and name*** so that compiler proceed for **further compilation without needing complete detail** about the variable. 
* A **variable declaration has its meaning at the time of compilation only**, compiler needs actual variable declaration at the **time of linking** of the program.

###9. What is dynamic type declaration of a variable in Go?
* A dynamic type variable declaration requires ***compiler to interpret the type of variable based on value passed to it***.
* *Compiler don't need a variable* to have **type statically as a necessary requirement**.

###10. Can you declared multiple types of variables in single declaration in Go?
* Yes, Variables of different types can be declared in one go using type inference.

   ```var a, b, c = 3, 4, "foo"```

###11. How to print type of a variable in Go?
* ```%T``` is used to print the type of a variable
   
   ```
   var a, b, c = 3, 4, "foo"
   fmt.Printf("a is of type %T\n", a)
   fmt.Printf("b is of type %T\n", b)
   fmt.Printf("c is of type %T\n", c)
   ```

###12. What is a pointer?
* It's a pointer variable which can hold the address of the variable.

   ```
   var x = 5
   var p *int
   p = &x
   fmt.Printf("x = %d", *p)
   ```
* Here x can be accessed by *p.

###13. Explain the syntax for 'for' loop.
* The syntax of a for loop in Go programming language is −
```
for [condition |  ( init; condition; increment ) | Range]
{
   statement(s);
}
```

* Here is the flow of control in a for loop −

    1. if condition is available, then for loop executes as long as condition is true.
    2. if for clause that is ( init; condition; increment ) is present then
    
    The init step is executed first, and only once. This step allows you to declare and initialize any loop control variables. You are not required to put a statement here, as long as a semicolon appears.
    
    Next, the condition is evaluated. If it is true, the body of the loop is executed. If it is false, the body of the loop does not execute and flow of control jumps to the next statement just after the for loop.

    After the body of the for loop executes, the flow of control jumps back up to the increment statement. This statement allows you to update any loop control variables. This statement can be left blank, as long as a semicolon appears after the condition.

    The condition is now evaluated again. If it is true, the loop executes and the process repeats itself (body of loop, then increment step, and then again condition). After the condition becomes false, the for loop terminates.

    3. if range is available, then for loop executes for each item in the range.







