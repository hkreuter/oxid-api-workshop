# oxid-api-workshop

OXID GraphQl API Workshop 2021-06-25

### Example 1

As customer I want to set a short (e.g max 254 characters) 'about me' description which is stored in
an extra field in the oxuser table. Use ExtendType to extend Storefront module's Customer DataType
so that the extra field can be queried in customer query.

```graphql
type Customer
{
    // ...
    aboutMe: String!
}

type Mutation {
    CustomerAboutMe (
        aboutMe: String
    ): Customer!
}
```

### Example 2

As admin user of (groups oxidadmin, oxidadmingraph) I want to query the count of orders
created in a specified timeframe

```graphql
type AdminOrders
{
    dateFrom: DateTime
    dateTo: DateTime
    ordersCount: int!
    orders: [Order]!
}

type Query {
    adminOrders (
        dateFrom: DateTime
        dateTo: DateTime
    ):  AdminOrders!
}
```

### Example 3

As customer I want to use an autocomplete product search powered by GraphQL.


### Useful links

* Official OXID eShop VM and SDK integration - https://github.com/OXID-eSales/oxvm_eshop
* OXID eShop dev env based on docker https://github.com/OXID-eSales/docker-eshop-sdk
* OXID GraphQL interface documentation https://docs.oxid-esales.com/interfaces/graphql/en/latest/
* Base module - https://github.com/OXID-eSales/graphql-base-module
* Storefront module - https://github.com/OXID-eSales/graphql-storefront-module
* Module skeleton - https://github.com/OXID-eSales/graphql-module-skeleton