# Cartesi Typescript React SQLite

The project is a React application built with Create React App and utilizes TypeScript for type safety. It is managed using npm as the package manager. The goal of the project is to create a template that streamlines the process of kickstarting new projects. The template incorporates the latest version of React and integrates with Ethers, allowing for seamless interaction with the underlying blockchain. For testing purposes, a pre-deployed demo on the Sepolia Network is available for users to explore before starting their own development.

## Bootstraping

### Frontend

For development frontend app you have 2 installation options:

1. Cloning the frontend repository

```sh
git clone https://github.com/doiim/cartesi-ts-react-sqlite
```

2. Use create-react-app template

```sh
npx create-react-app my-app --template cartesi-ts-sqlite
```

Obs.: Additional information on how to configure and run the app could be found at their own README.md files.

### Backend

For the backend at the moment we only have the option to clone the backend repo, a Sunodo template would be available soon:

```sh
git clone https://github.com/doiim/cartesi-ts-sqlite
```

Obs.: Additional information on how to configure, run and deploy backend to testnets could be found at their own README.md files.

## How this project is structure

![Cartesi project structure](https://github.com/doiim/cartesi-react-bootstrap/assets/13040410/2ab19829-997b-4964-82ca-b038f3fe2dd2)

### Frontend [(github)](https://github.com/doiim/cartesi-ts-react-sqlite)

A `Create React App` template that runs a `Typescript` supported app with `CSS Modules`. This app uses `Apollo Client` to update `Notices` from backend services and normal requests to call `Inspect` endpoint for fetch current state of the database. To call `Advance` inputs, the app uses `Ethers V5` to communicate with Backend EVM.

#### How does CreateProducForm works

![Cartesi Create Product Sequence](https://github.com/doiim/cartesi-react-sqlite-boilerplate/assets/13040410/c47fe872-d2ea-417f-8cf9-1ab82ee12ee3)

1. **User** send a Input(Advance) transaction to add a new product to the database.
2. Once transaction is confirmed by the **EVM**, user receive back the confirmation.
3. The **Cartesi Machine** than grab the Input from the **EVM** and send to the **Validator** backend service.
4. **Validator** process the Input(Advance) adding the data to the database.
5. **Validator** then sends a Notice to the **Cartesi Machine** with the confirming the Payload.
6. That Notice is then Cached on the **GraphQL** service that runs on **Validator** machine.

#### How does ListNotices works

![Cartesi List Notices Sequence](https://github.com/doiim/cartesi-react-sqlite-boilerplate/assets/13040410/6a134172-ab9c-4c04-9cc1-8f3f352d96ad)

1. Once **Frontend** is started it creates a Apollo Client service to listen for the **GraphQL service** running on the **Validator** machine.
2. Every time that a new Notice appears on **GraphQL service** it is added to the list on front-end and reported back to the **User**.

#### How does ListProducts works

![Cartesi List Products Sequence](https://github.com/doiim/cartesi-react-sqlite-boilerplate/assets/13040410/89d7c1a1-a90c-410d-a561-302da05f5e67)

1. Once **Frontend** is started it creates a Apollo Client service to listen for the **GraphQL service** running on the **Validator** machine.
2. Every time that a new Notice appears on **GraphQL service** it is added to the list.
3. Then **Frontend** then make a Inspect call to grab the current status of database from **Validator** service.
4. Once data is returned, it automatically updated the Products table.

### Backend [(github)](https://github.com/doiim/cartesi-ts-sqlite)

A `Sunodo` template machine that runs a `Typescript` node service along with `viem` to convert values from/to Hex strings. We could have switched to `Ethers` but the idea was to reduce the amount to code, and the `Sunodo` template used already have support to `viem`. The database runs `SQLite` with WASM support due to the nature of the Risc-V Node has no native support to `SQLite` bindings.

This will run an [anvil](https://book.getfoundry.sh/reference/anvil/) node as a local blockchain, and the GraphQL service and Inspect Service.

The Database consists in a simple SQLite database with a table called PRODUCTS, each product has an ID and a NAME. IDs are unique so in case user tries to register PRODUCT with same ID the backend will reject the attempt.

### Appendices

**Front-end integration package**

- https://github.com/prototyp3-dev/cartesi-client

**Back-end deployment tool**

- https://docs.sunodo.io/
- https://www.npmjs.com/package/@cartesi/rollups

**Cartesi Examples**

- https://github.com/cartesi/rollups-examples/tree/main

**Backend Typescript Framework**

- https://github.com/tuler/deroll
