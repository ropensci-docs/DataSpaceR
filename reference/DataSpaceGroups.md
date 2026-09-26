# The DataSpaceGroups class

An R6 class for DataSpace Groups data.

## Constructor

`DataSpaceConnection$getGroups()`

## See also

[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md)
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)

## Super class

[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)
-\> `DataSpaceGroups`

## Active bindings

- `availableDatasets`:

  A data.table of datasets available in the object.

- `datasets`:

  A list of data.table objects containing the availableDatasets that
  were loaded.

- `variableDefinitions`:

  A data.table of variable definitions.

## Methods

### Public methods

- [`DataSpaceGroups$new()`](#method-DataSpaceGroups-initialize)

- [`DataSpaceGroups$print()`](#method-DataSpaceGroups-print)

- [`DataSpaceGroups$refresh()`](#method-DataSpaceGroups-refresh)

- [`DataSpaceGroups$clone()`](#method-DataSpaceGroups-clone)

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

### `DataSpaceGroups$new()`

Initialize \`DataSpaceGroups\` class. See
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md).

#### Usage

    DataSpaceGroups$new(groupIds = NULL)

#### Arguments

- `groupIds`:

  A character vecotor of \`group_id\` values. as URL, path and username.

------------------------------------------------------------------------

### `DataSpaceGroups$print()`

Print `DataSpaceStudy` class.

#### Usage

    DataSpaceGroups$print()

------------------------------------------------------------------------

### `DataSpaceGroups$refresh()`

Refresh loaded integrated datasets, and information of what datasets are
available.

#### Usage

    DataSpaceGroups$refresh()

------------------------------------------------------------------------

### `DataSpaceGroups$clone()`

The objects of this class are cloneable with this method.

#### Usage

    DataSpaceGroups$clone(deep = FALSE)

#### Arguments

- `deep`:

  Whether to make a deep clone.

## Examples

``` r
if (FALSE) { # \dontrun{
# Create a connection (Initiate a DataSpaceConnection object)
con <- connectDS()

# Get group by `group_id` or pass a filtered `availableGroups` object.
groups <- con$getGroups(c(266, 267))
groups <- con$availableGroups[label == "NYVAC durability comparison"] |>
  con$getGroups()

# Retrieving group assay data for cvd408 from
# DataSpace is done automatically when the groups object is created.
groups$datasets$BAMA

# Get variable information of the assay dataset
groups$datasetDescription$BAMA

} # }
```
