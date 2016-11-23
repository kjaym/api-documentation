This guide walks through the steps needed to install the python Citrination client and execute a query against the Citrination site. See the [api](!api) documentation for a complete description of the methods that are available.

### Client installation

The python client can be install with [pip](https://pypi.python.org/pypi/pip) using:

`pip install citrination-client`

The library can also be accessed directly on [github](https://github.com/CitrineInformatics/python-citrination-client). After downloading that repository, run the following command to install:

`python setup.py install`

### Connecting to Citrination

In order to access Citrination using the client library, you will need your API key. You individual key is available on your account page. This key is unique to you; do not share it with anyone.

With your API key, a client is configured to run against https://citrination.com with the following code block:

```Python
from citrination-client import *
client = CitrinationClient('YOUR_API_KEY')
```

For users with private deployments (the site that you are accessing appears as https://PROJECT-NAME.citrination.com), the client should be configured against your site:

```Python
from citrination-client import *
client = CitrinationClient('YOUR_API_KEY', 'https://PROJECT-NAME.citrination.com')
```

### Executing a query

Citrination uses a robust [query language](!api/search/pif/query) to interact with the data that is stored. The following example simply runs a search that looks for records with chemical formula equal to GaN and with a band gap between 3 and 4 eV:

```Python
from citrination-client import *
client = CitrinationClient('YOUR_API_KEY')

query = PifQuery(
    from_index=0,
    size=10,
    system=SystemQuery(
        chemical_formula=ChemicalFieldOperation(
            filter=ChemicalFilter(equal='GaN')
        ),
        properties=PropertyQuery(
            name=FieldOperation(
                filter=Filter(equal='Band gap')
            ),
            value=FieldOperation(
                filter=Filter(
                    min=3,
                    max=4
                )
            ),
            units=FieldOperation(
                filter=Filter(equal='eV')
            )
        )
    )
)

results = client.search(query)
```

Results are return as a [`PifSearchResult`](!api/search/pif/result/PifSearchResult) object.

### Next steps

Users are encourage to read about the data model used on Citrination, the [PIF](http://citrine.io/pif), in order to understand how data is represented on the system.

The hierarchy of the [query language](!api/search/pif/query) exactly mirrors the hierarchy of the [PIF](http://citrine.io/pif) schema. With an understanding of this query language, users are able to query against data in Citrination in a very precise way.
