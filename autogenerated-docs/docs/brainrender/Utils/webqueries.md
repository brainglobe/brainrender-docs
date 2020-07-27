



Contents
========

* [**`connected_to_internet`** [#6]](#connected_to_internet-6)
* [**`send_query`** [#22]](#send_query-22)
* [**`request`** [#40]](#request-40)


&nbsp;

--------
# **`connected_to_internet`** [#6]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/webqueries.py#L6) online

```python
def connected_to_internet(url='http://www.google.com/', timeout=5):
```

&nbsp;  
docstring:

```text
Check that there is an internet connection

:param url: url to use for testing (Default value =
    'http://www.google.com/')

:param timeout:  timeout to wait for [in seconds] (Default value = 5)

```

&nbsp;

--------
# **`send_query`** [#22]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/webqueries.py#L22) online

```python
def send_query(query_string, clean=False):
```

&nbsp;  
docstring:

```text
Send a query/request to a website

:param query_string: string with query content

:param clean:  (Default value = False)

```

&nbsp;

--------
# **`request`** [#40]
  
Check the [***``source code``***](https://github.com/BrancoLab/BrainRender/blob/master/brainrender/Utils/webqueries.py#L40) online

```python
def request(url):
```

&nbsp;  
docstring:

```text
Sends a request to a url

:param url:

```