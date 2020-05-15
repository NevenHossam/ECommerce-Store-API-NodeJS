DETAILS:
------------------------------------------------------------
Our API is divided into sub folders: (for the structure enhancement)
1. Assets : for the static media.
2. Helpers : for the validation of each model.
3. Models : for each entity we have (Product, User, Order and OrderStatus).
4. Node modules: for the installed packages.
5. Routes : for the middlewares and the main functionalities.


	*Node: “index.js” file is the entry point of our API.
  
-----------------------------------------------------------------------

MODELS
------------------------------------------------------------
Here’s the required fields in each model:

ORDER MODEL:
------------
1. user >> object {}
2. products >> array of [products and its counts]  [{},number]

PRODUCT MODEL:
--------------
1. title >> string
2. price >> number
3. quantity >> number
4. category >> Enum ["women", "men", "children"]

USER MODEL:
-----------
1. username >> string
2. email >> string
3. password >> String (hashed in db)
4. gender >> Enum [“male”, “female”]
5. role >> Enum [“member”, “admin”]

-----------------------------------------------------------------------

ROUTES
------------------------------------------------------------
Routes Folder has the following:
- Middleware folder for the authentication (dealing with the token, checking on authorization of the user) and checking on the user’s role.

 Users.js file has routes for the following:	
 -------------------------------------------
1. [GET] >> Getting all users. >> /users
2. [GET] >> Getting a specific user using its id. >> /users/:id
3. [POST] >> Adding a new user. (Register) >> /users + body
4. [PUT] >> Getting a specific user using his email and password. (Login) >> /users + body
5. [PATCH] >> Updating an existing user using its id. >> /users/:id + body
6. [DELETE] >> Deleting an order using its id. >> /users/:id

 Products.js file has routes for the following:	
 ----------------------------------------------
1. [GET] >> Getting all products. >> /products
2. [GET] >> Getting products based on a specific category.(Men || Women || Children) >> /products/category/:category
3. [GET] >> Getting products based on their names. (Search) >> /products/productName/:productName
4. [GET] >> Getting the promoted products only. >> /products/promoted
5. [GET] >> Getting a specific product using its id. >> /products/:id
6. [POST] >> Adding a new product.	>> /products + body
7. [PATCH] >> Updating an old product using its id. >> /products/:id + body
8. [DELETE] >> Deleting a product using its id. (Soft Delete) >> /products/:id	

 Orders.js file has routes for the following:
 -------------------------------------------
1. [GET] >> Getting all orders. >> /orders
2. [GET] >> Getting a specific order using its id. >> /orders/:id
3. [POST] >> Placing a new order. >> /orders + body
4. [PATCH] >> Updating an old order using its id. >> /orders/:id + body
5. [DELETE] >> Deleting an order using its id. >> /orders/:id
6. [GET] >> Getting the orders of a user using the user’s id. >> /orders/user/:id

