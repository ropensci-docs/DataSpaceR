# Write a netrc file

Write a netrc file that is valid for accessing DataSpace.

## Usage

``` r
writeNetrc(
  login,
  password,
  netrcFile = NULL,
  onStaging = FALSE,
  overwrite = FALSE
)
```

## Arguments

- login:

  A character. Email address used for logging in on DataSpace.

- password:

  A character. Password associated with the login.

- netrcFile:

  A character. Credentials will be written into that file. If left NULL,
  netrc will be written into a temporary file.

- onStaging:

  A logical. Whether to connect to the staging server instead of the
  production server.

- overwrite:

  A logical. Whether to overwrite the existing netrc file.

## Value

A character vector containing the netrc file path

## Details

The database is accessed with the user's credentials. A netrc file
storing login and password information is required. See
[here](https://docs.ropensci.org/DataSpaceR/) for instruction on how to
register and set DataSpace credential. By default `curl` will look for
the file in your home directory.

## See also

[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md)
[`checkNetrc`](https://docs.ropensci.org/DataSpaceR/reference/checkNetrc.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# First, create an account in the DataSpace App and read the terms of use
# Next, create a netrc file using writeNetrc()
writeNetrc(
  login = "dataspaceuser@email.com",
  password = "yourSecretPassword"
)
# Specify `netrcFile = getNetrcPath()` to write netrc in the default path
} # }
```
