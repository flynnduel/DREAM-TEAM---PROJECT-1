# DREAM-TEAM---PROJECT-1

## Team Name
MIST 4610: 29704 - Dream Team

## Team Members
1. Flynn Duel https://github.com/flynnduel
2. Anna Pachon https://github.com/AnnaPachon
3. Jeremiah Doherty https://github.com/jdoherty18
4. Geetika Polkam https://github.com/geetikapolkam
5. Krutee Pillay https://github.com/kruteepillay
## Problem Description
The objective is to design and implement a relational database that captures the key functions of a music record distribution company. At the core of this model is the record entity, representing individual music releases distributed to customers. The model will capture various relationships, including those between records, artists, genres, and suppliers, along with customer interactions through orders and shipments. This structure needs to accurately represent how records are supplied, promoted, and sold, while also allowing for tracking of inventory levels and employee involvement in order processing. The goal is to generate sample data for each entity and populate the database, enabling us to perform analytical queries that provide insights into sales trends, inventory management, and the effectiveness of promotions, supporting data-driven business decisions.

## Data Model
**Explanation of Data Model:**

Our data model’s main goal was to represent the ins and outs of the business operations for a record/ vinyl store. We started with two primary tables for Artist and Genre. We linked these two tables to our Record table with a one-to-many relationship as each record will have only one artist and genre, but each artist and each genre will have multiple records. 

Attached to the record table is our Supplier and Inventory tables. These two tables are connected through a many-to-many relationship as we cannot have records in our inventory if our supplier does not have them on hand and our supplier does not need to supply us with records that do not comply with our inventory. These two tables created the ‘supplier_has_record’ table which is linked to our Record table with a one-to-many relationship. This ensures the database checks for records that are available both from our suppliers and our inventory. 

On the other side of the database, we started with 3 primary tables; Customer, Shipment, and Employee. Customer and Employee are both attached to the Order table with one-to-many relationships, and shipments are attached to the Order table with a one-to-one relationship. This is because our shipments will go out once. Our order table contains our foreign keys for all these tables so we know that when we look at the table we can see the shipment status, the employee who rang in the order, and the customer who ordered it. 

The order table is also attached to the Order Detail table with Order being the primary table in the one-to-many relationship. Order Detail is then attached to the record table with another one-to-many relationship with Record being the primary table. This brings in both sides of the business; the product side which includes the records, and our financial side which includes our customers, employees, and orders.

One last table was added on at the end for any promotions or discounts the business has. There is a many-to-many relationship between record and promotion to make sure the specific record that was chosen is eligible for a promotion, and the promotion that was chosen is applied to the correct record. 

![project1dbpic](https://github.com/user-attachments/assets/328c88e4-59ad-4e66-9eb4-57fdf2dbd398)

## Data Dictionary

![Image 10-13-24 at 6 15 PM](https://github.com/user-attachments/assets/d689968c-9a82-46b7-bfb7-5430b57b2cfd)
![Image 10-13-24 at 6 32 PM](https://github.com/user-attachments/assets/22ee2765-c9ae-4976-a42a-6f70675daf86)

## Queries
### Complex 1
 This query produces the remaining inventory for each artist in descending order.
 
<img width="510" alt="Screenshot 2024-10-13 at 3 58 51 PM" src="https://github.com/user-attachments/assets/2a261965-8bba-4352-8555-7aa209bc82e4">

**Why is this important for management? -** Management can use this to plan out promotions and or sales to get records off the shelves.

### Complex 2
This query lists the artists who sold the most records in the store in descending order.

<img width="485" alt="Screenshot 2024-10-13 at 4 00 27 PM" src="https://github.com/user-attachments/assets/6b6fed06-57c1-41e4-9aac-8bf2c02d4a43">

**Why is this important for management? -** Management can use this to identify where most of their revenue comes from and communicate with suppliers to ensure the best selling artists are in stock. 

### Complex 3
This query lists each employee based on the most orders fulfilled to the least amount of orders fulfilled.

<img width="596" alt="Screenshot 2024-10-13 at 4 01 52 PM" src="https://github.com/user-attachments/assets/64d0231e-8791-428f-a12a-636f13f58383">

**Why is this important for management? -** Understanding how many orders each employee has fulfilled is important for management because it allows management to make decisions based off of employee performance. It allows for management to create better systems and differentiate work more efficiently either by getting rid of unnecessary employees or making sure certain employees step up their work. It will show management which employees are doing their jobs well and which ones are slacking. 

### Complex 4

This query shows how many records from each genre have recieved promotions
<img width="729" alt="Screenshot 2024-10-13 at 18 41 12" src="https://github.com/user-attachments/assets/78ed185f-2484-4324-bd62-d3d2bdfccf99">

**Why is this important for management? -** Understanding the patterns between music genres and promotions is critical for managment because it can help them decide which genres and records to keep in stock. If artists from certian genres commonly run promotions, it may not be as profitable for the store to keep lots of records in that genre.

### Complex 5
This query shows the name, order date, and order ID of customers that have placed an order that has not yet been shipped.
<img width="839" alt="Screenshot 2024-10-13 at 18 45 09" src="https://github.com/user-attachments/assets/1c96933c-63f2-40bd-83b3-64efd5767a98">

**Why is this important for management? -** It is important for managers to keep track of what orders have been fulfilled and when. In order to maintain good customer service, managers must ensure orders are being fulfilled in a timely manner and no orders get forgotten.

### Complex 6

This query shows the total sales by employee. 
<img width="761" alt="Screenshot 2024-10-13 at 18 48 06" src="https://github.com/user-attachments/assets/b7d04538-d018-4806-89c0-e2bf6f424fbe">

**Why is this important for management? -** Management can use this to track employee performance and check which employees are bringing in the most revenue. Management can also use this for performance reviews and increase the effectiveness of sales strategies. 

### Simple 1
The first query aims to identify and list all artists from the United States who have a manufacturer's suggested retail price (MSRP) of over $25

<img width="566" alt="Screenshot 2024-10-13 at 4 04 15 PM" src="https://github.com/user-attachments/assets/c67b472e-7d06-49e2-9a04-b98221da219a">

**Why is this important for management? -** This query is valuable for management because it helps them monitor popular and in-demand records within the U.S. market. By identifying which artists and records are commanding higher prices, management can analyze market trends and consumer demand. The data can also inform decisions about where to focus marketing efforts or expand availability, either domestically or internationally, to capitalize on high-demand artists and maximize revenue potential. Understanding these trends at a detailed level enables more strategic planning and optimized inventory management.

### Simple 2
This query shows all of the promotions that were over a week long and how long they lasted each lasted.

<img width="809" alt="Screenshot 2024-10-13 at 18 53 00" src="https://github.com/user-attachments/assets/7f516809-e2e4-496e-85be-c0e5ca3cbaa0">

**Why is this important for management? -** This can help give management insight into what records are demand is like for certian records and what albums customers are least interested in purchasing. Typicaly, records that are on sale for a long time and still do not run out are not popular products. 

### Simple 3
This query lists the number of orders, in descending order, placed in each state.

<img width="500" alt="Screenshot 2024-10-13 at 4 22 00 PM" src="https://github.com/user-attachments/assets/11c2fde8-cd77-4118-9f71-36145e1c858a">

**Why is this important for management? -** Management needs to be able to determine what states are doing the best from a sales standpoint. This query allows management to track where most of their sales are coming from and then make the appropriate decisions regarding the best way to approach selling in each state. One state may have many sales while another is doing really well; this query will allow management to decide on where they want to focus their marketing. It will also further aid management in the decision of if they want to pull out of a certain state that is not producing the amount of sales it needs to be producing.

### Simple 4
This query lists the names of artists who have less than 3 records associated with them.
<img width="584" alt="Screenshot 2024-10-13 at 19 07 09" src="https://github.com/user-attachments/assets/a4fc4d23-66ef-4830-b5d8-1b9fb8657244">

**Why is this important for management? -** This query can be useful to management for identifying underrepresented or emerging artists within their catalog. It helps pinpoint artists who have not yet been capitalized on by the management team. By recognizing these artists, management can explore opportunities to expand their record catalog. This insight is valuable for strategic planning, as investing in these artists could boost market presence and generate additional revenue.

### Database Information
Name of the database: cs_jdd29152

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_QX();
