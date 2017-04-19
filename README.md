# dinero

dinero is a [Go](https://golang.org) package for fetching exchange rates and converting between currencies. It aims to provide a simple interface and uses [hippasus' ExchangeRates](https://github.com/hippasus/ExchangeRates) and [decimal](https://github.com/shopspring/decimal), which allows for higher precision when working with the values representing currency.

[![Build Status](https://travis-ci.org/calmandniceperson/dinero.svg?branch=master)](https://travis-ci.org/calmandniceperson/dinero) [![Go Report Card](https://goreportcard.com/badge/github.com/calmandniceperson/dinero)](https://goreportcard.com/report/github.com/calmandniceperson/dinero) [![GoDoc](https://godoc.org/github.com/calmandniceperson/dinero?status.svg)](https://godoc.org/github.com/calmandniceperson/dinero)

## Installation

    go get github.com/calmandniceperson/dinero

## Examples

### Converting a value in one currency to another

```go
a := Amount{Value: decimal.NewFromFloat(5), Currency: USD}
res, _ := a.ConvertTo(EUR)
// res contains the converted value as a decimal
```

### Creating a certain amount of a currency

```go
u := USD
a := u.Amount(decimal.NewFromFloat(25000))
```

### Printing an amount of a certain currency

```go
a := Amount{decimal.NewFromFloat(450), JPY}
println(a.String())
```

## Dependencies

* [decimal](https://github.com/shopspring/decimal)

### For testing

* [testify](https://github.com/stretchr/testify)