## Development Environment Setup
- Install [Chocolatey](https://chocolatey.org/docs/installation){target=_blank}
- Download and Install [Node.js](https://chocolatey.org/packages/nodejs.install){target=_blank} v11.0.0
- Download and Install [Yarn](https://chocolatey.org/packages/yarn){target=_blank}
- Download and Install [Windows build tools](https://chocolatey.org/packages/microsoft-visual-cpp-build-tools){target=_blank}
- Download and Install [Make](https://chocolatey.org/packages/make){target=_blank}
- Download [MySQL Server](https://chocolatey.org/packages/mysql){target=_blank}

## Dev Environment
### Server setup:

```bash
- git clone https://github.com/SaucecodeOfficial/tistro.git
- cd tistro
- yarn install
- yarn boot
```

### Start the server:

```bash
- cd apps/tistro/server
- yarn start
```

### Start the web app

```bash
- cd apps/tistro/web
- yarn start
```

### View on localhost
[`http://localhost:5000`](http://localhost:5000){target=_blank}

### Cargo

Build and package all the things by running `yarn cargo`.

### Deploy

To prepare for deployment, after cargo run `yarn deploy`.

This will copy the web build, server package and configs into the "deploy" folder.

### Adding dependencies

#### Web

- yarn run dep <packageName> --scope=app-tistro-web

#### Server

- yarn run dep <packageName> --scope=app-tistro-server

### Before your app can work, you need to go through a  few steps  first:
- Create a database in the MySQL Workbench
- In the app/server/config/default.json, you need to add the credentials that you used when creating the database.

```bash
- "mysql": "mysql://<USERNAME>:<PASSWORD>@localhost:3306/<DATABASENAME>",
- "mssql": {
-  * "database": "test",
-  * "username": "sa",
-  * "password": "test"
- }
```

- After creating the Database and setting your connection string, you can just start the server and Sequelize will handle creating the tables, configuring relationships, creating indexes and seeding it for you.


