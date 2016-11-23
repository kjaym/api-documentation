## Description

A PropertyQuery object contains information about a desired property.

## Fields

Field name | Value type | Default | Description
-----------|------------|---------|------------
`name` | [`FieldOperation`](api/search/pif/query/core/FieldOperation) |  | A bag for anything to execute against the name field |
`value` | [`FieldOperation`](api/search/pif/query/core/FieldOperation) |  | A bag for anything to execute against the value field |

`logic`    | `{"MUST", "SHOULD", "MUST_NOT"}` | `"SHOULD"` | Match type.  If multiple property objects have `"SHOULD"` logic, at least one such property must match for the system to match.

