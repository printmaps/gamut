# gamut

Go package to generate and manage color palettes & schemes

## Examples

### Generating Color Palettes

```go
import "github.com/muesli/gamut"

colors, err := gamut.Generate(8, gamut.PastelGenerator{})
// returns a slice of 8 pastel colors
```

Instead of `gamut.PastelGenerator` you can also use `gamut.WarmGenerator` or
`gamut.HappyGenerator`.

### Name A Color

```go
name, distance := gamut.Wikipedia.Name(color)
// name = "Baby blue"
// distance between 0.0 and 1.0
```

### Retrieving Colors

```go
colors = gamut.Crayola.Filter("Red")
// returns a slice of all "Red" colors in the Crayola palette
colors = gamut.Crayola.Colors()
// returns a slice of all colors in the Crayola palette
```

### Complementary Colors

```go
c = gamut.Complementary(color)
```

### Contrast Colors

```go
c = gamut.Contrast(color)
```

### Warm/Cool Colors

```go
b = gamut.Warm(color)
b = gamut.Cool(color)
// either true or false
```

### Hue Offsets

```go
colors = gamut.Triadic(color)
// slice of triadic colors
colors = gamut.Quadratic(color)
// slice of quadratic colors
colors = gamut.Analogous(color)
// slice of analogous colors
colors = gamut.SplitComplementary(color)
// slice of split-complementary colors
```

### Shades & Tints

```go
colors = gamut.Shades(color, 8)
// returns a slice of 8 shades, from color to black
colors = gamut.Tints(color, 8)
// returns a slice of 8 tints, from color to white
```

### Mixing Palettes

```go
p = gamut.Crayola.MixedWith(gamut.Monokai)
// returns a palette with all colors from both Crayola and Monokai
```

## Development

[![GoDoc](https://godoc.org/github.com/golang/gddo?status.svg)](https://godoc.org/github.com/muesli/gamut)
[![Build Status](https://travis-ci.org/muesli/gamut.svg?branch=master)](https://travis-ci.org/muesli/gamut)
[![Coverage Status](https://coveralls.io/repos/github/muesli/gamut/badge.svg?branch=master)](https://coveralls.io/github/muesli/gamut?branch=master)
[![Go ReportCard](http://goreportcard.com/badge/muesli/gamut)](http://goreportcard.com/report/muesli/gamut)
