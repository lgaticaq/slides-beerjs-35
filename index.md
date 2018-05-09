title: Beerjs #35
author:
  name: Leonardo Gatica
  twitter: lgaticaq
  url: https://about.me/lgatica
  email: lgatica@protonmail.com
output: index.html
theme: juanbrujo/cleaver-beerjs
style: style.css
controls: true

--

# GraphQL en producción

--

# Primero ¿Es necesario GraphQL?

Si tu **app/servicio/lo-que-sea** funciona, no hagas nada `next()`.

Si estas comenzando un proyecto nuevo o te gusta vivir al limite _vo dale_.

--

# Entonces ¿Por donde comienzo?

Lo más fácil para entender como funciona, antes de iniciar tu propio servicio con GraphQL, es usar [graph.cool](https://www.graph.cool/).

graph.cool es de las cosas más mágicas que podrás encontrar relacionada a GraphQL.

--

![graphcool-1.png](img/graphcool-1.png)

--

![graphcool-2.png](img/graphcool-2.png)

--

![graphcool-3.png](img/graphcool-3.png)

--

![graphcool-4.png](img/graphcool-4.png)

--

![graphcool-5.png](img/graphcool-5.png)

--

# Usa Graphiql/playground/o-similar

Usar estas herramientas ayuda a construir `querys` y `mutations` a prueba de errores con el extra de ver la documentación.

--

# ¿querys? mutations? WTF :wat:

`query` es a `curl -X GET /users` como `mutation` es a `curl -X DELETE /users/1`

--

# ¿`schema`, `resolvers`, `args`?

```graphql
schema {
  query: Query,
  mutation: Mutation
}
```

```graphql
type Query {
  posts: [Post]
  author(id: Int!): Author
}

type Mutation {
  upvotePost (
    postId: Int!
  ): Post
}
```

--

```graphql
type Author {
  id: Int!
  firstName: String
  lastName: String
  posts: [Post]
}

type Post {
  id: Int!
  title: String
  author: Author
  votes: Int
}
```
