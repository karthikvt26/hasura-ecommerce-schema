# E commerce schema

A Hasura project with the schema for a simple e-commerce application.


## Files and Directories

The project (a.k.a. project directory) has a particular directory structure and it has to be maintained strictly, else `hasura` cli would not work as expected. A representative project is shown below:

```
.
├── clusters.yaml
├── conf
│   ├── authorized-keys.yaml
│   ├── auth.yaml
│   ├── ci.yaml
│   ├── domains.yaml
│   ├── filestore.yaml
│   ├── gateway.yaml
│   ├── http-directives.conf
│   ├── notify.yaml
│   ├── postgres.yaml
│   ├── README.md
│   ├── routes.yaml
│   └── session-store.yaml
├── hasura.yaml
├── microservices
│   └── README.md
├── migrations
│   ├── 1509711424_create_table_category.up.yaml
│   ├── 1509711600_create_table_product.up.yaml
│   ├── 1509711617_alter_table_product_alter_column_category_id.up.yaml
│   ├── 1509711618_alter_table_product_add_foreign_key.up.yaml
│   ├── 1509711661_create_table_product_image.up.yaml
│   ├── 1509711673_alter_table_product_image_alter_column_product_id.up.yaml
│   ├── 1509711674_alter_table_product_image_add_foreign_key.up.yaml
│   ├── 1509711685_add_relationship_category_table_product.up.yaml
│   ├── 1509711690_add_relationship_images_table_product.up.yaml
│   ├── 1509711698_add_relationship_products_table_category.up.yaml
│   ├── 1509711826_create_table_product_rating.up.yaml
│   ├── 1509711869_drop_table_product_rating.up.yaml
│   ├── 1509712048_create_table_product_rating.up.yaml
│   ├── 1509712070_drop_table_product_rating.up.yaml
│   ├── 1509712096_create_table_product_rating.up.yaml
│   ├── 1509712132_create_table_stock.up.yaml
│   ├── 1509712143_alter_table_stock_alter_column_product_id.up.yaml
│   ├── 1509712144_alter_table_stock_add_foreign_key.up.yaml
│   ├── 1509712150_add_relationship_product_table_stock.up.yaml
│   ├── 1509712157_add_relationship_stocks_table_product.up.yaml
│   ├── 1509712198_create_table_customer.up.yaml
│   ├── 1509712220_alter_table_product_rating_alter_column_customer_id.up.yaml
│   ├── 1509712221_alter_table_product_rating_add_foreign_key.up.yaml
│   ├── 1509712452_modify_permission_user_table_customer.up.yaml
│   ├── 1509712479_modify_permission_anonymous_table_product.up.yaml
│   ├── 1509712522_modify_permission_anonymous_table_product_image.up.yaml
│   ├── 1509712574_modify_permission_anonymous_table_product_rating.up.yaml
│   ├── 1509712586_modify_permission_anonymous_table_category.up.yaml
│   ├── 1509712598_add_relationship_product_ratings_table_customer.up.yaml
│   ├── 1509712629_modify_permission_user_table_customer.up.yaml
│   ├── 1509712704_modify_permission_user_table_customer.up.yaml
│   ├── 1509712732_modify_permission_user_table_customer.up.yaml
│   ├── 1509712790_modify_permission_anonymous_table_stock.up.yaml
│   ├── 1509712835_create_table_customer_wishlist.up.yaml
│   ├── 1509712854_alter_table_customer_wishlist_alter_column_customer_id.up.yaml
│   ├── 1509712856_alter_table_customer_wishlist_add_foreign_key.up.yaml
│   ├── 1509712865_alter_table_customer_wishlist_alter_column_product_id.up.yaml
│   ├── 1509712867_alter_table_customer_wishlist_add_foreign_key.up.yaml
│   ├── 1509712876_add_relationship_customer_table_customer_wishlist.up.yaml
│   ├── 1509712880_add_relationship_product_table_customer_wishlist.up.yaml
│   ├── 1509712933_create_table_customer_address.up.yaml
│   ├── 1509712948_alter_table_customer_address_alter_column_customer_id.up.yaml
│   ├── 1509712950_alter_table_customer_address_add_foreign_key.up.yaml
│   ├── 1509712957_add_relationship_customer_table_customer_address.up.yaml
│   ├── 1509712965_add_relationship_customer_addresses_table_customer.up.yaml
│   ├── 1509712973_add_relationship_wishllists_table_customer.up.yaml
│   ├── 1509714117_create_table_cart_item.up.yaml
│   ├── 1509714140_alter_table_cart_item_alter_column_customer_id.up.yaml
│   ├── 1509714142_alter_table_cart_item_add_foreign_key.up.yaml
│   ├── 1509714159_add_relationship_cart_table_customer.up.yaml
│   ├── 1509714541_create_table_payment .up.yaml
│   ├── 1509714599_create_table_order_request.up.yaml
│   ├── 1509714780_create_table_order_address.up.yaml
│   ├── 1509714936_create_table_order.up.yaml
│   ├── 1509714949_alter_table_order_alter_column_customer_id.up.yaml
│   ├── 1509714950_alter_table_order_add_foreign_key.up.yaml
│   ├── 1509714964_alter_table_order_alter_column_payment_id.up.yaml
│   ├── 1509714965_alter_table_order_add_foreign_key.up.yaml
│   ├── 1509714978_alter_table_order_alter_column_order_address_id.up.yaml
│   ├── 1509714979_alter_table_order_add_foreign_key.up.yaml
│   ├── 1509714985_add_relationship_customer_table_order.up.yaml
│   ├── 1509714991_add_relationship_order_address_table_order.up.yaml
│   ├── 1509714996_add_relationship_payment_table_order.up.yaml
│   ├── 1509715064_create_table_order_item.up.yaml
│   ├── 1509715083_alter_table_order_item_alter_column_order_detail_id.up.yaml
│   ├── 1509715085_alter_table_order_item_add_foreign_key.up.yaml
│   ├── 1509715106_alter_table_order_item_alter_column_product_id.up.yaml
│   ├── 1509715107_alter_table_order_item_add_foreign_key.up.yaml
│   ├── 1509715116_add_relationship_product_table_order_item.up.yaml
│   ├── 1509715132_add_relationship_items_table_order.up.yaml
│   ├── 1509715163_modify_permission_user_table_order.up.yaml
│   ├── 1509715219_add_relationship_order_detail_table_order_item.up.yaml
│   ├── 1509715235_modify_permission_user_table_order_item.up.yaml
│   ├── 1509715264_add_relationship_order_table_payment .up.yaml
│   ├── 1509715291_modify_permission_user_table_payment .up.yaml
│   ├── 1509715328_modify_permission_user_table_cart_item.up.yaml
│   └── README.md
└── README.md
```

### `hasura.yaml`

This file contains some metadata about the project, namely a name, description and some keywords. Also contains `platformVersion` which says which Hasura platform version is compatible with this project.

### `clusters.yaml`

Info about the clusters added to this project can be found in this file. Each cluster is defined by it's name allotted by Hasura. While adding the cluster to the project you are prompted to give an alias, which is just hasura by default. The `kubeContext` mentions the name of kubernetes context used to access the cluster, which is also managed by hasura. The `config` key denotes the location of cluster's metadata on the cluster itself. This information is parsed and cluster's metadata is appended while conf is rendered. `data` key is for holding custom variables that you can define.

```yaml
- name: h34-ambitious93-stg
  alias: hasura
  kubeContext: h34-ambitious93-stg
  config:
    configmap: controller-conf
    namespace: hasura
  data: null  
```
