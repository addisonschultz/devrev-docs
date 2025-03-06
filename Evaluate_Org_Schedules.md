# Evaluate Org Schedules

```http
GET https://api.devrev.ai/org-schedules.evaluate
```

Evaluates an organization's schedule at specified instants.



## Query Parameters

- Id (required): Organization schedule ID.
- Instants (required): Time instants to evaluate the organization schedule for.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/org-schedules.evaluate \
     -H "Authorization: Bearer <token>" \
     -d id=id \
     -d "instants[]"=instants \
     -d "instants[]"=instants
```