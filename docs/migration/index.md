Users of the previous clients that were available for Citrination can use this guide to convert their searches to the newer API syntax.

## Update client libraries

Updates to the python client library are available at https://github.com/CitrineInformatics/python-citrination-client or using pip with `pip install citrination-client`.

## Making connections to Citrination using the Python client

See the [Client](!api/client/Client) page.

## Search queries

The previous python client used the following fields to define a search:

* `term` - General search string. _This has been deprecated in the new API._
* `formula` - Chemical formula to search for.
* `property` - Name of the property to search for.
* `contributor` - Name of the contributor of the data. _This has been deprecated in the new API._
* `reference` - Filter against the reference field. _This field has been broken into multiple parts. The example below shows how to use the DOI filter. See [`ReferenceQuery`](!api/search/pif/query/core/ReferenceQuery) for more options._
* `min_measurement` - Minimum value to allow for the property.
* `max_measurement` - Maximum value to allow for the property.
* `from_record` - Index of the first record to return.
* `per_page` - Number of results to return.
* `data_set_id` - ID of the dataset to search on.

These fields map to a the new [`PifQuery`](!api/search/pif/query/PifQuery) object in the following way. Any fields that are not defined can be omitted.

```Python
from citrination-client import *
query = PifQuery(
    from_index=`from_record`,
    size=`per_page`,
    system=SystemQuery(
        chemical_formula=ChemicalFieldOperation(
            filter=ChemicalFilter(equal=`formula`)
        ),
        properties=PropertyQuery(
            name=FieldOperation(
                filter=Filter(equal=`property`)
            ),
            value=FieldOperation(
                filter=Filter(
                    min=`min_measurement`,
                    max=`max_measurement`
                )
            )
        ),
        references=ReferenceQuery(
            doi=FieldOperation(
                filter=Filter(equal=`reference`)
            )
        )
    ),
    include_datasets=[`data_set_id`]
)
```

With this query, the following command can be used to execute against the Citrination site. See [`PifSearchResult`](!api/search/pif/result/PifSearchResult) for the format of the results.

```Python
from citrination-client import *
client = CitrinationClient('YOU_API_KEY')
pifSearchResult = client.search(query)
```
