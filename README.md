DETAILS:
-------
Our API is divided into sub folders: (for the structure enhancement)
Assets : for the static media.
Helpers : for the validation of each model.
Models : for each entity we have (Product, User, Order and OrderStatus).
Node modules: for the installed packages.
Routes : for the middlewares and the main functionalities.

	*Node: “index.js” file is the entry point of our API.
  
------------------------------------------------------------

MODELS
-------
Here’s the required fields in each model:

ORDER MODEL:
------------
user >> object {}
products >> array of [products and its counts]  [{},number]

PRODUCT MODEL:
--------------
title >> string
price >> number
quantity >> number
category >> Enum ["women", "men", "children"]

USER MODEL:
username
string
email
string
password
String (hashed in db)
gender
Enum [“male”, “female”]
role
Enum [“member”, “admin”]

ROUTES
Routes Folder has the following:
Middleware folder for the authentication (dealing with the token, checking on authorization of the user) and checking on the user’s role.

 Users.js file has routes for the following:		
[GET]
Getting all users.
/users
[GET]
Getting a specific user using its id.	
/users/:id
[POST]
Adding a new user. (Register)
/users + body
[PUT]
Getting a specific user using his email and password. (Login)
/users + body
[PATCH]
Updating an existing user using its id.	
/users/:id + body
[DELETE]
Deleting an order using its id.		
/users/:id

 Products.js file has routes for the following:		
[GET]
Getting all products.
/products
[GET]
Getting products based on a specific category. 
(Men || Women || Children)
/products/category/:category
[GET]
Getting products based on their names. (Search)
/products/productName/:productName
[GET]
Getting the promoted products only.
/products/promoted
[GET]
Getting a specific product using its id.	
/products/:id
[POST]
Adding a new product.	
/products + body
[PATCH]
Updating an old product using its id.
/products/:id + body
[DELETE]
Deleting a product using its id. (Soft Delete)		
/products/:id	

 Orders.js file has routes for the following:		
[GET]
Getting all orders.
/orders
[GET]
Getting a specific order using its id.	
/orders/:id
[POST]
Placing a new order.	
/orders + body
[PATCH]
Updating an old order using its id.	
/orders/:id + body
[DELETE]
Deleting an order using its id.		
/orders/:id
[GET]
Getting the orders of a user using the user’s id.
/orders/user/:id

