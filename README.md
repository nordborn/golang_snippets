# golang_snippets

## Inheritance
https://play.golang.org/p/hHj_GEpEFb
```
package main

import (
	"fmt"
)


// ColorNamer
type ColorNamer interface {
	Color() string
	Name() string
}

// common func
func cnDetails(cn ColorNamer) {
	fmt.Println(cn.Color(), cn.Name())
}


// A
type A struct {
	color string
	name  string
}

func (a *A) Color() string {
	return a.color
}

func (a *A) Name() string {
	return a.name
}


// B inherit A
type B struct {
	name string
	A
}

// redefine for B
func (b *B) Name() string {
	return b.name
}



func main() {
	a := A{"green", "A"}
	cnDetails(&a)
	b := B{"B", a}
	cnDetails(&b)
}


```

output

```
green A
green B
```
