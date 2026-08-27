# The DataSpaceStudies class

An R6 class for DataSpace Study data.

## Constructor

`DataSpaceConnection$getStudies()`

## See also

[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md)
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)

## Super class

[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)
-\> `DataSpaceStudies`

## Active bindings

- `studies`:

  A character vector of \`study_id\` values found in the object.

- `availableDatasets`:

  A table of datasets available in the `DataSpaceStudies` object.

- `datasets`:

  A list of data.table objects containing the availableDatasets that
  were loaded.

- `variableDefinitions`:

  A list of data.table objects containing the data dictionaries of the
  integrated data loaded.

- `treatmentArm`:

  A data.table. The table of treatment arm information for the connected
  study. Not available for all study connection.

- `studyInfo`:

  A list. Stores the information about the study.

## Methods

### Public methods

- [`DataSpaceStudies$new()`](#method-DataSpaceStudies-initialize)

- [`DataSpaceStudies$print()`](#method-DataSpaceStudies-print)

- [`DataSpaceStudies$loadAvailableDatasets()`](#method-DataSpaceStudies-loadAvailableDatasets)

- [`DataSpaceStudies$refresh()`](#method-DataSpaceStudies-refresh)

- [`DataSpaceStudies$clone()`](#method-DataSpaceStudies-clone)

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

### `DataSpaceStudies$new()`

Initialize `DataSpaceStudy` class. See
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md).

#### Usage

    DataSpaceStudies$new(studyIds)

#### Arguments

- `studyIds`:

  A character. Name of the study to retrieve. as URL, path and username.

------------------------------------------------------------------------

### `DataSpaceStudies$print()`

Print `DataSpaceStudy` class.

#### Usage

    DataSpaceStudies$print()

------------------------------------------------------------------------

### `DataSpaceStudies$loadAvailableDatasets()`

Load datasets to the studies object from an availableDatasets object.

#### Usage

    DataSpaceStudies$loadAvailableDatasets(
      availableDatasets = self$availableDatasets,
      downloadDir = tempdir()
    )

#### Arguments

- `availableDatasets`:

  An \`availableDatasets\` object or vector of \`study_id\` values.

- `downloadDir`:

  Optional, a character path specifying a directory to download.
  nonstandard datasets. The default is the working temp directory.

------------------------------------------------------------------------

### `DataSpaceStudies$refresh()`

Refresh the study object to update available datasets and treatment
info.

#### Usage

    DataSpaceStudies$refresh()

------------------------------------------------------------------------

### `DataSpaceStudies$clone()`

The objects of this class are cloneable with this method.

#### Usage

    DataSpaceStudies$clone(deep = FALSE)

#### Arguments

- `deep`:

  Whether to make a deep clone.

## Examples

``` r
if (FALSE) { # \dontrun{
# Create a connection (Initiate a DataSpaceConnection object)
con <- connectDS()

# Get group by `study_id` or pass a filtered `availableStudies` object.
studies <- con$getStudies(c("vtn505", "cvd408"))
studies <- con$getStudies(
  con$availableStudies[grepl("BAMA", data_availability) & species == "Human"]
)

# Load BAMA to the studies object.
studies$loadAssayDatasets("BAMA")
studies$datasets$BAMA

# Inspect variable information of the BAMA dataset
studies$datasetDescriptions$BAMA

# Inspect treatment arm information for all studies in study object
studies$treatmentArm

} # }
```
