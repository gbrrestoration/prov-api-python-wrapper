# rrap_mds_is_prov_api.ModelRunsApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**register_model_run_complete_model_run_register_complete_post**](ModelRunsApi.md#register_model_run_complete_model_run_register_complete_post) | **POST** /model_run/register_complete | Register Model Run Complete


# **register_model_run_complete_model_run_register_complete_post**
> RegisterModelRunResponse register_model_run_complete_model_run_register_complete_post(model_run_record)

Register Model Run Complete

register_model_run_complete Given the model run record object (schema/model) will: - validate the ids provided in the model      - Validate and retrieve the workflow definition     - Validate the templates for the input and output datasets      - Validate that the provided datasets satisfy all templates     - Validate that datasets provided through data store exist - mint a model run record in the registry  - produce a prov-o document reflecting the input model run record - update the model run record in the registry with the prov serialisation   and other information  - lodge the model run record into the graph database store - update the record to lodged status  - return information including the handle id from the model run record  Arguments ---------- record : ModelRunRecord     The model run record to lodge into the graph store and registry  Returns -------  : RegisterModelRunResponse     The response including the handle id and record information  Raises ------ HTTPException     If something goes wrong when validating the IDs returns a 400 error.  See Also (optional) --------  Examples (optional) --------

### Example

* OAuth Authentication (OAuth2PasswordBearer):

```python
import time
import rrap_mds_is_prov_api
from rrap_mds_is_prov_api.api import model_runs_api
from rrap_mds_is_prov_api.model.http_validation_error import HTTPValidationError
from rrap_mds_is_prov_api.model.model_run_record import ModelRunRecord
from rrap_mds_is_prov_api.model.register_model_run_response import RegisterModelRunResponse
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
    api_instance = model_runs_api.ModelRunsApi(api_client)
    model_run_record = ModelRunRecord(
        workflow_definition=ModelRunWorkflowDefinitionResource(
            id="id_example",
        ),
        inputs=InputInfo(
            datasets={
                "key": TemplatedDataset(
                    template=TemplateResource(
                        id="id_example",
                    ),
                    dataset_type=DatasetType("DATA_STORE"),
                    dataset=Dataset(None),
                ),
            },
        ),
        outputs=OutputInfo(
            datasets={
                "key": TemplatedDataset(
                    template=TemplateResource(
                        id="id_example",
                    ),
                    dataset_type=DatasetType("DATA_STORE"),
                    dataset=Dataset(None),
                ),
            },
        ),
        associations=AssociationInfo(
            modeller=ModellerResource(
                id="id_example",
            ),
            requesting_organisation=OrganisationResource(
                id="id_example",
            ),
        ),
        start_time=1,
        end_time=1,
    ) # ModelRunRecord | 

    # example passing only required values which don't have defaults set
    try:
        # Register Model Run Complete
        api_response = api_instance.register_model_run_complete_model_run_register_complete_post(model_run_record)
        pprint(api_response)
    except rrap_mds_is_prov_api.ApiException as e:
        print("Exception when calling ModelRunsApi->register_model_run_complete_model_run_register_complete_post: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **model_run_record** | [**ModelRunRecord**](ModelRunRecord.md)|  |

### Return type

[**RegisterModelRunResponse**](RegisterModelRunResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

