# User Management

## Data types
<api-schema openapi-path="./user_management.yaml" name="InterfaceUser"/>

## User Endpoints

### Base Url : hostname/api/auth
> It is recommended that the Base Url is provided as a global constant, as it may change periodically. This can cause unwanted code refactorings if hardcoded.
<api-doc openapi-path="./user_management.yaml">
<api-endpoint endpoint="/user/" method="GET">
<description>Retrieve details of the authenticated user.</description>
<response type="200">
<sample lang="json" title="Response">
{
  "url": "http://example.com/api/users/1/",
  "id": 1,
  "name": "John Doe",
  "email": "john.doe@example.com",
  "is_superadmin": false,
  "is_admin": false,
  "is_manager": false
}
</sample>
</response>
</api-endpoint>
<api-endpoint endpoint="/users/" method="GET">
<description>Retrieve a list of users.</description>
<response type="200">
<sample lang="json" title="Response">
[
  {
    "url": "http://example.com/api/users/1/",
    "id": 1,
    "name": "John Doe",
    "email": "john.doe@example.com",
    "is_superadmin": false,
    "is_admin": false,
    "is_manager": false
  }
]
</sample>
</response>
</api-endpoint>
<api-endpoint endpoint="/users/" method="POST">
<description>Create a new user.</description>
<request>
<sample lang="json" title="Request Body">
{
  "name": "Jane Doe",
  "email": "jane.doe@example.com",
  "password": "password123"
}
</sample>
</request>
<response type="201">
<sample lang="json" title="Response">
{
  "url": "http://example.com/api/users/2/",
  "id": 2,
  "name": "Jane Doe",
  "email": "jane.doe@example.com"
}
</sample>
</response>
</api-endpoint>
</api-doc>