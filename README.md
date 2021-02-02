# exhaustivestruct

Cloned from [mbilski/exhaustivestruct](https://github.com/mbilski/exhaustivestruct): a go static analysis tool to find structs that have uninitialized fields.

Changes:

- Check for private fields in the same package
- Check for unnamed field initializations

## Installation

```
go get -u github.com/jiping-s/exhaustivestruct/cmd/exhaustivestruct@master
```

## Usage

```
Usage: exhaustivestruct [-flag] [package]

Flags:
  -struct_patterns string
      This is a comma separated list of expressions to match struct packages and names
```

## Example

``` go
type User struct {
  Name string
  Age int
}

var user = User{ // fails with "Age is missing in User"
  Name: "John",
}
```

