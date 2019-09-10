package fuse

import "reflect"

/**
 * It receives 2 structs and fuses data with the same field name
 * return interface
 */
func Fuse(from, into interface{}) interface{} {
	x := reflect.ValueOf(from).Elem()
	y := reflect.Indirect(reflect.ValueOf(into))

	for i := 0; i < y.NumField(); i++ {
		typeField := y.Type().Field(i)
		otherValue := x.FieldByName(typeField.Name)

		if otherValue.IsValid() {
			if y.CanSet() {
				y.Field(i).Set(otherValue)
			}
		}
	}
	return y.Interface()
}
