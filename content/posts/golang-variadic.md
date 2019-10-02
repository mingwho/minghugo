---
title: "Variadic Functions in Go"
date: 2019-10-01T15:26:00+04:00
draft: false
tags: ["golang"]
slug: "Golang Variadic"
---

## What are variadic functions?

Variadic functions are functions that can be called with any number of trailing arguments. In Golang, `fmt.Println` is a common variadic function.

```
fmt.Println("hello") // prints hello
fmt.Println("hello ", "world", 4, 2) // prints hello world 4 2
```

## How to write variadic functions?

To declare a variadic function, the type of the last argument is prefixed with `...`, which shows that this function can be called with any number of arguments of the same type.

```
func sum(nums ...int) int {
    total := 0
    for _, v := range nums {
        total += v
    }
    return total
}

func main() {
    fmt.Println(sum(1,2,3,4))
    //prints 10
}
```
[Try the snippet here](https://play.golang.org/p/IadnEUWSGG2)

If we already have a slice of multiple arguments, we can use `slice...` to unpack the slice and pass as arguments.

```
func main() {
    s := []int{1,2,3,4}
    fmt.Println(sum(s...))
    //prints 10
}
```

## What are some uses of variadic functions?

Variadic functions are extremely useful when we want to accept a variable number of arguments. For example, `strings.Join` function joins a string slice with separator string, and we can write a similar function that accepts an arbitrary number of strings as arguments.

```
func joinString(sep string, words ...string) string {
	result := ""
	for k, v := range words {
		result += v
		if k != len(words) - 1 {
			result += sep
		}
	}
	return result
}
func main() {
    fmt.Println(joinString(" ", "hello", "world"))
    // prints "hello world"
}
```
[Try the snippet here](https://play.golang.org/p/wMyyhzlPCDd)

