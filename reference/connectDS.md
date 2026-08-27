# Create a connection to DataSpace

Constructor for
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)

## Usage

``` r
connectDS(login = NULL, password = NULL, verbose = FALSE, onStaging = FALSE)
```

## Arguments

- login:

  A character. Optional argument. If there is no netrc file a temporary
  one can be written by passing login and password of an active
  DataSpace account.

- password:

  A character. Optional. The password for the selected login.

- verbose:

  A logical. Whether to print the extra details for troubleshooting.

- onStaging:

  A logical. Whether to connect to the staging server instead of the
  production server.

## Value

an instance of `DataSpaceConnection`

## Details

Instantiates an `DataSpaceConnection`. The constructor will try to take
the values of the various `labkey.*` parameters from the global
environment. If they don't exist, it will use default values. These are
assigned to \`options\`, which are then used by the
`DataSpaceConnection` class.

## See also

[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)

## Examples

``` r
if (FALSE) { # \dontrun{
con <- connectDS()
} # }
```
