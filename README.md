# bitmap
Simple bitmap in go

## example

```
package main

import (
	"fmt"
	"github.com/weint/bitmap"
)

func main() {

	addNum := uint(500)

	btm := bitmap.New()

	for i := uint(1); i < addNum; i++ {
		btm.Add(i)
	}

	fmt.Println("btm len", btm.Len(), "Words len", len(btm.Words))
	fmt.Println(btm.String())
	fmt.Println(btm.Lst())

	for i := uint(1); i < addNum; i++ {
		if !btm.Has(i) {
			fmt.Println("not has", i)
			return
		}
	}

	for i := uint(1); i < addNum; i++ {
		btm.Del(i)
	}

	fmt.Println("btm len", btm.Len(), "Words len", len(btm.Words))
	fmt.Println(btm.String())

	btm.ReSize()
	btm.Add(uint(100))
	fmt.Println("btm len", btm.Len(), "Words len", len(btm.Words))
	fmt.Println(btm.String())

}

```
