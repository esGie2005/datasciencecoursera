In order to determine the current working directory of R, we use the
**getwd()** function.

``` r
getwd()
```

    ## [1] "C:/Users/Kyle/Personal/OneDrive - carc.pshs.edu.ph/Coursera/Coursera - Data Science (Johns Hopkins)/datasciencecoursera/R Programming"

List all objects in the local workspace using **ls()**

``` r
ls()
```

    ## character(0)

assign x \<- 9 and look at the objects in the local workspace using
**ls()**

``` r
x <- 9
ls()
```

    ## [1] "x"

list all the files in the working directory using **list.files() or
dir()**

``` r
list.files()
```

    ##  [1] "hw1_data.csv"                          
    ##  [2] "testdir"                               
    ##  [3] "Week-1-data-types.Rmd"                 
    ##  [4] "Week-1-data.R"                         
    ##  [5] "Week-1-quiz.html"                      
    ##  [6] "Week-1-quiz.Rmd"                       
    ##  [7] "Week-1-reading-writing-data.html"      
    ##  [8] "Week-1-reading-writing-data.Rmd"       
    ##  [9] "Week-1-subsetting.html"                
    ## [10] "Week-1-subsetting.Rmd"                 
    ## [11] "Week-1-swirl-2-workspace-and-files.Rmd"
    ## [12] "Week-1-y.R"

using the **args() function** can see what arguments a function can take

``` r
args(list.files) # determines the arguments the function list.files() can take
```

    ## function (path = ".", pattern = NULL, all.files = FALSE, full.names = FALSE, 
    ##     recursive = FALSE, ignore.case = FALSE, include.dirs = FALSE, 
    ##     no.. = FALSE) 
    ## NULL

use **dir.create()** to make a new directory in the current working
directory and set working directory to the new one

``` r
old.dir <- getwd()    # saves the old directory
dir.create("testdir") # makes a new directory
```

    ## Warning in dir.create("testdir"): 'testdir' already exists

``` r
setwd("testdir")      # sets the new directory
```

create a file in the newly formed directory using **file.create()** and
check all the files in the working directory

``` r
file.create("mytest.R")
```

    ## [1] TRUE

``` r
list.files()
```

    ##  [1] "hw1_data.csv"                          
    ##  [2] "mytest.R"                              
    ##  [3] "testdir"                               
    ##  [4] "Week-1-data-types.Rmd"                 
    ##  [5] "Week-1-data.R"                         
    ##  [6] "Week-1-quiz.html"                      
    ##  [7] "Week-1-quiz.Rmd"                       
    ##  [8] "Week-1-reading-writing-data.html"      
    ##  [9] "Week-1-reading-writing-data.Rmd"       
    ## [10] "Week-1-subsetting.html"                
    ## [11] "Week-1-subsetting.Rmd"                 
    ## [12] "Week-1-swirl-2-workspace-and-files.Rmd"
    ## [13] "Week-1-y.R"

check if “mytest.R” exists in the working directory by using the
**file.exists()** function and access information about the file using
the **file.info()** function

``` r
file.exists("mytest.R") # determines if the file exists in the current wd
```

    ## [1] TRUE

``` r
file.info("mytest.R")   # accesses info about the said file
```

    ##          size isdir mode               mtime               ctime
    ## mytest.R    0 FALSE  666 2020-10-29 13:41:56 2020-10-29 13:41:56
    ##                        atime exe
    ## mytest.R 2020-10-29 13:41:56  no

rename the file by using the function, **file.rename** and make a copy
of the file using the function, **file.copy()**

``` r
file.rename("mytest.R", "mytest2.R") # renames the file
```

    ## [1] TRUE

``` r
file.copy("mytest2.R", "mytest3.R")  # makes a copy of a file
```

    ## [1] TRUE

provide the relative path to the file by using **file.path()**

``` r
file.path("mytest3.R")
```

    ## [1] "mytest3.R"

**file.path()** can be used to construct file and directory paths
independent of the OS the R code is running on. Pass folder1’ and
‘folder2’ as arguments to file.path() to make a platform-independent
pathname.

``` r
file.path("folder1", "folder2")
```

    ## [1] "folder1/folder2"

Create a directory in the current working directory called “testdir2”
and a subdirectory for it called “testdir3”, all in one command by using
**dir.create()** and **file.path()**.

``` r
dir.create(file.path("testdir2", "testdir3"), recursive = TRUE)
```

go back to the previous working directory

``` r
setwd(old.dir)
```
