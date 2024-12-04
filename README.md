# DREAM-TEAM---PROJECT-2

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

The order table is also attached to the Order Detail table with Order being the primary table in the one-to-many relationship. Order Detail is then attached to the record table with another one-to-many relationship with Record being the primary table. This brings in both sides of the business; the product side which includes the records, and our financial side which includes our customers, employees, and orders. One last table was added on at the end for any promotions or discounts the business has. There is a many-to-many relationship between record and promotion to make sure the specific record that was chosen is eligible for a promotion, and the promotion that was chosen is applied to the correct record. 

To increase the efficiency of our model our team added some one-to-one recursive relationships. We added one for a boss in our Employee table as it will help management see how employees are performing under different authorities. We also added a one-to-one recursive relationship for holiday promotions in our promotion table as Christmas is coming around the corner! Our holiday promotions are simply a 10% discount added on to all purchases starting December 1st and ending December 26th, which is why we thought it would be best represented through a recursive relationship. 

Lastly, keeping the holiday spirit in mind we added on a loyalty program table. This was attached to the customer table with a one-to-many relationship and also attached to the promotion table with another one-to-many relationship. Management thought this was important to add as a loyalty program will allow more incentive for our customers. 

![Image 12-3-24 at 11 45 AM](https://github.com/user-attachments/assets/d155d5d5-f465-4ba8-8bdd-bfcb39e0f486)




## Data Dictionary

![Image 12-3-24 at 12 39 PM](https://github.com/user-attachments/assets/3a7c38af-32a6-40dc-b6f6-fd81955cda36)
![Image 12-3-24 at 12 40 PM](https://github.com/user-attachments/assets/d2887e47-cfa6-4b43-b92e-859b518b73f2)



### Complex 1
 This query shows records and suppliers of which items have gone below the low stock threshold of 20 items.
 
<img width="633" alt="Screenshot 2024-12-03 at 5 21 22 PM" src="https://github.com/user-attachments/assets/d2796cea-4215-4fe6-a557-5696b76cae9d">


**Why is this important for management? -** Management can use this to help keep the supply chain moving smoothly. If management knows what Records are running low, they can then restock those records so that they do not have to restock everytime current stock on a record hits zero.

### Complex 2
This query identifies each genre by total revenue and lists it in descending order.

<img width="468" alt="image" src="https://github.com/user-attachments/assets/a057414c-b413-440b-b6be-9e0e221c4f8d">

**Why is this important for management? -** Management can use this to identify the most popular genres and provides insights into customer preferences. Management can check which genre is driving the most revenue and prevent unnecessary inventory costs by stocking up on the most popular genres based on customer demand. This also allows Management to communicate with suppliers to ensure the best-selling genres are in stock. 
 
### Complex 3 
This query lists each employee based on the highest total revenue generated from orders. 

<img width="468" alt="image" src="https://github.com/user-attachments/assets/8f18846d-d782-4c18-870f-3930d607df96">


**Why is this important for management? -** This helps management assess individual performance and recognize employees who are generating the most revenue. This could highlight other skills, such as maintaining strong customer relationships. Top employees can share skills and product knowledge to others and management can also provide more training and support for lower-performing employees.


### Complex 4

This query generates a list of employees who processed shipments that were associated with orders containing at least three records.

<img width="992" alt="Screenshot 2024-12-03 at 22 20 14" src="https://github.com/user-attachments/assets/82ef5b6b-a461-4da7-bfee-b19a1ea0c1c8">

**Why is this important for management? -** Management can use this information to recognize high-performing employees, balance workloads, and optimize resource allocation. It also helps identify potential bottlenecks in operations by showing which employees are handling more complex or larger orders.

### Complex 5
List all promotions that apply to records by artists from a specific country, including the promotion description and artist name.
<img width="781" alt="Screenshot 2024-12-03 at 22 19 40" src="https://github.com/user-attachments/assets/bb552c1a-f009-4441-9d7c-9820ae0e47ea">
<img width="254" alt="Screenshot 2024-12-03 at 22 19 16" src="https://github.com/user-attachments/assets/f7163459-92d3-41da-9641-a55be294c4c8">

**Why is this important for management? -** By focusing on artists from a specific country, management can tailor marketing strategies to align with regional trends or consumer preferences. This data also aids in evaluating the effectiveness of promotions tied to domestic talent, providing insights for future campaigns.

### Tableau 1

This visualization shows the top 5 genres by revenue earned in the year of 2023. 

![tableau 1](https://github.com/user-attachments/assets/a5dce6ae-7593-433c-be2b-17170ac1c6b4)


**Why is this important for management? -** Management can use this to make strategic decisions regarding where they want to focus their marketing capital moving into 2024. Since Jazz is shown to be generating the most revenue it would be smart to make sure to invest a large amount of funds into Jazz marketing moving into 2024.

### Tableau 2
This visualization shows the customers listed by their first name and last name on the y-axis and their order totals summed up on the x-axis

<img width="749" alt="Screenshot 2024-12-03 at 10 55 58 PM" src="https://github.com/user-attachments/assets/784f08e9-50cb-4353-8f42-4271c9551017">

**Why is this important for management? -** This shows management who their top buyers are. With this information, management can make informed and strategic decisions based on customer demographics. This allows management to target specific market segments effectively and efficiently. 

### Tableau 3
This visualization shows the amount of records the shop sold per year. The year is on the x-axis and the quantity is on the y-axis. 
<img width="668" alt="image" src="https://github.com/user-attachments/assets/bc44d70a-2f0b-42d8-aef5-d76c5be3c693">

**Why is this important for management? -** This helps managment get an idea for how their shop is doing and if they are trending upwards or downwards. If there is low sales for several years in a row, that is a signal to managment that there should be a change to the business.

### Database Information
Name of the database: cs_jdd29152

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_QX();
