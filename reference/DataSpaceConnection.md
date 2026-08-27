# The DataSpaceConnection class

An R6 class for DataSpace browsing and fetching data in DataSpace.

## Constructor

[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md)

## See also

[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md)
[`DataSpaceR-package`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceR-package.md)

## Active bindings

- `config`:

  A list. Stores configuration of the connection object such as URL,
  path and username.

- `availableStudies`:

  A data.tabl of available studies.

- `availableGroups`:

  A data.table of available groups.

- `availableMabs`:

  A data.table of available mAbs.

- `availableMabMixtures`:

  A data.table. Metadata of available mAb mixtures.

- `availableDonors`:

  A data.table. Metadata about all mAb donors in the DataSpace.

- `availableViruses`:

  A data.table of metadata about all virsues in the DataSpace and virus
  name synonyms.

- `availablePublications`:

  A data.table of available publications metadata and available
  datasets.

- `lanlMabMetadata`:

  A data.table of mAb metadata from LANL of mAbs found in the object

- `virusNameMappingTables`:

  A list of data.tables containing virus name mappings.

- `mabGridSummary`:

  Defunct. Use \`availableMabs\`.

- `mabGrid`:

  Defunct. Use \`availableMabs\`.

- `virusMetadata`:

  Defunct. Use \`virusNameMappingTables\`.

## Methods

### Public methods

- [`DataSpaceConnection$new()`](#method-DataSpaceConnection-initialize)

- [`DataSpaceConnection$print()`](#method-DataSpaceConnection-print)

- [`DataSpaceConnection$getStudies()`](#method-DataSpaceConnection-getStudies)

- [`DataSpaceConnection$getGroups()`](#method-DataSpaceConnection-getGroups)

- [`DataSpaceConnection$getMabs()`](#method-DataSpaceConnection-getMabs)

- [`DataSpaceConnection$getDonors()`](#method-DataSpaceConnection-getDonors)

- [`DataSpaceConnection$getDaash()`](#method-DataSpaceConnection-getDaash)

- [`DataSpaceConnection$downloadPublicationData()`](#method-DataSpaceConnection-downloadPublicationData)

- [`DataSpaceConnection$loadLanlMabMetadata()`](#method-DataSpaceConnection-loadLanlMabMetadata)

- [`DataSpaceConnection$getStudy()`](#method-DataSpaceConnection-getStudy)

- [`DataSpaceConnection$getGroup()`](#method-DataSpaceConnection-getGroup)

- [`DataSpaceConnection$getMab()`](#method-DataSpaceConnection-getMab)

- [`DataSpaceConnection$filterMabGrid()`](#method-DataSpaceConnection-filterMabGrid)

- [`DataSpaceConnection$resetMabGrid()`](#method-DataSpaceConnection-resetMabGrid)

- [`DataSpaceConnection$refresh()`](#method-DataSpaceConnection-refresh)

- [`DataSpaceConnection$clone()`](#method-DataSpaceConnection-clone)

------------------------------------------------------------------------

### `DataSpaceConnection$new()`

Initialize a `DataSpaceConnection` object. See
[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md).

#### Usage

    DataSpaceConnection$new(
      login = NULL,
      password = NULL,
      verbose = FALSE,
      onStaging = FALSE
    )

#### Arguments

- `login`:

  A character. Optional argument. If there is no netrc file a temporary
  one can be written by passing login and password of an active
  DataSpace account.

- `password`:

  A character. Optional. The password for the selected login.

- `verbose`:

  A logical. Whether to print the extra details for troubleshooting.

- `onStaging`:

  A logical. Whether to connect to the staging server instead of the
  production server.

#### Returns

A new \`DataSpaceConnection\` object.

------------------------------------------------------------------------

### `DataSpaceConnection$print()`

Print the `DataSpaceConnection` object.

#### Usage

    DataSpaceConnection$print()

------------------------------------------------------------------------

### `DataSpaceConnection$getStudies()`

Create a \`DataSpaceStudies\` object.

#### Usage

    DataSpaceConnection$getStudies(availableStudies = self$availableStudies)

#### Arguments

- `availableStudies`:

  an \`availableStudies\` object, or a vector of \`study_id\` values.

------------------------------------------------------------------------

### `DataSpaceConnection$getGroups()`

Create a \`DataSpaceGroups\` object.

#### Usage

    DataSpaceConnection$getGroups(availableGroups = self$availableGroups)

#### Arguments

- `availableGroups`:

  an \`availableGroups\` object, or a vector of \`group id\` values.

------------------------------------------------------------------------

### `DataSpaceConnection$getMabs()`

Create a \`DataSpaceMabs\` object.

#### Usage

    DataSpaceConnection$getMabs(
      availableMabs = self$availableMabs,
      includeMixtures = "yes"
    )

#### Arguments

- `availableMabs`:

  an \`availableMabs\` or \`availableMabMixtures\` object, or a vector
  of \`mab id\` values. \`mab_id\` values are inferred from
  \`availableMabMixtures\` objects.

- `includeMixtures`:

  Whether or not to include mab mixtures. "yes", "no", or "only" are
  valid. The default, "yes", will return any available mAb mixtures for
  any mAb passed here.

------------------------------------------------------------------------

### `DataSpaceConnection$getDonors()`

Create a \`DataSpaceDonors\` object.

#### Usage

    DataSpaceConnection$getDonors(availableDonors = self$availableDonors)

#### Arguments

- `availableDonors`:

  an \`availableDonors\` object, or a vector of \`donor_id\` values.

------------------------------------------------------------------------

### `DataSpaceConnection$getDaash()`

Create a \`DataSpaceDaash\` object.

#### Usage

    DataSpaceConnection$getDaash(availableDaash = NULL)

#### Arguments

- `availableDaash`:

  an \`availableMabs\`, or \`availableDonors\` object, or a vector of
  \`sequnce_id\` values.

------------------------------------------------------------------------

### `DataSpaceConnection$downloadPublicationData()`

Download study related publication datasets.

#### Usage

    DataSpaceConnection$downloadPublicationData(
      availablePublications = NULL,
      downloadDir = tempdir()
    )

#### Arguments

- `availablePublications`:

  an \`availablePublications\` object or a vector of \`publication_id\`
  values.

- `downloadDir`:

  A character. Optional, specifies directory to download nonstandard
  datasets. Default is use to the R session temp directory

------------------------------------------------------------------------

### `DataSpaceConnection$loadLanlMabMetadata()`

Load any available mAb metadata from LANL.

#### Usage

    DataSpaceConnection$loadLanlMabMetadata()

------------------------------------------------------------------------

### `DataSpaceConnection$getStudy()`

Defunct. Use \`getStudies\`.

#### Usage

    DataSpaceConnection$getStudy()

------------------------------------------------------------------------

### `DataSpaceConnection$getGroup()`

Defunct. Use \`getGroups\`.

#### Usage

    DataSpaceConnection$getGroup()

------------------------------------------------------------------------

### `DataSpaceConnection$getMab()`

Defunct. Use \`getMabs\`.

#### Usage

    DataSpaceConnection$getMab()

------------------------------------------------------------------------

### `DataSpaceConnection$filterMabGrid()`

Defunct. Use \`availableMabs\`.

#### Usage

    DataSpaceConnection$filterMabGrid()

------------------------------------------------------------------------

### `DataSpaceConnection$resetMabGrid()`

Defunct. Use \`availableMabs\`.

#### Usage

    DataSpaceConnection$resetMabGrid()

------------------------------------------------------------------------

### `DataSpaceConnection$refresh()`

Refresh the connection object to update available studies and groups.

#### Usage

    DataSpaceConnection$refresh()

------------------------------------------------------------------------

### `DataSpaceConnection$clone()`

The objects of this class are cloneable with this method.

#### Usage

    DataSpaceConnection$clone(deep = FALSE)

#### Arguments

- `deep`:

  Whether to make a deep clone.

## Examples

``` r
if (FALSE) { # \dontrun{
# Create a connection (Initiate a DataSpaceConnection object)
con <- connectDS()

# View available data

con$availableStudies
con$availableGroups
con$availablePublications
con$availableMabs
con$availableMabMixtures
con$availableDonors
con$availableViruses

# Pass an available object to a "get" method to get data

cvd408 <- con$availableStudies[study_id == "cvd408"] |>
  con$getStudies()

cd4Mabs <- con$availableMabs[grepl("CD4bs", mab_ab_binding_type)] |>
  con$getMabs()

} # }
```
