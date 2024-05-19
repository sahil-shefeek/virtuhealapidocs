# Care Home Managers

## Datatypes
<api-schema openapi-path="./carehome_managers.yaml" name="CarehomeManager"/>

## Endpoints

### Base Url : hostname/api/
> It is recommended that the Base Url is provided as a global constant, as it may change periodically. This can cause unwanted code refactorings if hardcoded.
<api-doc openapi-path="./carehome_managers.yaml">
<api-endpoint endpoint="/carehomes/managers/" method="GET">
<description>Retrieve a list of care home managers.</description>
<response type="200">
<sample lang="json" title="Response">
[
  {
    "id": "cdd5d9cf-11f4-4033-9f53-350b84cb83c9",
    "manager": "manager1@example.com",
    "carehome": "a6cf4a77-2655-4b7f-abc5-63d803024365"
  },
  {
    "id": "e5e4e3c2-b1a8-4b52-bca1-f12f867de042",
    "manager": "manager2@example.com",
    "carehome": "a6cf4a77-2655-4b7f-abc5-63d803024365"
  }
]
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/carehomes/managers/" method="POST">
<description>Add a manager to a care home.</description>
<request>
<sample lang="json" title="Request Body">
{
  "manager": "manager3@example.com",
  "carehome": "a6cf4a77-2655-4b7f-abc5-63d803024365"
}
</sample>
</request>
<response type="201">
<sample lang="json" title="Response">
{
  "id": "f3b5ae13-9e27-42e1-8153-f33235b79db7",
  "manager": "manager3@example.com",
  "carehome": "a6cf4a77-2655-4b7f-abc5-63d803024365"
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/carehomes/managers/by-carehome/" method="GET">
<description>Retrieve managers for a specific care home.</description>
<request>
<sample lang="json" title="Query Parameters">
{
  "carehome": "a6cf4a77-2655-4b7f-abc5-63d803024365"
}
</sample>
</request>
<response type="200">
<sample lang="json" title="Response">
[
  {
    "id": "cdd5d9cf-11f4-4033-9f53-350b84cb83c9",
    "manager": "manager1@example.com",
    "carehome": "a6cf4a77-2655-4b7f-abc5-63d803024365"
  },
  {
    "id": "e5e4e3c2-b1a8-4b52-bca1-f12f867de042",
    "manager": "manager2@example.com",
    "carehome": "a6cf4a77-2655-4b7f-abc5-63d803024365"
  }
]
</sample>
</response>
</api-endpoint>
</api-doc>