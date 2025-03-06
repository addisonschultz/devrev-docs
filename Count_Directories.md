# Count Directories

```http
GET https://api.devrev.ai/directories.count
```

Get count of directories matching given filter.



## Query Parameters

- CreatedBy (optional): Filters for directories created by any of the provided users.

- ModifiedBy (optional): Filters for directories modified by any of the provided users.


## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/directories.count \
     -H "Authorization: Bearer <token>"
```