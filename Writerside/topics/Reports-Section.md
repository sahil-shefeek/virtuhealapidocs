# Reports

## Table of Contents

- [Introduction](#introduction)
- [Datatype](#datatypes)
- [Endpoints](#endpoints)

## Introduction

This documentation provides details about the available endpoints in our Virtuheal API for managing reports.


## Datatypes
<api-schema openapi-path="./reports.yaml" name="Report"/>

## Endpoints

### Base Url : hostname/api/
> It is recommended that the Base Url is provided as a global constant, as it may change periodically. This can cause unwanted code refactorings if hardcoded.
<api-doc openapi-path="./reports.yaml">
<api-endpoint endpoint="/reports/" method="GET">
<description>Retrieve a list of reports. The returned list is filtered based on the user's role.</description>
<response type="200">
<sample lang="json" title="Response">
[
  {
    "id": "123e4567-e89b-12d3-a456-426614174000",
    "report_month": "2023-04-01",
    "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
    "description": "Monthly report for April",
    "pdf": "http://example.com/uploads/reports/report_april.pdf"
  },
  ...
]
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/reports/" method="POST">
<description>Create a new report entry. Only users with appropriate permissions can create reports.</description>
<request>
<sample lang="json" title="Request">
{
  "report_month": "2023-04-01",
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "description": "Monthly report for April",
  "pdf": "http://example.com/uploads/reports/report_april.pdf"
}
</sample>
</request>
<response type="201">
<sample lang="json" title="Response">
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "report_month": "2023-04-01",
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "description": "Monthly report for April",
  "pdf": "http://example.com/uploads/reports/report_april.pdf"
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/reports/{id}/" method="GET">
<description>Retrieve details of a specific report entry.</description>
<response type="200">
<sample lang="json" title="Response">
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "report_month": "2023-04-01",
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "description": "Monthly report for April",
  "pdf": "http://example.com/uploads/reports/report_april.pdf"
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/reports/{id}/" method="PUT">
<description>Update details of a specific report entry.</description>
<request>
<sample lang="json" title="Request">
{
  "report_month": "2023-04-01",
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "description": "Updated monthly report for April",
  "pdf": "http://example.com/uploads/reports/updated_report_april.pdf"
}
</sample>
</request>
<response type="200">
<sample lang="json" title="Response">
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "report_month": "2023-04-01",
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "description": "Updated monthly report for April",
  "pdf": "http://example.com/uploads/reports/updated_report_april.pdf"
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/reports/{id}/" method="DELETE">
<description>Delete a specific report entry.</description>
<response type="204">
<sample lang="json" title="Response"></sample>
</response>
</api-endpoint>
</api-doc>

## Models

<api-schema openapi-path="./reports.yaml" name="Report"/>