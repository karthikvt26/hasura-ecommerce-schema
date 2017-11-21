# E-commerce schema
A Hasura project with the schema for a simple e-commerce application.

## Deploy this project
Use the quickstart instructions at (hasura/ecommerce-schema)[/hub/project/hasura/ecommerce-schema].

## Browse the schema
Once you deploy this project on a cluster, head to [https://schemaspy.cluster-name.hasura-app.io/relationships.html](https://schemaspy.cluster-name.hasura-app.io/relationships.html) to see your schema.

Remember to replace cluster-name with the name of your cluster. You can get your cluster name by running: 

```shell
$ hasura cluster status
```

## Test the APIs
Run:

```shell
$ hasura api-console
```

and use the API explorer to test the instant APIs available on this schema.
