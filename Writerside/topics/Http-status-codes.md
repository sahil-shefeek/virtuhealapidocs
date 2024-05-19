# HTTP Status Codes in Virtuheal APIs

## Introduction

HTTP status codes are a key part of the web's protocol for communication between clients and servers. They indicate the result of a client's request and help the client understand what happened with their request.

Below is a detailed overview of the HTTP status codes used in Virtuheal APIs, organized by their class types.

## HTTP Status Codes

### Informational - 1xx

Informational responses indicate that the request was received and understood, and that the client should proceed with the request or ignore it if it is already being processed.

- `HTTP_100_CONTINUE` - Continue with the request.
- `HTTP_101_SWITCHING_PROTOCOLS` - The server is switching protocols according to the request.
- `HTTP_102_PROCESSING` - The server has received and is processing the request, but no response is available yet.
- `HTTP_103_EARLY_HINTS` - Early hints to help the client start preloading resources while the server is still preparing a response.

### Successful - 2xx

This class of status code indicates that the client's request was successfully received, understood, and accepted.

- `HTTP_200_OK` - The request has succeeded.
- `HTTP_201_CREATED` - The request has been fulfilled and has resulted in a new resource being created.
- `HTTP_202_ACCEPTED` - The request has been accepted for processing, but the processing has not been completed.
- `HTTP_203_NON_AUTHORITATIVE_INFORMATION` - The request has been successfully processed, but is returning information that may be from another source.
- `HTTP_204_NO_CONTENT` - The server has successfully fulfilled the request and there is no additional content to send.
- `HTTP_205_RESET_CONTENT` - The server has fulfilled the request and the client should reset the document view.
- `HTTP_206_PARTIAL_CONTENT` - The server is delivering only part of the resource due to a range header sent by the client.
- `HTTP_207_MULTI_STATUS` - Provides status for multiple independent operations.
- `HTTP_208_ALREADY_REPORTED` - The members of a DAV binding have already been enumerated in a previous reply to this request.
- `HTTP_226_IM_USED` - The server has fulfilled a request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.

### Redirection - 3xx

This class of status code indicates that further action needs to be taken by the user agent in order to fulfill the request.

- `HTTP_300_MULTIPLE_CHOICES` - There are multiple options for the resource that the client may follow.
- `HTTP_301_MOVED_PERMANENTLY` - The requested resource has been assigned a new permanent URI.
- `HTTP_302_FOUND` - The requested resource resides temporarily under a different URI.
- `HTTP_303_SEE_OTHER` - The response to the request can be found under another URI using a GET method.
- `HTTP_304_NOT_MODIFIED` - The resource has not been modified since the version specified by the request headers.
- `HTTP_305_USE_PROXY` - The requested resource must be accessed through the proxy given by the Location field.
- `HTTP_306_RESERVED` - No longer used. Originally meant "Switch Proxy".
- `HTTP_307_TEMPORARY_REDIRECT` - The request should be repeated with another URI, but future requests should still use the original URI.
- `HTTP_308_PERMANENT_REDIRECT` - The request and all future requests should be repeated using another URI.

### Client Error - 4xx

The 4xx class of status code is intended for cases in which the client seems to have made an error.

- `HTTP_400_BAD_REQUEST` - The server could not understand the request due to invalid syntax.
- `HTTP_401_UNAUTHORIZED` - The client must authenticate itself to get the requested response.
- `HTTP_402_PAYMENT_REQUIRED` - This status code is reserved for future use.
- `HTTP_403_FORBIDDEN` - The client does not have access rights to the content.
- `HTTP_404_NOT_FOUND` - The server can not find the requested resource.
- `HTTP_405_METHOD_NOT_ALLOWED` - The request method is known by the server but is not supported by the target resource.
- `HTTP_406_NOT_ACCEPTABLE` - The server cannot produce a response matching the list of acceptable values defined in the request's proactive content negotiation headers.
- `HTTP_407_PROXY_AUTHENTICATION_REQUIRED` - The client must first authenticate itself with the proxy.
- `HTTP_408_REQUEST_TIMEOUT` - The server would like to shut down this unused connection.
- `HTTP_409_CONFLICT` - The request could not be completed due to a conflict with the current state of the resource.
- `HTTP_410_GONE` - The requested resource is no longer available and will not be available again.
- `HTTP_411_LENGTH_REQUIRED` - The request did not specify the length of its content, which is required by the requested resource.
- `HTTP_412_PRECONDITION_FAILED` - The server does not meet one of the preconditions that the requester put on the request.
- `HTTP_413_REQUEST_ENTITY_TOO_LARGE` - The request is larger than the server is willing or able to process.
- `HTTP_414_REQUEST_URI_TOO_LONG` - The URI requested by the client is longer than the server is willing to interpret.
- `HTTP_415_UNSUPPORTED_MEDIA_TYPE` - The media format of the requested data is not supported by the server.
- `HTTP_416_REQUESTED_RANGE_NOT_SATISFIABLE` - The range specified by the Range header field in the request cannot be fulfilled.
- `HTTP_417_EXPECTATION_FAILED` - The expectation given in the request's Expect header field could not be met by the server.
- `HTTP_421_MISDIRECTED_REQUEST` - The request was directed at a server that is not able to produce a response.
- `HTTP_422_UNPROCESSABLE_ENTITY` - The request was well-formed but was unable to be followed due to semantic errors.
- `HTTP_423_LOCKED` - The resource that is being accessed is locked.
- `HTTP_424_FAILED_DEPENDENCY` - The request failed due to failure of a previous request.
- `HTTP_425_TOO_EARLY` - Indicates that the server is unwilling to risk processing a request that might be replayed.
- `HTTP_426_UPGRADE_REQUIRED` - The client should switch to a different protocol.
- `HTTP_428_PRECONDITION_REQUIRED` - The origin server requires the request to be conditional.
- `HTTP_429_TOO_MANY_REQUESTS` - The user has sent too many requests in a given amount of time ("rate limiting").
- `HTTP_431_REQUEST_HEADER_FIELDS_TOO_LARGE` - The server is unwilling to process the request because its header fields are too large.
- `HTTP_451_UNAVAILABLE_FOR_LEGAL_REASONS` - The user requests an illegal resource, such as a web page censored by a government.

### Server Error - 5xx

Response status codes beginning with the digit "5" indicate cases in which the server is aware that it has erred or is incapable of performing the request.

- `HTTP_500_INTERNAL_SERVER_ERROR` - The server has encountered a situation it doesn't know how to handle.
- `HTTP_501_NOT_IMPLEMENTED` - The request method is not supported by the server and cannot be handled.
- `HTTP_502_BAD_GATEWAY` - The server, while acting as a gateway or proxy, received an invalid response from the upstream server.
- `HTTP_503_SERVICE_UNAVAILABLE` - The server is not ready to handle the request.
- `HTTP_504_GATEWAY_TIMEOUT` - The server, while acting as a gateway or proxy, did not get a response in time from the upstream server.
- `HTTP_505_HTTP_VERSION_NOT_SUPPORTED` - The HTTP version used in the request is not supported by the server.
- `HTTP_506_VARIANT_ALSO_NEGOTIATES` - The server has an internal configuration error.
- `HTTP_507_INSUFFICIENT_STORAGE` - The server is unable to store the representation needed to complete the request.
- `HTTP_508_LOOP_DETECTED` - The server detected an infinite loop while processing a request with "Depth: infinity".
- `HTTP_509_BANDWIDTH_LIMIT_EXCEEDED` - The server has exceeded the bandwidth specified by the server administrator.
- `HTTP_510_NOT_EXTENDED` - Further extensions to the request are required for the server to fulfill it.
- `HTTP_511_NETWORK_AUTHENTICATION_REQUIRED` - The client needs to authenticate to gain network access.
