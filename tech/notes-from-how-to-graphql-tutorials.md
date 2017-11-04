# Notes from How to GraphQL Tutorials
> Sat, 4 Nov 2017 at 1:25:05 MYT

###1. Introduction

- apollo vs relay
    - apollo: framework agnostic, community driven
    - relay: initially made as routing framework. built by facebook, for react & react native. higher entry barrier compared to apollo
- apollo features: optimistic caching, subscription support, etc
- Graphcool: Flexible ***backend*** platform combining GraphQL + Serverless

###2. Fundamentals

- GraphQL != REST
- GrapqhQL types: `query` & `mutation`
    - query type: represents all entry points
    - mutation type: represents all updates we can make to our data
- "if you've to adjust the api everytime you changed your design on the front end, you won't be able to iterate quickly on the product"
- GraphQl: single endpoint for all data
- example of GraphQL `query` type:

    ```
    query {
        User(id: "er3453sdfsd") {
            name
            posts {
                title
            }
            followers(last: 3) {
                name
            }
        }
    }
    ```
- `data` is the root field of GraphQL response, as defined in GraphQL specification
- GraphQL advantages over REST:
    - no more overfetching (downloading unecessary data)
    - no more underfetching: the need to send multiple requests because single endpoint does not return enough information (n+1 problem)
    - enables rapid product iteration: changes on the client side can be made without any extra work on the server
    - fine-grained info about what data is read by clients
    - strong type system: enables frontend & backend team to work completely independent from each other
- GraphQL uses ***resolver*** functions to fetch data that's being requested by the clients

### 3. Core Concepts

- Schema Definition Language (SDL): syntax for writing graphql schemas. example:
    
    ```
    type Person {
        name: String!
        age: Int!
        posts: [Post!]!
    }
    
    // express relationship between types
    type Post {
        title: String!
        author: Person!
    }
    ``` 
    > Read more about GraphQL SDL here: [http://graphql.org/learn/schema/](http://graphql.org/learn/schema/)
- one of major benefit in using GraphQL: ability to do nested query easily
- the general 3 kind of mutation in GraphQL:
    1. create (new data)
    2. update (existing data)
    3. delete (existing data)
- in GraphQL, one can query information when sending mutation
- GraphQL supports real-time updates using via its "subscriptions" feature, which represent stream of data sent over to the clients
- example of subscription type:
    
    ```
    subscription {
        newPerson {
            name
            age
        }
    }
    
    // type definition
    type Subscription {
        newPerson: Person!
    }
    ```

**3. The Big Picture (Architecture)**

- "GraphQL has been released only as a specification. This means that GraphQL is in fact not more than a long document that describes in detail the behaviour of a GraphQL server."
- Note that GraphQL is actually *transport-layer* agnostic: it is potentially possible to implement a GraphQL server based on TCP, WebSockets, etc.
- Each field in the query corresponds to a resolver function. The GraphQL calls all required resolvers when a query comes in to fetch the specified data, packed it up once all resolvers finished its jobs, and sent it to the client
- GraphQL vs REST == declarative vs imperative
