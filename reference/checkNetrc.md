# Check netrc file

Check that there is a netrc file with a valid entry for the CAVD
DataSpace.

## Usage

``` r
checkNetrc(netrcFile = getNetrcPath(), onStaging = FALSE, verbose = TRUE)
```

## Arguments

- netrcFile:

  A character. File path to netrc file to check.

- onStaging:

  A logical. Whether to check the staging server instead of the
  production server.

- verbose:

  A logical. Whether to print the extra details for troubleshooting.

## Value

The name of the netrc file

## See also

[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md)
[`writeNetrc`](https://docs.ropensci.org/DataSpaceR/reference/writeNetrc.md)

## Examples

``` r
if (FALSE) { # \dontrun{
checkNetrc()
} # }
```
