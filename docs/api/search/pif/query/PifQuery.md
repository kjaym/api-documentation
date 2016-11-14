## Description

A PifQuery object contains all information for a single query.

## Fields

Field name | Value type | Default | Description
-----------|------------|---------|------------
`from` | Integer | 0 | Index of the first hit that should be returned. Used for pagination.
`size` | Integer | 100 | Total number of hits that should be returned.  Used for pagination. Maximum value of 100.
`returnSystem` | Boolean | True | True to return the PIF objects that matched. False omits the PIF objects and returns only their IDs.
`addLatex` | Boolean | False | True to inject Latex formatting into the results where possible. This only applies to a small subset of the fields in the results.
`scoreRelevance` | Boolean | False | True to turn on relevancy so that the _best_ matches appear first.
`system` | Array of [`SystemQuery`](!api/search/pif/query/core/SystemQuery) objects | | List of queries to execute at the System level.
`includeDatasets` | Array of integers | | Filter on a subset of datasets by their unique ID.
`excludeDatasets` | Array of integers | | Filter out a subset of datasets by their unique ID.
