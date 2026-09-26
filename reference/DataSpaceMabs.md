# The DataSpaceMab class

An R6 class for DataSpace MAb data.

## Constructor

`DataSpaceConnection$getMab()`

## See also

[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md)
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)

## Super class

[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)
-\> `DataSpaceMabs`

## Active bindings

- `mabMetadata`:

  A data.table of mAbs with metadata found in the object.

- `donorMetadata`:

  A data.table of donors with metadata found in the object.

- `mabMixMetadata`:

  A data.table. A table of mAb mixtures with metadata found in this
  DataSpaceMab instance.

- `mabMix`:

  A data.table. A mapping table of mab_mix_id to mab_id. with metadata
  found in this DataSpaceMab instance.

- `datasets`:

  A list of data.table objects containing the mab related that were
  loaded.

- `variableDefinitions`:

  A data.table of variable definitions.

## Methods

### Public methods

- [`DataSpaceMabs$new()`](#method-DataSpaceMabs-initialize)

- [`DataSpaceMabs$print()`](#method-DataSpaceMabs-print)

- [`DataSpaceMabs$loadDaash()`](#method-DataSpaceMabs-loadDaash)

- [`DataSpaceMabs$refresh()`](#method-DataSpaceMabs-refresh)

- [`DataSpaceMabs$clone()`](#method-DataSpaceMabs-clone)

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

### `DataSpaceMabs$new()`

Initialize `DataSpaceMab` object. See
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md).

#### Usage

    DataSpaceMabs$new(mabIds, includeMixtures)

#### Arguments

- `mabIds`:

  A character vector of \`mab_id\` values.

- `includeMixtures`:

  Whether or not to include mab mixtures. "yes", "no", or "only" are
  valid.

------------------------------------------------------------------------

### `DataSpaceMabs$print()`

Print the `DataSpaceMab` object summary.

#### Usage

    DataSpaceMabs$print()

------------------------------------------------------------------------

### `DataSpaceMabs$loadDaash()`

Load any available DAASH datasets.

#### Usage

    DataSpaceMabs$loadDaash()

------------------------------------------------------------------------

### `DataSpaceMabs$refresh()`

Refresh the `DataSpaceMab` object to update datasets.

#### Usage

    DataSpaceMabs$refresh()

------------------------------------------------------------------------

### `DataSpaceMabs$clone()`

The objects of this class are cloneable with this method.

#### Usage

    DataSpaceMabs$clone(deep = FALSE)

#### Arguments

- `deep`:

  Whether to make a deep clone.

## Examples

``` r
if (FALSE) { # \dontrun{
# Create a connection (Initiate a DataSpaceConnection object)
con <- connectDS()

# Inspect available mabs, then pass subset to the `getMabs` method.
vrc01 <- con$availableMabs[mab_name_std == "VRC01"] |>
  con$getMabs()

# Inspect the `NABMAb` assay data.
vrc01$datasets$NABMAb

# Load DAASH data from mab object
vrc01$loadDaash()

# Inspect DAASH datasets
vrc01$datasets$daash |> names()

} # }
```
