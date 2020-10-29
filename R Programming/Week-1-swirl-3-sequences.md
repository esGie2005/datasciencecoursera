Sequences are normally initiated using:

``` r
1:20  # As you can see it increments by 1 until the value > 20
```

    ##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20

``` r
pi:10 # As you can see it still increments by 1 until the value is > 10
```

    ## [1] 3.141593 4.141593 5.141593 6.141593 7.141593 8.141593 9.141593

``` r
20:1  # As you can see it increments by -1 until the value < 1
```

    ##  [1] 20 19 18 17 16 15 14 13 12 11 10  9  8  7  6  5  4  3  2  1

or can be initialized using the seq function for more controlled purpose

``` r
seq(1,20) # sequence from 1 to 20, increment 1
```

    ##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20

``` r
seq(1,50,by=5) # sequence from 1 to 50, increment 5
```

    ##  [1]  1  6 11 16 21 26 31 36 41 46

``` r
my_seq <- seq(1,10,length=30); my_seq # sequence of 30 numbers from 1 to 50, neverminding the increment
```

    ##  [1]  1.000000  1.310345  1.620690  1.931034  2.241379  2.551724  2.862069
    ##  [8]  3.172414  3.482759  3.793103  4.103448  4.413793  4.724138  5.034483
    ## [15]  5.344828  5.655172  5.965517  6.275862  6.586207  6.896552  7.206897
    ## [22]  7.517241  7.827586  8.137931  8.448276  8.758621  9.068966  9.379310
    ## [29]  9.689655 10.000000

``` r
length(my_seq) # use length() to confirm its length
```

    ## [1] 30

assuming length is unknown, we must generate a sequence from 1 to N. In
other words, we want a new vector with the same length as my\_seq. One
possibility is:

``` r
1:length(my_seq)
```

    ##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    ## [26] 26 27 28 29 30

or to use:

``` r
seq(along.with = my_seq)
```

    ##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    ## [26] 26 27 28 29 30

r, however, has a built-in function for this purpose:

``` r
seq_along(my_seq)
```

    ##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    ## [26] 26 27 28 29 30

one function related to creating sequences of numbers is rep(), which
stands for ‘replicate’. One of the uses is if we’re interested in
creating a vector that contains 40 zeros:

``` r
rep(0, times = 40)
```

    ##  [1] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
    ## [39] 0 0

If instead we want our vector to contain 10 repetitions of the vector
(0, 1, 2)

``` r
rep(c(0, 1, 2), times = 10)
```

    ##  [1] 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2

Finally, let’s say that rather than repeating the vector (0, 1, 2) over
and over again, we want our vector to contain 10 zeros, then 10 ones,
then 10 twos. We can do this with the `each` argument.

``` r
rep(c(0, 1, 2), each = 10)
```

    ##  [1] 0 0 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1 1 1 2 2 2 2 2 2 2 2 2 2
