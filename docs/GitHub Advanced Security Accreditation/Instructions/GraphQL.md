### set up a GraphQL Explorer
1. Get a properly configured OAuth token.
2. Open GraphiQL.
3. In the upper-right corner of GraphiQL, select Edit HTTP Headers.
4. In the Key field, enter 'Authorization'. In the Value field, enter Bearer <token>, where <token> is your generated OAuth token.
5. Select the checkmark to the right of the token to save it.
6. To return to the editor, select outside of the Edit HTTP Headers modal.
7. In the GraphQL Endpoint field, enter https://api.github.com/graphql.
8. In the Method dropdown, select Post.