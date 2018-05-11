Python 3 SDK
=============
The Python SDK is a client class for our V2 API. It allows you to do GET, POST, 
PUT, PATCH and DELETE requests to our API by simply specifying the path to the 
and a (dictionary) parameter to represent the (JSON) data you want to send. 

Basic Usage
-----------

As a simple example to get those assets having the label 'Funny dogs', try
these steps on the console:

1. Go the folder where this file resides

  ```
  $ cd python-v3-sdk
  ```
  
2. Invoke the Python interpreter

  ```
  $ python3
  ```

3. Load the API module

  ```python
  >>> from api import OoyalaAPI
  ```

4. Create an OoyalaAPI object by passing your V2 API keys:

  ```python
  >>> api = OoyalaAPI("<Your API Key>", "<Your Secret Key>")
  ```
  
5. Get all assets having the "Funny dogs" label:

 ```python
  >>> parameters = {'where': "labels INCLUDES 'Funny dogs'"}
  >>> assets = api.get('assets', parameters)['items']
  ```
  
6. Now that we have our results on the assets array, lets print them embed codes and names

  ```python
  >>> for asset in assets:
        print ("%s - %s" % (asset['embed_code'], asset['name']))
  ```

You can do much more that just querying for assets, type

  ```python
  >>> help(OoyalaAPI)
  ```
  
to get a complete documentation. Its that easy to work with this SDK!