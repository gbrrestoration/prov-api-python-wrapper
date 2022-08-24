# rrap_mds_is_prov_api.ExploreLineageApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**explore_downstream**](ExploreLineageApi.md#explore_downstream) | **GET** /explore/downstream | Explore Downstream
[**explore_upstream**](ExploreLineageApi.md#explore_upstream) | **GET** /explore/upstream | Explore Upstream


# **explore_downstream**
> LineageResponse explore_downstream(starting_id)

Explore Downstream

explore_downstream Explores in the downstream direction (outputs/results) starting at the specified node handle ID. The search  depth is bounded by the depth parameter which has a default maximum of 100.  Arguments ---------- starting_id : str     The handle ID to start at. depth : int, optional     The maximum depth to traverse in this direction, by default DEPTH_UPPER_LIMIT  Returns -------  : LineageResponse     A status, node count, and networkx serialised graph response.  See Also (optional) --------  Examples (optional) --------

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import time
import rrap_mds_is_prov_api
from rrap_mds_is_prov_api.api import explore_lineage_api
from rrap_mds_is_prov_api.model.http_validation_error import HTTPValidationError
from rrap_mds_is_prov_api.model.lineage_response import LineageResponse
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = rrap_mds_is_prov_api.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: OAuth2PasswordBearer
configuration = rrap_mds_is_prov_api.Configuration(
    host = "http://localhost"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with rrap_mds_is_prov_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = explore_lineage_api.ExploreLineageApi(api_client)
    starting_id = "starting_id_example" # str | 
    depth = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Explore Downstream
        api_response = api_instance.explore_downstream(starting_id)
        pprint(api_response)
    except rrap_mds_is_prov_api.ApiException as e:
        print("Exception when calling ExploreLineageApi->explore_downstream: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Explore Downstream
        api_response = api_instance.explore_downstream(starting_id, depth=depth)
        pprint(api_response)
    except rrap_mds_is_prov_api.ApiException as e:
        print("Exception when calling ExploreLineageApi->explore_downstream: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **starting_id** | **str**|  |
 **depth** | **int**|  | [optional]

### Return type

[**LineageResponse**](LineageResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **explore_upstream**
> LineageResponse explore_upstream(starting_id)

Explore Upstream

explore_upstream Explores in the upstream direction (inputs/associations) starting at the specified node handle ID. The search  depth is bounded by the depth parameter which has a default maximum of 100.  Arguments ---------- starting_id : str     The handle ID to start at. depth : int, optional     The maximum depth to traverse in this direction, by default DEPTH_UPPER_LIMIT  Returns -------  : LineageResponse     A status, node count, and networkx serialised graph response.  See Also (optional) --------  Examples (optional) --------

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import time
import rrap_mds_is_prov_api
from rrap_mds_is_prov_api.api import explore_lineage_api
from rrap_mds_is_prov_api.model.http_validation_error import HTTPValidationError
from rrap_mds_is_prov_api.model.lineage_response import LineageResponse
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = rrap_mds_is_prov_api.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: OAuth2PasswordBearer
configuration = rrap_mds_is_prov_api.Configuration(
    host = "http://localhost"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with rrap_mds_is_prov_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = explore_lineage_api.ExploreLineageApi(api_client)
    starting_id = "starting_id_example" # str | 
    depth = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Explore Upstream
        api_response = api_instance.explore_upstream(starting_id)
        pprint(api_response)
    except rrap_mds_is_prov_api.ApiException as e:
        print("Exception when calling ExploreLineageApi->explore_upstream: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Explore Upstream
        api_response = api_instance.explore_upstream(starting_id, depth=depth)
        pprint(api_response)
    except rrap_mds_is_prov_api.ApiException as e:
        print("Exception when calling ExploreLineageApi->explore_upstream: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **starting_id** | **str**|  |
 **depth** | **int**|  | [optional]

### Return type

[**LineageResponse**](LineageResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

