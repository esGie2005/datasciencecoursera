Vectors
-------

Vectors come in two different flavors: atomic vectors and lists. An
atomic vector contains exactly one data type, whereas a list may contain
multiple data types.

logical vectors in action:

``` r
num_vect <- c(0.5, 55, -10, 6)
tf <- num_vect < 1; tf
```

    ## [1]  TRUE FALSE  TRUE FALSE

``` r
num_vect >= 6
```

    ## [1] FALSE  TRUE FALSE  TRUE

character vectors in action:

``` r
my_char <- c("My", "name", "is")
paste(my_char, collapse = " ") # Joins the my_char together separated by spaces
```

    ## [1] "My name is"

``` r
my_name <-c(my_char, "Kyle") # concatenates my name and my_char
paste(my_name, collapse = " ")
```

    ## [1] "My name is Kyle"

``` r
paste("Hello", "world!", sep = " ")
```

    ## [1] "Hello world!"

``` r
paste(1:3, c("X", "Y", "Z"), sep = "")
```

    ## [1] "1X" "2Y" "3Z"

``` r
paste(LETTERS, 1:4, sep = "-")
```

    ##  [1] "A-1" "B-2" "C-3" "D-4" "E-1" "F-2" "G-3" "H-4" "I-1" "J-2" "K-3" "L-4"
    ## [13] "M-1" "N-2" "O-3" "P-4" "Q-1" "R-2" "S-3" "T-4" "U-1" "V-2" "W-3" "X-4"
    ## [25] "Y-1" "Z-2"

Missing Values
--------------

Missing values play an important role in statistics and data analysis.
Often, missing values must not be ignored, but rather they should be
carefully studied to see if there’s an underlying pattern or cause for
their missingness.

Here is an example:

``` r
x <- c(44, NA, 5, NA)
x * 3
```

    ## [1] 132  NA  15  NA

``` r
y <- rnorm(1000) # 1000 draws from a standard normal distribution
z <- rep(NA, 1000)
my_data <- sample(c(y,z), 100) # let's select 100 elements at random from these 2000 values (combining y and z) such that we don't know how many NAs we'll wind up with or what positions they'll occupy in our final vector

my_na <- is.na(my_data)
sum(my_na) # Since FALSE (numerical) is 0 and TRUE (NA) is 1, by adding up my_na can we determine the number of NAs
```

    ## [1] 50
