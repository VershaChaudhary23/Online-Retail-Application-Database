# Online-Retail-Application-Database
ER Diagram

Entities:

User (userId, name, phoneNum)
Buyer (userId)
Seller (userId)
Bank Card (cardNumber, userId, bank, expiryDate)
Credit Card (cardNumber, organization)
Debit Card (cardNumber)
Store (sid, name, startTime, customerGrade, streetAddr, city, province)
Product (pid, sid, name, brand, type, amount, price, colour, customerReview, modelNumber)
Order Item (itemid, pid, price, creationTime)
Order (orderNumber, creationTime, paymentStatus, totalAmount)
Address (addrid, userid, name, city, postalCode, streetAddr, province, contactPhoneNumber)

Relationships:

Manage (userid, sid, SetupTime) (userid ref Seller, sid ref Store)
Save to Shopping Cart (userid, pid, quantity, addtime) (userid ref Buyer, pid ref Product)
Contain (orderNumber, itemid, quantity) (orderNumber ref Order, itemid ref Order Item)
Deliver To (addrid, orderNumber, TimeDelivered) (addrid ref Address, orderNumber ref Order)
Payment (C.cardNumber, orderNumber, payTime) (C.cardNumber ref Credit Card, orderNumber ref Order)

Create Database:

Table.sql: Create tables for entities and relationships above.
Insert.sql: Insert datas into tables.
Modification.sql: Modify the data.

Java GUI
simpleJDBCPostgres.java is only a sample Java to link the Postgresql JDBC driver and connect to the database for your reference.

SQL.java is the acutal program that we wrote to submit the sql execution to the database based on the sample above.

Java_GUI contains the Java programs for creating the GUI.

MainFrame.java: Provide main menu for user to choose different function.

Register.java: User registration interface.

Login.java: User log-in interface.

AddAddress.java: Add address for delivery.

SearchFrame.java:Search products in database.

SaveToCartFrame.java: Add products into shopping cart.

SetUpOrderFrame.java: View the shopping cart and create the order.

addressFrame.java: Select a delivery address and finish the shopping.
