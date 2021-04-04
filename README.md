# PHP Database Example with MVC Pattern

Planning and implementing a web application using **products** from a database,
reads and outputs according to categories. The application offers the possibility of lists of
output product categories and products with **MVC Design Pattern`**. 
A prepared database given.
In the DB you will find amongst other, two tables, which show the products and the
product categories (product_types) that are accessed via a foreign key ([from
products] id_product_types → id [from product_types]).

The queries you need are the two, with the php variable being one of course
must contain a valid value (the ID for the selected category):

- for the list of categories

SELECT id, name FROM product_types ORDER BY name;

- for the products of a category

SELECT t.name AS productTypeName, p.name AS prodcutName
FROM product_types t
JOIN products p ON t.id = p.id_product_types
WHERE t.id = {$ productTypeId};

# Interface

The following two parameters are to be processed via the interface:

- GET Parameter String: action (Can contain the values ​​listTypes and
listProductsByTypeId included)

- GET parameter Integer: typeId (in the case of listProductsByTypeId, this contains
Parameter the ID of the selected category)

Two Examples:

http: //localhost/Uebung3/index.php? action = listTypes
http: //localhost/Uebung3/index.php? action = listProductsByTypeId & typeId = 2

Action output: listTypes:

[{
"productType": "day creme",
"url": http: //localhost/Uebung3/index.php? action = listProductsByTypeId & typeId = 1 "
}, {
"productType": "night creme",
"url": "http: //localhost/Uebung3/index.php? action = listProductsByTypeId & typeId = 2"
}, ... and so on
]