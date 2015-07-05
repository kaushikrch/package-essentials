---
title       : R-Package Essentials
author      : Kaushik Roy Chowdhury
framework   : io2012
highlighter : highlight.js  
hitheme     : github 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Classes

* Objects sharing specific attributes. 


```r
x <- c(1, 2, 3)
class(x)
```

```
## [1] "numeric"
```

```r
mod <- lm(mpg ~ disp, data = mtcars)
class(mod)
```

```
## [1] "lm"
```

* Example: an object of class "lm", generated from the lm function,
is really just a list with some specific attributes

---

## Methods

<style>
em {
  font-style: italic
}
</style>
<style>
strong {
  font-weight: bold;
}
</style>

* Functions that behave differently depending on the class of their input. 


```r
print(x)
```

```
## [1] 1 2 3
```

```r
print(mod)
```

```
## 
## Call:
## lm(formula = mpg ~ disp, data = mtcars)
## 
## Coefficients:
## (Intercept)         disp  
##    29.59985     -0.04122
```

---

## Method Dispatching

* **Generic Functions**: Functions that pass objects to the right function. `print()`, `predict()` are two such widely used functions.


```r
print
```

```
## function (x, ...) 
## UseMethod("print")
## <bytecode: 0x00000000071a5c10>
## <environment: namespace:base>
```

* `UseMethod()` tells R to look for a function that can deal with the type of object passed in `x`.

* To see how many printing methods are present with base R distribution type `methods(print)`.

* Creating a new class with methods can drastically improve the
usability of the function and results.

---

## License

* CRAN accepts packages only with open-source licensing listed [here](https://svn.r-project.org/R/trunk/share/licenses/license.db).

* "The package's license must give the right for CRAN to distribute the package in perpetuity." -- [CRAN Policies](http://cran.r-project.org/web/packages/policies.html)

<iframe width="400" height="75" frameborder="1" src = "https://tldrlegal.com/license/gnu-general-public-license-v3-(gpl-3)">
</iframe>



