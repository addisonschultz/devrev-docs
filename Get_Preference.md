# Get Preference

```http
GET https://api.devrev.ai/preferences.get
```

Get the preferences object.



## Query Parameters

- Object (required): The ID of the target object for which preferences object is to be
fetched.

- Type (required): Type of the preference object to be fetched.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/preferences.get \
     -H "Authorization: Bearer <token>" \
     -d object=object \
     -d type=user_preferences
```