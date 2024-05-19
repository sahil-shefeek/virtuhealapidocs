# Feedbacks

## Table of Contents

- [Introduction](#introduction)
- [Datatypes](#datatypes)
- [Feedback Endpoints](#endpoints)


## Introduction

This documentation provides details about the available endpoints in our Virtuheal API for managing
feedbacks.

## Datatypes
<api-schema openapi-path="./feedbacks.yaml" name="Feedback"/>

## Endpoints

### Base Url : hostname/api/
> It is recommended that the Base Url is provided as a global constant, as it may change periodically. This can cause unwanted code refactorings if hardcoded.
<api-doc openapi-path="./feedbacks.yaml">
<api-endpoint endpoint="/feedbacks/" method="GET">
<description>Retrieve a list of feedbacks. The returned list is filtered based on the user's role.</description>
<response type="200">
<sample lang="json" title="Response">
[
  {
    "id": "123e4567-e89b-12d3-a456-426614174000",
    "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
    "created_at": "2023-05-18T10:00:00Z",
    "session_date": "2023-05-17",
    "session_duration": 60,
    "vr_experience": "It was a very engaging VR session.",
    "engagement_level": 5,
    "satisfaction": 4,
    "physical_impact": 3,
    "cognitive_impact": 4,
    "emotional_response": "The associate was very happy after the session.",
    "feedback_notes": "No additional notes."
  },
  ...
]
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/feedbacks/" method="POST">
<description>Create a new feedback entry. Only users with appropriate permissions can create feedback.</description>
<request>
<sample lang="json" title="Request">
{
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "session_date": "2023-05-17",
  "session_duration": 60,
  "vr_experience": "It was a very engaging VR session.",
  "engagement_level": 5,
  "satisfaction": 4,
  "physical_impact": 3,
  "cognitive_impact": 4,
  "emotional_response": "The associate was very happy after the session.",
  "feedback_notes": "No additional notes."
}
</sample>
</request>
<response type="201">
<sample lang="json" title="Response">
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "created_at": "2023-05-18T10:00:00Z",
  "session_date": "2023-05-17",
  "session_duration": 60,
  "vr_experience": "It was a very engaging VR session.",
  "engagement_level": 5,
  "satisfaction": 4,
  "physical_impact": 3,
  "cognitive_impact": 4,
  "emotional_response": "The associate was very happy after the session.",
  "feedback_notes": "No additional notes."
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/feedbacks/{id}/" method="GET">
<description>Retrieve details of a specific feedback entry.</description>
<response type="200">
<sample lang="json" title="Response">
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "created_at": "2023-05-18T10:00:00Z",
  "session_date": "2023-05-17",
  "session_duration": 60,
  "vr_experience": "It was a very engaging VR session.",
  "engagement_level": 5,
  "satisfaction": 4,
  "physical_impact": 3,
  "cognitive_impact": 4,
  "emotional_response": "The associate was very happy after the session.",
  "feedback_notes": "No additional notes."
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/feedbacks/{id}/" method="PUT">
<description>Update details of a specific feedback entry.</description>
<request>
<sample lang="json" title="Request">
{
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "session_date": "2023-05-17",
  "session_duration": 60,
  "vr_experience": "It was a very engaging VR session.",
  "engagement_level": 5,
  "satisfaction": 4,
  "physical_impact": 3,
  "cognitive_impact": 4,
  "emotional_response": "The associate was very happy after the session.",
  "feedback_notes": "No additional notes."
}
</sample>
</request>
<response type="200">
<sample lang="json" title="Response">
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "associate": "http://example.com/api/associates/123e4567-e89b-12d3-a456-426614174000/",
  "created_at": "2023-05-18T10:00:00Z",
  "session_date": "2023-05-17",
  "session_duration": 60,
  "vr_experience": "It was a very engaging VR session.",
  "engagement_level": 5,
  "satisfaction": 4,
  "physical_impact": 3,
  "cognitive_impact": 4,
  "emotional_response": "The associate was very happy after the session.",
  "feedback_notes": "No additional notes."
}
</sample>
</response>
</api-endpoint>

<api-endpoint endpoint="/feedbacks/{id}/" method="DELETE">
<description>Delete a specific feedback entry.</description>
<response type="204">
<sample lang="json" title="Response"></sample>
</response>
</api-endpoint>
</api-doc>

