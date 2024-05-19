# Care Homes

## Table of Contents
- [Introduction](#introduction)
- [Datatypes](#datatypes)
- [Care Home Endpoints](#endpoints)
- <b><a href="Care-Home-Managers.md">Care Home Manager endpoints</a></b>

## Introduction

This documentation provides details about the available endpoints for managing care homes in our Virtuheal API.

## Datatypes
<api-schema openapi-path="./carehome.yaml" name="CareHome"/>

## Endpoints

### Base Url : hostname/api/
> It is recommended that the Base Url is provided as a global constant, as it may change periodically. This can cause unwanted code refactorings if hardcoded.
<api-doc openapi-path="./carehome.yaml" generate-samples="all">
<api-endpoint endpoint="/carehomes/" method="GET">
<description>Retrieve a list of care homes.</description>
<response type="200">
<sample lang="json" title="Response">
[
  {
    "id": "a6cf4a77-2655-4b7f-abc5-63d803024365",
    "name": "Sunrise Care Home",
    "code": "SUN123",
    "admin": "john@example.com",
    "address": "123 Sunrise Lane",
    "created_at": "2024-05-18T12:00:00Z",
    "updated_at": "2024-05-18T12:00:00Z",
    "homes_count": 5
  },
  {
    "id": "d4b31d64-9de4-46e4-89d8-87b17ae7b5fa",
    "name": "Moonlight Care Facility",
    "code": "MOON456",
    "admin": "jane@example.com",
    "address": "456 Moonlight Road",
    "created_at": "2024-05-18T12:00:00Z",
    "updated_at": "2024-05-18T12:00:00Z",
    "homes_count": 3
  }
]
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/carehomes/" method="POST">
<description>Create a new care home.</description>
<request>
<sample lang="json" title="Request Body">
{
  "name": "Sunset Care Home",
  "code": "SUNSET789",
  "admin": "admin@example.com",
  "address": "789 Sunset Blvd"
}
</sample>
</request>
<response type="201">
<sample lang="json" title="Response">
{
  "id": "4aef1b21-d9cb-4e14-9c5d-25bdcfcfc879",
  "name": "Sunset Care Home",
  "code": "SUNSET789",
  "admin": "admin@example.com",
  "address": "789 Sunset Blvd",
  "created_at": "2024-05-18T12:00:00Z",
  "updated_at": "2024-05-18T12:00:00Z",
  "homes_count": 1
}
</sample>
</response>
</api-endpoint>
</api-doc>
