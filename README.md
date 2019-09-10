# fuse

A simple tool to fuse/merge structs from different  or equal types that share the same fields name 

##### Example

```go
type ExampleA struct {
	Name string
	Id int
	City string
	Alias []string
}

type ExampleB struct {
	Name string
	City string
	Country string
	Bank string
	TotalBalance float64
}


func main() {
	
	a := &ExampleA{} //populate with some data
	b := &ExampleB{} //populate with some data
	
	result := Fuse(a, b).(ExampleA)

}
```
