A client is used to maintain a connection to the Citrination platform.

Java client to connect to www.citrination.com

    CitrinationClient client = new CitrinationClient.builder()
        .setApiKey("YOUR_API_KEY")
        .build();

Java client to connect to PROJECT.citrination.com

    CitrinationClient client = new CitrinationClient.builder()
        .setProject("PROJECT")
        .setApiKey("YOUR_API_KEY")
        .build();

Python client to connect to www.citrination.com

    client = CitrinationClient('YOU_API_KEY')

Python client to connect to PROJECT.citrination.com

    client = CitrinationClient('YOUR_API_KEY', 'https://PROJECT.citrination.com')
