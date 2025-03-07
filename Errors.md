# Errors

DevRev’s APIs use standard HTTP status codes when responding to requests. On success, a `20X` status code is returned along with any response data, as indicated in the OpenAPI specification.

| Status Code | Status       | Description                                                                               |
| ----------- | ------------ | ----------------------------------------------------------------------------------------- |
| `200`       | `OK`         | The request succeeded and the result is contained in the response.                        |
| `201`       | `Created`    | The request successfully created an object and the result is contained in the response.   |
| `204`       | `No Content` | The request succeeded and contains no response data. This is common for object deletions. |

A request may encounter a set of errors that are common across all the APIs. In the response, a JSON object with a `message` field is provided that contains supplemental information to the encountered error.

```
HTTP/1.1 404 Not Found
Content-Type: application/json
Content-Length: 29
{"message":"route not found"}
```

| Status Code | Status                  | Description                                                                                                                                                                                                                                                                |
| ----------- | ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `400`       | `Bad Request`           | The request was malformed or contained invalid arguments.                                                                                                                                                                                                                  |
| `401`       | `Unauthorized`          | The user attempted to access an endpoint that requires authentication and no credentials were provided or their validation failed.                                                                                                                                         |
| `403`       | `Forbidden`             | The user isn't authorized to perform the requested action.                                                                                                                                                                                                                 |
| `404`       | `Not Found`             | The requested endpoint doesn’t exist.                                                                                                                                                                                                                                      |
| `429`       | `Too Many Requests`     | The user is currently throttled due to exceeding their permitted rate limit. The `Retry-After` response header contains the number of seconds before the user should retry.                                                                                                |
| `500`       | `Internal Server Error` | An internal error was encountered in the handling of the request which couldn’t be processed to completion. DevRev is automatically alerted to any occurrence of this error. The user should retry after a short delay and contact DevRev support if the problem persists. |
| `503`       | `Service Unavailable`   | A transient error was encountered and the user should retry after a short delay.                                                                                                                                                                                           |

An endpoint may be annotated with additional status codes in the OpenAPI specification to denote special behavior.

| Status Code | Status              | Description                                                                                                               |
| ----------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `301`       | `Moved Permanently` | The target resource’s ID has changed, where the `Location` response header contains the updated ID.                       |
| `404`       | `Not Found`         | The target object or requested resource doesn’t exist.                                                                    |
| `409`       | `Conflict`          | The attempted object creation conflicted with an existing object, for example, a group with the same name already exists. |