---
alias: uo6uv0ecoh
path: /docs/reference/relay-api/relation-queries
layout: REFERENCE
shorttitle: Relation Queries
description: For every available relation in your GraphQL schema, certain queries are automatically generated.
simple_relay_twin: aihaeph5ip
tags:
  - relay-api
  - queries
  - relations
related:
  further:
  more:
---

# Relation Queries in the Relay API

Every available [relation](!alias-goh5uthoc1) in your [GraphQL schema](!alias-ahwoh2fohj) adds a new field to the [type queries](!alias-uquae2shae) of the two connected types.

For example, with the following schema:

```graphql
type Post {
  id: ID!
  title: String!
  author: User @relation(name: "UserOnPost")
}

type User {
  id: ID!
  name : String!
  posts: [Post!]! @relation(name: "UserOnPost")
}
```

the following fields will be available:

* the `Post` and `allPosts` queries expose a new `author` field to [traverse one node](!alias-thu4siay9a).
* the `User` and `allUsers` queries expose a new `posts` field to [traverse many nodes](!alias-zixaephoh8). The `edges` field can be used to fetch [relation aggregation data](!alias-fe1ahseek6).
