# Переход client-app на Graphql

## Scheme

````
type Query {
    client(id: ID!): Client
    documents(id: ID!): [Document]
    relatives(id: ID!): [Relative]
}

type Client {
    id: ID!
    name: String
    age: Int
    documents: [Document]
    relatives: [Relative]
}

type Document {
    id: ID!
    type: String
    number: String
    issueDate: String
    expiryDate: String
}

type Relative {
    id: ID!
    relationType: String
    name: String
    age: Int
}
````

## Queries

```json
// аналог GET /clients/{id}
query {
  client(id: "{id}") {
    id
    name
    age
  }
}

// аналог GET /clients/{id}/documents
query {
  documents(id: "{id}") {
    id
    type
    number
    issueDate
    expiryDate
  }
}

// аналог GET /clients/{id}/relatives
query {
  relatives(id: "{id}") {
    id
    relationType
    name
    age
  }
}

```

