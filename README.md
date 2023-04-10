# small-business-enterprise-system
An online enterprise management system with non-trivial functionalities for a generalized local business. 

The database is for a small business. It keeps track of products and orders made by users. Users can either be customers or the admin/owner of the small business.  


<img width="707" alt="Screen Shot 2023-04-10 at 4 45 12 PM" src="https://user-images.githubusercontent.com/67254834/230995163-6639ac6f-a8de-40c4-aa58-3a9972292e06.png">


ENTITY

USER:
Attributes: cid, cfirstName, clastName, cusername, cpassword, address, email
Constraints:
primary key: cid
not null: cfirstName, clastName, email, address
unique: email, username

PRODUCT: 
Attributes: pid, pname, price, quantity
Constraints:
primary key: pid
not null: pname, price
check: price > 0, quantity >0
unique: name


ORDER: 
Attributes: id, order_date, ship_date, cust_id, prod_id, status
Constraints:
primary key: oid
foreign key: cust_id, prod_id
not null: cust_id, prod_id, orderDate  
Check: quantity>0

ROLE:
Attributes: roleID, userRole
Constraint:
Primary key: roleID
Not null: userRole (admin/customer)

RELATION: 

*USER- ONE TO MANY -ORDER
	-customer can make many orders

*ORDER- MANY TO MANY -PRODUCT
	-order can include many products
	-product can be in many orders

*USER - MANY TO ONE- ROLE (total participation)
	-user can only have one role 
	-role can have many users.

