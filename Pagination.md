# Pagination

A lot of the time, when you're making calls to the DevRev API, there'll be a lot of results to return. For that reason, we paginate the results to make sure responses are easier to handle.
DevRev API uses a cursor-based pagination to provide consistency and support large data.
Let's say your initial call is asking to list all the users in an org; the result could be a massive response with hundreds of thousands of pages. That's not a good place to start.

When you make an API call, it returns a cursor with a random code. If there are more pages available, the response will include a field called `next_cursor` which points to the next page.

<CodeBlock title="Response">
  ```json
  {
    "next_cursor": "ufhe492s",
    /* ... Rest of the payload ... */
  }
  ```
</CodeBlock>

If there are no more pages to paginate, the response will not include the `next_cursor` field.

To advance to the next page, include the cursor parameter in your query like this:

<CodeBlock title="Query">
  ```json
  .../internal/works.list?cursor="u4hf9fd"
  ```
</CodeBlock>