# graphql-api-portfolio

A minimal GraphQL server built with Express and Apollo Server, exposing a single `hello` query.

**Status:** Stub. The only source file is `server.js`, which defines one query that returns a fixed string. Mongoose is listed as a dependency, but nothing in the code uses it.

## The problem

The code shows a starting point for a GraphQL API: an Express app with an Apollo Server mounted on it, ready for types and resolvers to be added. The repo name suggests a portfolio, but the code contains no portfolio data or content.

## What it does

- Starts an Express app with an Apollo GraphQL server mounted at `/graphql`.
- Serves a schema with one query, `hello: String`, which returns `"Hello world!"`.
- Listens on port 4000 and logs the GraphQL endpoint URL when it starts.

## How it's built

- Node.js with CommonJS modules, Express 4, `apollo-server-express` 3 and `graphql` 16.
- The schema is written with the `gql` tag and passed to `new ApolloServer` together with its resolvers.
- `server.js` wraps startup in an async function. It awaits `server.start()` before calling `applyMiddleware`, which is the order Apollo Server 3 expects when it is attached to an existing Express app.

## Running it locally

```
npm install     # or: pnpm install
npm start       # node server.js
npm run dev     # nodemon server.js
```

Open `http://localhost:4000/graphql` to reach the endpoint.

`npm test` is the default placeholder and exits with an error. There are no tests.

## What's left

- The schema has one query and no mutations or other types.
- Mongoose is listed in `package.json`, but there is no database connection or model.
- There are no tests. The `test` script is the npm placeholder.
- No portfolio content or data source is present, despite the repo name.
- The port is fixed at 4000 in `server.js`.
- `pnpm-workspace.yaml` still contains an unfilled placeholder for the `@apollo/protobufjs` build setting.
