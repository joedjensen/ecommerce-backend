# Ecommerce Backed
This repository contains an ecommerce backend built using an Express API and Sequelize to interact with a MySQL database. Users are able to perform all CRUD operations on Categories, Products, and Tags. As defined in sequelize, a Category `hasMany` Products and a Product `belongsTo` a Category. A Product `belongsToMany` tags, and a tag `belongsToMany` products. The API follows REST conventioins

This repository utilizes
* JavaScript
* Node
* npm
* MySQL
* Sequelize

[Video](https://drive.google.com/file/d/1igvRYhMDQkZI4DhJKViT-1mP5wNefpmW/view)

## Installation 

Make sure you have node installed. Install dependencies
```sh
npm install
```
You will need mysql installed. Then run 
```sh
source db/schema.sql
```
from within the mysql shell at the root directory. This creates the db.

You will need to include a .env file with the db name and your username and pw, which sequelize will use to connect. We have included an example file.

In order to seed the db run
```sh
npm run seed
```

## Usage 
In order to start the server run
```sh
npm start
```
You can then test `GET`, `POST`, `PUT`, and `DELETE` requests on 
* api/categories
* api/products
* api/tags

Example of `POST` api/tags

See the video in the description for a more detailed walkthrough of the endpoints and requests.

## Code Snippets

Below is a code snippet showing the definition of the many to many relationship between Product and Tag through the ProductTag table
```Javascript
// Products belongToMany Tags (through ProductTag)
Product.belongsToMany(Tag, { through: ProductTag, foreignKey: 'product_id'} )
// Tags belongToMany Products (through ProductTag)
Tag.belongsToMany(Product, { through: ProductTag, foreignKey: 'tag_id'})
```


## License

Refer to the license in the Github repo.
