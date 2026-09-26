# The DataSpaceDAASH class

An R6 class for DataSpace DAASH data.

## Constructor

`DataSpaceConnection$getDaash()`

## See also

[`connectDS`](https://docs.ropensci.org/DataSpaceR/reference/connectDS.md)
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)

## Super class

[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md)
-\> `DataSpaceDaash`

## Active bindings

- `mabMetadata`:

  A data.table of mAbs with metadata found in the object.

- `donorMetadata`:

  A data.table of donors with metadata found in the object.

- `daashMetadata`:

  A data.table showing the donor and mAb metadata with CDS sequence_id
  values for the loaded DAASH dataset.

- `availableStructures`:

  A data.table showing the mAb structures available to download.

- `datasets`:

  A list of DAASH datastets loaded to the DAASH object.

- `variableDefinitions`:

  A data.table of variable definitions.

## Methods

### Public methods

- [`DataSpaceDaash$new()`](#method-DataSpaceDaash-initialize)

- [`DataSpaceDaash$print()`](#method-DataSpaceDaash-print)

- [`DataSpaceDaash$getFastaFromSequences()`](#method-DataSpaceDaash-getFastaFromSequences)

- [`DataSpaceDaash$downloadAntibodyStructures()`](#method-DataSpaceDaash-downloadAntibodyStructures)

- [`DataSpaceDaash$refresh()`](#method-DataSpaceDaash-refresh)

- [`DataSpaceDaash$clone()`](#method-DataSpaceDaash-clone)

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

### `DataSpaceDaash$new()`

Initialize `DataSpaceMabMetadata` object. See
[`DataSpaceConnection`](https://docs.ropensci.org/DataSpaceR/reference/DataSpaceConnection.md).

#### Usage

    DataSpaceDaash$new(availableDaash)

#### Arguments

- `availableDaash`:

  availableDaash an \`availableMabs\`, or \`availableDonors\` object, or
  a vector of \`sequnce_id\` values.

- `config`:

  A list.

------------------------------------------------------------------------

### `DataSpaceDaash$print()`

Print the `DataSpaceMab` object summary.

#### Usage

    DataSpaceDaash$print()

------------------------------------------------------------------------

### `DataSpaceDaash$getFastaFromSequences()`

Return a fasta file for available daash sequences that have been loaded
to the current object.

#### Usage

    DataSpaceDaash$getFastaFromSequences(
      sequenceType = "nt",
      originalHeaders = FALSE,
      path = NULL
    )

#### Arguments

- `sequenceType`:

  character the type of fasta file to return: nt = nucleotide, aa =
  amino acid.

- `originalHeaders`:

  boolean if the original fasta headers should be provided

- `path`:

  The path where to save the fasta files to. If using the default value,
  NULL, then a fasta file is returned as a character vector.

------------------------------------------------------------------------

### `DataSpaceDaash$downloadAntibodyStructures()`

Saves all antibody structures associated with the daash object's
\`availableStuctures\` object.

#### Usage

    DataSpaceDaash$downloadAntibodyStructures(path = tempdir(), mab_id = NULL)

#### Arguments

- `path`:

  The directory to export fasta files to.

- `mab_id`:

  A subset of mab_ids to export. If using the default, NULL, all
  structures in availableStuctures are downloaded.

------------------------------------------------------------------------

### `DataSpaceDaash$refresh()`

Refresh the `DataSpaceMabMetadata` object to update datasets.

#### Usage

    DataSpaceDaash$refresh()

------------------------------------------------------------------------

### `DataSpaceDaash$clone()`

The objects of this class are cloneable with this method.

#### Usage

    DataSpaceDaash$clone(deep = FALSE)

#### Arguments

- `deep`:

  Whether to make a deep clone.

## Examples

``` r
if (FALSE) { # \dontrun{
# Create a connection (Initiate a DataSpaceConnection object)
con <- connectDS()

# Get the daash object using either an availableMabs or
# availableDonors object.
daash <- con$availableMabs[mab_ab_binding_type %like% "CD4"] |>
  con$getDaash()

# To get lineage sequences, query donors, then pipe available
# donors to the connection getDaash object.
daash <- con$availableDonors[
  lineage_sequences_available == TRUE & mab_count < 10,
  ] |>
  con$getDaash()

# Inspect what datasets are available
names(daash$datasets)

# Inspect the `topCalls` dataset
daash$datasets$topCalls

} # }
```
