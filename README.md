# rrap-mds-is-prov-api
No description provided (generated by Openapi Generator https://github.com/openapitools/openapi-generator)

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 0.1.0
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >=3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
import rrap_mds_is_prov_api
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import rrap_mds_is_prov_api
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import rrap_mds_is_prov_api
from pprint import pprint
from rrap_mds_is_prov_api.api import access_check_api
from rrap_mds_is_prov_api.model.user import User
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
    api_instance = access_check_api.AccessCheckApi(api_client)

    try:
        # Check Admin Access
        api_response = api_instance.check_admin_access_check_access_check_admin_access_get()
        pprint(api_response)
    except rrap_mds_is_prov_api.ApiException as e:
        print("Exception when calling AccessCheckApi->check_admin_access_check_access_check_admin_access_get: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccessCheckApi* | [**check_admin_access_check_access_check_admin_access_get**](docs/AccessCheckApi.md#check_admin_access_check_access_check_admin_access_get) | **GET** /check-access/check-admin-access | Check Admin Access
*AccessCheckApi* | [**check_general_access_check_access_check_general_access_get**](docs/AccessCheckApi.md#check_general_access_check_access_check_general_access_get) | **GET** /check-access/check-general-access | Check General Access
*AccessCheckApi* | [**check_read_access_check_access_check_read_access_get**](docs/AccessCheckApi.md#check_read_access_check_access_check_read_access_get) | **GET** /check-access/check-read-access | Check Read Access
*AccessCheckApi* | [**check_write_access_check_access_check_write_access_get**](docs/AccessCheckApi.md#check_write_access_check_access_check_write_access_get) | **GET** /check-access/check-write-access | Check Write Access
*ExploreLineageApi* | [**explore_downstream_explore_downstream_get**](docs/ExploreLineageApi.md#explore_downstream_explore_downstream_get) | **GET** /explore/downstream | Explore Downstream
*ExploreLineageApi* | [**explore_upstream_explore_upstream_get**](docs/ExploreLineageApi.md#explore_upstream_explore_upstream_get) | **GET** /explore/upstream | Explore Upstream
*ModelRunsApi* | [**register_model_run_complete_model_run_register_complete_post**](docs/ModelRunsApi.md#register_model_run_complete_model_run_register_complete_post) | **POST** /model_run/register_complete | Register Model Run Complete
*DefaultApi* | [**root_get**](docs/DefaultApi.md#root_get) | **GET** / | Root


## Documentation For Models

 - [AssociationInfo](docs/AssociationInfo.md)
 - [DataStoreDatasetResource](docs/DataStoreDatasetResource.md)
 - [Dataset](docs/Dataset.md)
 - [DatasetType](docs/DatasetType.md)
 - [FileSystemResource](docs/FileSystemResource.md)
 - [HTTPValidationError](docs/HTTPValidationError.md)
 - [InputInfo](docs/InputInfo.md)
 - [LineageResponse](docs/LineageResponse.md)
 - [LocationInner](docs/LocationInner.md)
 - [ModelRunRecord](docs/ModelRunRecord.md)
 - [ModelRunWorkflowDefinitionResource](docs/ModelRunWorkflowDefinitionResource.md)
 - [ModellerResource](docs/ModellerResource.md)
 - [OrganisationResource](docs/OrganisationResource.md)
 - [OutputInfo](docs/OutputInfo.md)
 - [ProvenanceRecordInfo](docs/ProvenanceRecordInfo.md)
 - [RegisterModelRunResponse](docs/RegisterModelRunResponse.md)
 - [Status](docs/Status.md)
 - [TemplateResource](docs/TemplateResource.md)
 - [TemplatedDataset](docs/TemplatedDataset.md)
 - [URLDatasetResource](docs/URLDatasetResource.md)
 - [User](docs/User.md)
 - [ValidationError](docs/ValidationError.md)


## Documentation For Authorization


## OAuth2PasswordBearer

- **Type**: OAuth
- **Flow**: password
- **Authorization URL**: 
- **Scopes**: N/A


## Author




## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in rrap_mds_is_prov_api.apis and rrap_mds_is_prov_api.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from rrap_mds_is_prov_api.api.default_api import DefaultApi`
- `from rrap_mds_is_prov_api.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import rrap_mds_is_prov_api
from rrap_mds_is_prov_api.apis import *
from rrap_mds_is_prov_api.models import *
```
