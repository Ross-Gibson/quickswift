---
title:  "Where"
<!-- date:   2015-11-19 13:00:00 -->
description: Where to use where
---

### Requirements
- Swift 2.0
- iOS 9
- Xcode 7

---

### ⌘ + C, ⌘ + V
```swift
let numbers = [-3, -2, -1, 0, 1, 2, 3]

fooWhere(numbers)

func fooWhere(numbers: [Int]) {
	for number in numbers where number > 0 {
        print(number) // prints: "1, 2, 3"
    }
}
```
---

### **DO NOT READ THIS**
Code inside a defer will always be executed before the block looses scope. This can be very useful for error handeling [__1__].

- Defers execution until the current scope is exited
- Called regardless of how execution leaves the current block of code
- Defers can be stacked. When doing this deferred actions are executed in reverse order of how they are specified
- __Do not__ try to exit scope inside a defer by using return, break or by throwing an error

---

### TL;DR
The guard keyword in Swift 2.0 gives rise to clearer and easier to read early returns. It enables for a [happy path](https://en.wikipedia.org/wiki/Happy_path "Wikipedia") in the logic, meaning that conditions are checked against the expected result opposed to reversing the logic and testing for the case that would result in an error. This approach improves readability and generally results in less code with fewer bugs.

Comparing the code below with the version above highlights the happy path and shows how variables unwrapped from optionals can remain in scope.

```swift
func fooGuard(value: Int?) {
    // Check for errors
    if value == nil {
        // Handle the error here
        return
    } else {
        // Do something with the value here
        print(value)
    }
}
```

---

### Notes

 [__1__] A defer statement can be used even when no error handling code is involved.

---

### Enlightenment
- [Marcin Krzyżanowski: Where "where" may be used?](http://blog.krzyzanowskim.com/2015/11/13/where-where-may-be-used/ "Marcin Krzyżanowski's Blog")
