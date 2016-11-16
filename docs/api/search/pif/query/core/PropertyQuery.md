## Description

A PropertyQuery object contains information about a desired property.

## Fields

Field name | Value type | Default | Description
-----------|------------|---------|------------
`name` | [`FieldOperation`](api/search/pif/query/core/FieldOperation) |  | Acceptable names of the property as a field operation |
`value` | [`FieldOperation`](api/search/pif/query/core/FieldOperation) |  | Acceptable values of the property as a field operation |

`logic`    | `{"MUST", "SHOULD", "MUST_NOT"}` | `"SHOULD"` | Match type.  If multiple property objects have `"SHOULD"` logic, at least one such property must match for the system to match.

