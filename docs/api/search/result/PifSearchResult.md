## Description

A PifSearchResult object contains information about the results of a query.

## Fields

Field name | Value type | Description
-----------|------------|------------
took | Integer | Number of milliseconds that the query took to execute.
totalNumHits | Integer | Total number of hits that matched the query.
hits | Array of [`PifSearchHit`](!api/search/result/PifSearchHit) objects | Records that were matched.
