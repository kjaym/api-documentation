A client is used to maintain a connection to the Citrination platform.

Connect to www.citrination.com

```Java
CitrinationClient client = new CitrinationClient.builder()
    .setApiKey("YOUR_API_KEY")
    .build();
```

```python
client = CitrinationClient('YOU_API_KEY')
```

Connect to PROJECT.citrination.com

```Java
CitrinationClient client = new CitrinationClient.builder()
    .setProject("PROJECT")
    .setApiKey("YOUR_API_KEY")
    .build();
```

```python
client = CitrinationClient('YOUR_API_KEY', 'https://PROJECT.citrination.com')
```
