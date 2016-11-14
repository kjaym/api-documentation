## Description

A PifSearchHit object contains information about a single PIF record that was matched.

## Fields

Field name | Value type | Description
-----------|------------|------------
id | String | ID of the record on Citrination.
dataset | Integer | Dataset to which the record belongs.
datasetVersion | Integer | Version of the dataset to which the record belongs.
system | PIF [System](http://citrineinformatics.github.io/pif-documentation/schema_definition/system/System.html) | The PIF object that was matched.
extracted | Map of strings to strings | Key value map of values that were extracted. See the extractAs field on [FieldOperation](!api/search/pif/query/core/FieldOperation) and [ChemicalFieldOperation](!api/search/pif/query/chemical/ChemicalFieldOperation).
