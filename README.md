# small-business-enterprise-system
An online enterprise management system with non-trivial functionalities for a generalized local business. 

We created a website that allows users to shop for clip-art stickers. The user can be a customer or admin. The website has a homepage, login, registration, products, and orders page.
Customers can change their profile details, view products and make orders. They can view their orders as well.
Admins can change user roles, view/modify/add/delete products, and view orders. They can update shipping dates and order status for the orders.
The shop calls a storage procedure to reduce the available products based on the order quantity.

The database is for a small business. It keeps track of products and orders made by users. Users can either be customers or the admin/owner of the small business.  

![image](https://user-images.githubusercontent.com/67254834/231038253-a7644e61-2007-4aa0-a9f3-9ccd521cf307.png)
![Screen Shot 2025-03-24 at 10 42 34 PM](https://github.com/user-attachments/assets/ba1cf661-3c90-4e01-869a-81a8a196559e)
![Screen Shot 2025-03-24 at 10 43 11 PM](https://github.com/user-attachments/assets/374c997c-9f28-46fb-b873-4a337bba57f1)
![Screen Shot 2025-03-24 at 10 43 27 PM](https://github.com/user-attachments/assets/202f5d9f-7f7e-4b78-b0d5-0c8093e694ff)
![Screen Shot 2025-03-24 at 10 43 45 PM](https://github.com/user-attachments/assets/e086f7ca-8f88-40bd-885d-0ddf0d6d2688)
![Screen Shot 2025-03-24 at 10 43 57 PM](https://github.com/user-attachments/assets/e34289a8-1024-42e9-9d5e-49645ba40c13)
![Screen Shot 2025-03-24 at 10 44 17 PM](https://github.com/user-attachments/assets/aecd962e-7e37-4f63-aa67-6281b1358020)





# ENTITY

## USER:
**Attributes:** cid, cfirstName, clastName, cusername, cpassword, address, email

**Constraints:**
primary key: cid

not null: cfirstName, clastName, email, address

unique: email, username

## PRODUCT: 
**Attributes:** pid, pname, price, quantity

**Constraints:**

primary key: pid

not null: pname, price

check: price > 0, quantity >0

unique: name


## ORDER: 
**Attributes:** id, order_date, ship_date, cust_id, prod_id, status

**Constraints:**

primary key: oid

foreign key: cust_id, prod_id

not null: cust_id, prod_id, orderDate  

Check: quantity>0

## ROLE:
**Attributes:** roleID, userRole

**Constraints:**

Primary key: roleID

Not null: userRole (admin/customer)

## RELATION: 

* USER- ONE TO MANY -ORDER
	-customer can make many orders

* ORDER- MANY TO MANY -PRODUCT
	-order can include many products
	-product can be in many orders

* USER - MANY TO ONE- ROLE (total participation)
	-user can only have one role 
	-role can have many users.




