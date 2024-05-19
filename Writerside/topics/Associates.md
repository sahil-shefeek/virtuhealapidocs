# Associates

## Table of Contents

- [Introduction](#introduction)
- [Datatypes](#datatypes)
- [Associate Endpoints](#endpoints)

## Introduction

This documentation provides details about the available endpoints in our Virtuheal API for managing
associates.

## Datatypes
<api-schema openapi-path="./associates.yaml" name="Associate"/>

## Endpoints

### Base Url : hostname/api/
> It is recommended that the Base Url is provided as a global constant, as it may change periodically. This can cause unwanted code refactorings if hardcoded.
<api-doc openapi-path="./associates.yaml">

<api-endpoint endpoint="/associates/" method="GET">
<description>Retrieve a list of associates. The returned list is filtered based on the user's role.</description>
<response type="200">
<sample lang="json" title="Response">
[
  {
    "id": "123e4567-e89b-12d3-a456-426614174000",
    "name": "John Doe",
    "date_of_birth": "1990-01-01",
    "care_home": "http://example.com/api/carehomes/123e4567-e89b-12d3-a456-426614174000/",
    "created_by": "http://example.com/api/users/123e4567-e89b-12d3-a456-426614174000/"
  },
  ...
]
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/associates/" method="POST">
<description>Create a new associate. Only users with appropriate permissions can create associates.</description>
<request>
<sample lang="json" title="Request">
{
  "name": "John Doe",
  "date_of_birth": "1990-01-01",
  "care_home": "http://example.com/api/carehomes/123e4567-e89b-12d3-a456-426614174000/",
  "created_by": "http://example.com/api/users/123e4567-e89b-12d3-a456-426614174000/"
}
</sample>
</request>
<response type="201">
<sample lang="json" title="Response">
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "name": "John Doe",
  "date_of_birth": "1990-01-01",
  "care_home": "http://example.com/api/carehomes/123e4567-e89b-12d3-a456-426614174000/",
  "created_by": "http://example.com/api/users/123e4567-e89b-12d3-a456-426614174000/"
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/associates/{id}/" method="GET">
<description>Retrieve details of a specific associate.</description>
<response type="200">
<sample lang="json" title="Response">
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "name": "John Doe",
  "date_of_birth": "1990-01-01",
  "care_home": "http://example.com/api/carehomes/123e4567-e89b-12d3-a456-426614174000/",
  "created_by": "http://example.com/api/users/123e4567-e89b-12d3-a456-426614174000/"
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/associates/{id}/" method="PUT">
<description>Update details of a specific associate.</description>
<request>
<sample lang="json" title="Request">
{
  "name": "John Doe",
  "date_of_birth": "1990-01-01",
  "care_home": "http://example.com/api/carehomes/123e4567-e89b-12d3-a456-426614174000/",
  "created_by": "http://example.com/api/users/123e4567-e89b-12d3-a456-426614174000/"
}
</sample>
</request>
<response type="200">
<sample lang="json" title="Response">
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "name": "John Doe",
  "date_of_birth": "1990-01-01",
  "care_home": "http://example.com/api/carehomes/123e4567-e89b-12d3-a456-426614174000/",
  "created_by": "http://example.com/api/users/123e4567-e89b-12d3-a456-426614174000/"
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/associates/{id}/" method="DELETE">
<description>Delete a specific associate.</description>
<response type="204">
<sample lang="json" title="Response"></sample>
</response>
</api-endpoint>
</api-doc>
