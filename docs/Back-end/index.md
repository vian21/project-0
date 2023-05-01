# Back-end

## REST vs GraphQL VS tRPC

-> chose `REST`

### Why not GraphQL?

- Perfomance: GraphQL is slower than REST due to the fact that it needs to parse the query before sending the response.

### Why not tRPC?

- trpc is a very promising technology with numerous benefits such as complete type safety on both the frontend and backend
- but its downside is that is only compatible with typescript and to some extent JS
- It offers less flexibility and interoperability than REST and GraphQL
- Working with Rest would allow us to integrate other programming languages with easy since it will be hitting a Rest endpoint
