# The DataSpaceDonors class

An R6 class for DataSpace MAb Donor data.

## Constructor

`DataSpaceConnection$getMab()`

## See also

[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md)
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)

## Super class

[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)
-\> `DataSpaceDonors`

## Active bindings

- `mabMetadata`:

  A data.table of mAbs with metadata found in the object.

- `donorMetadata`:

  A data.table of donors with metadata found in the object.

- `datasets`:

  A list of data.table objects containing the related data loaded.

- `variableDefinitions`:

  A data.table of variable definitions.

## Methods

### Public methods

- [`DataSpaceDonors$new()`](#method-DataSpaceDonors-initialize)

- [`DataSpaceDonors$print()`](#method-DataSpaceDonors-print)

- [`DataSpaceDonors$loadDaash()`](#method-DataSpaceDonors-loadDaash)

- [`DataSpaceDonors$refresh()`](#method-DataSpaceDonors-refresh)

- [`DataSpaceDonors$clone()`](#method-DataSpaceDonors-clone)

Inherited methods

- [`DataSpaceConnection$downloadPublicationData()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-downloadPublicationData)
- [`DataSpaceConnection$filterMabGrid()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-filterMabGrid)
- [`DataSpaceConnection$getDaash()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-getDaash)
- [`DataSpaceConnection$getDonors()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-getDonors)
- [`DataSpaceConnection$getGroup()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-getGroup)
- [`DataSpaceConnection$getGroups()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-getGroups)
- [`DataSpaceConnection$getMab()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-getMab)
- [`DataSpaceConnection$getMabs()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-getMabs)
- [`DataSpaceConnection$getStudies()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-getStudies)
- [`DataSpaceConnection$getStudy()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-getStudy)
- [`DataSpaceConnection$loadLanlMabMetadata()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-loadLanlMabMetadata)
- [`DataSpaceConnection$resetMabGrid()`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.html#method-resetMabGrid)

------------------------------------------------------------------------

### `DataSpaceDonors$new()`

Initialize `DataSpaceMab` object. See
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md).

#### Usage

    DataSpaceDonors$new(donorIds)

#### Arguments

- `donorIds`:

  a character vector of \`donor_id\` values.

------------------------------------------------------------------------

### `DataSpaceDonors$print()`

Print the `DataSpaceMab` object summary.

#### Usage

    DataSpaceDonors$print()

------------------------------------------------------------------------

### `DataSpaceDonors$loadDaash()`

Load DAASH data to the object.

#### Usage

    DataSpaceDonors$loadDaash()

------------------------------------------------------------------------

### `DataSpaceDonors$refresh()`

Refresh the \`DataSpaceDonors\` object to update datasets.

#### Usage

    DataSpaceDonors$refresh()

------------------------------------------------------------------------

### `DataSpaceDonors$clone()`

The objects of this class are cloneable with this method.

#### Usage

    DataSpaceDonors$clone(deep = FALSE)

#### Arguments

- `deep`:

  Whether to make a deep clone.

## Examples

``` r
if (FALSE) { # \dontrun{
# Create a connection (Initiate a DataSpaceConnection object)
con <- connectDS()

# Print available donors to the console
con$availableDonors

# Query the available donors object and pass that to `getDonors` to get a DataSpaceDonors object
donors <- con$availableDonors[lineage_sequences_available == TRUE & donor_clade == "B",] |>
  con$getDonors()

# Load DAASH data to the object
donors$loadDaash()

} # }
```
