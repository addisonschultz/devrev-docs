# Rate Limits

To ensure a consistent experience for all users, DevRev applies rate limits to its APIs. This helps prevent unintentionally proactive clients from impacting others’ accessibility.

Rate limits are applied in aggregate to all requests made by an authenticated user. If a user exceeds their rate limit, they're throttled from further processing until their rate limit *window* elapses. At present, this window resets every five minutes.

If a request is made when the user’s rate limit has been exceeded, the following response is received:

```
HTTP/1.1 429 Too Many Requests
Retry-After: 30
```

The `Retry-After` response header can be used to determine the number of seconds left before the user’s rate limit window expires.

The user’s current rate limit quota and usage can be inspected in a request’s response headers:

| Header                | Description                                                                     |
| :-------------------- | :------------------------------------------------------------------------------ |
| X-Ratelimit-Limit     | The user’s total rate limit units for the current window.                       |
| X-Ratelimit-Remaining | The user’s remaining rate limit units for the current window.                   |
| X-Ratelimit-Reset     | The time at which the rate limit window resets, in seconds from the Unix epoch. |

The following provides an example of response header values:

```
X-Ratelimit-Limit: 1000
X-Ratelimit-Remaining: 900
X-Ratelimit-Reset: 1720636800
```

<Callout intent="info">
  All APIs have the same weight when applying rate limiting, and there is no preference given to any individual API. However, this is subject to change in the future.
</Callout>