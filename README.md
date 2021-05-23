[![CircleCI](https://circleci.com/gh/circleci/circleci-docs.svg?style=svg)](https://circleci.com/gh/circleci/circleci-docs)

# **cestos**
An REST API to integrate with your online store!
The api was build with:

[![Node.js Logo](/.github/images/node.js_logo.png)](https://nodejs.org/en/)

[![Sequelize Logo](/.github/images/sequelize-logo.png)](https://www.npmjs.com/package/sequelize)

[![PostgreSQL Logo](/.github/images/postgres-logo.png)](https://www.postgresql.org/)

[![Yarn Logo](/.github/images/yarn-logo.png)](https://yarnpkg.com/)

## Required

- #### Node.js - ^12.14.1
- #### Yarn - ^1.17.3
- #### PostgreSQL - 12.3

## Install dependencies

First install all required dependencies, you can do so by running:

```
yarn
```

 or

 ```
 yarn install
 ```

## Decrypt secret files

First export your secret key:

```
export KEY="<secret-key>";
```

Next decrypt both ``` test.js ```  and ``` development.js```:

```
bin/utils/decrypt config/test.enc config/test.js
```
and
```
bin/utils/decrypt config/development.enc config/development.js
```

## Setup Database

You need to create an database called:

```
cestos
```

Add a new role:

```
root
```

With password:

```
root
```

Now you can use:

```
yarn:db:all
```

to migrate and seed your database.

## Postman Collection

We have added one Postman Collection so you can test your endpoints easily.

Browse to ``` postman ``` folder, there you will find a file named: ``` cestos_colllection.json ```.

Download it and import it to Postman, here is a tutorial on how to do it:

```
1. Open Postman
2. Click Import, click Choose Files and specify cestos_colllection.json . An import success message appears for each collection imported
3. Click the Eye icon to setup an Environment
4. Click Add
5. Enter the Environment name: cestos
6. Enter a Key and a Value:
  6.1. Key: port
  6.2. Value: <port-number-you-defined> 
```

## Start your local server

Now that you have everything setup, you just need to start your localhost, for this you just need to run:

```
yarn start
```
=> This will start your localhost at port ```5000``` by default.

### Options

- #### Port

    If you want to set an other port, just pass the following argument:

    ```
    -p {port}
    ```

    It whould look something like this:

    ```
    yarn start -p 3000
    ```
    => Now the api is running on port ```3000```.

- #### Debugging

    If   you want to start debugging your server, we added the debugging option to.
    For this you only need to run:

    ```
    yarn start:debug
    ```

    When you run this command we automatically run ```yarn:db:all``` too.

Remember that you can combine those, for example:

```
yarn start:debug -p 3000
```


## Endpoints

### [Orders](/.github/readme/orders.md)

### [Users](/.github/readme/users.md)

### [Stores](/.github/readme/stores.md)


## Tests

Run

```
yarn test:local
```

So the database is reset.

## Authors

- ### [Duarte Pereira](https://github.com/DuarteNRP)
- ### [Gabriel Gomes](https://github.com/gabrieloptionq)
