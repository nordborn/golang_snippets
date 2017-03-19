# golang_snippets

## Inheritance
https://play.golang.org/p/x11hzUQF0V
```
package main

import (
	"fmt"
)


// ColorNamer
type ColorNamer interface {
	GetColor() string
	GetName() string
}

// common func
func you(cn ColorNamer) {
	fmt.Println(cn.GetColor(), cn.GetName())
}


// A
type A struct {
	Color string
	Name  string
}

func (a *A) GetColor() string {
	return a.Color
}

func (a *A) GetName() string {
	return a.Name
}


// B
type B struct {
	Name string
	A
}

// redefine for B
func (b *B) GetName() string {
	return b.Name
}



func main() {
	a := A{"green", "A"}
	you(&a)
	b := B{"B", a}
	you(&b)
}
```
