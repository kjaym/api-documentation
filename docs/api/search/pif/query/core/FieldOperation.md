## Description

A FieldOperation object describes a set of manipulations on a field in the PIF. 

## Fields

Field name | Value type | Default | Description
-----------|------------|---------|------------
`filter` | Array of [`Filter`](api/search/pif/query/core/Filter) objects |  | Conditions under which to match the field.  Any can match. |
`extract_as` | String | None | Name to use as the key in the `extracted` key-value map.  If None, do not extract. |

