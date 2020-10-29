A common scenario is when working with real-world data is that we want
to extract all elements of a vector that are not NA

``` r
my_vector <- 1:20
dim(my_vector)
```

    ## NULL

``` r
length(my_vector)
```

    ## [1] 20

as you can see, it doesn’t have a dim attribute since it’s just a
vector, but when you check its length.

We can give a vector dimensions, but it won’t be a vector anymore but a
matrix

``` r
dim(my_vector) <- c(4,5)
dim(my_vector) # This is one way to check dimensions OR
```

    ## [1] 4 5

``` r
attributes(my_vector); my_vector
```

    ## $dim
    ## [1] 4 5

    ##      [,1] [,2] [,3] [,4] [,5]
    ## [1,]    1    5    9   13   17
    ## [2,]    2    6   10   14   18
    ## [3,]    3    7   11   15   19
    ## [4,]    4    8   12   16   20

``` r
class(my_vector); my_matrix <- my_vector
```

    ## [1] "matrix" "array"

To delve on matrices further:

``` r
my_matrix2 <- matrix(1:20, nrow=4, ncol=5)
identical(my_matrix, my_matrix2) # determines if 2 variables are identical
```

    ## [1] TRUE

If we want my\_matrix data to represent names we can cbind them:

``` r
patients <- c("Bill", "Gina", "Kelly", "Sean")
cbind(patients, my_matrix)
```

    ##      patients                       
    ## [1,] "Bill"   "1" "5" "9"  "13" "17"
    ## [2,] "Gina"   "2" "6" "10" "14" "18"
    ## [3,] "Kelly"  "3" "7" "11" "15" "19"
    ## [4,] "Sean"   "4" "8" "12" "16" "20"

The numbers suddenly became characters cause matrices ONLY STORE ONE
CLASS of data - implicit coercion.

This problem can be easily solved by data frames:

``` r
my_data <- data.frame(patients, my_matrix)
```

With data frames, you can also name columns to identify what type of
measurement each column represents.

``` r
cnames <- c("patient", "age", "weight", "bp", "rating", "test")
colnames(my_data) <- cnames
```

colnames() attribute gives the columns their own name
