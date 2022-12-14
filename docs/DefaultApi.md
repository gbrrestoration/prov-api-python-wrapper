# rrap_mds_is_prov_api.DefaultApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**root**](DefaultApi.md#root) | **GET** / | Root


# **root**
> bool, date, datetime, dict, float, int, list, str, none_type root()

Root

Function Description --------------------  Demonstration unauthenticated endpoint.   Returns ------- Json     Basic message response    See Also (optional) --------  Examples (optional) --------

### Example


```python
import time
import rrap_mds_is_prov_api
from rrap_mds_is_prov_api.api import default_api
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = rrap_mds_is_prov_api.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with rrap_mds_is_prov_api.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # Root
        api_response = api_instance.root()
        pprint(api_response)
    except rrap_mds_is_prov_api.ApiException as e:
        print("Exception when calling DefaultApi->root: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

**bool, date, datetime, dict, float, int, list, str, none_type**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

