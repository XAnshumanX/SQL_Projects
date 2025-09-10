# Project Title

# Zomato: Company Overview and Case Study

**Tools Used:** SQL, ER Modeling, Schema Design, Data Analysis

---

## Industry Context

The food delivery and restaurant discovery industry has transformed significantly with the rise of digital platforms. Companies like Zomato have redefined customer engagement by combining convenience, transparency, and personalization. The market has shifted from traditional phone-based ordering to app-based platforms that integrate restaurant discovery, food ordering, delivery, and customer feedback.

### Recent Examples in Industry Context:

* **Zomato & Swiggy Market Leadership (2023):** Together, they captured over 90% of India’s food delivery market.
* **Hyperpure Procurement Model:** Zomato diversified with Hyperpure, supplying high-quality ingredients to restaurants and ensuring consistency.
* **Personalization & AI:** Platforms use machine learning to recommend restaurants based on user preferences and past orders.
* **COVID-19 Impact:** Adoption of contactless delivery and safety protocols boosted trust, accelerating growth in online food ordering.
* **Discounts & Loyalty Programs:** Zomato Gold/Pro membership increased customer retention through dining discounts and delivery perks.

---

## Project Objective

The objective of this case study was to:

* Dissect Zomato’s platform from a **product and data perspective**.
* Understand how Zomato solves real-world challenges in food ordering, restaurant discovery, and delivery management.
* Analyze **schema design** to see how entities and relationships power its ecosystem.

---

## Project Steps

1. **Problem Identification:** Recognized real-world challenges like inefficient ordering, limited options, lack of transparency, and personalization gaps.
2. **Solution Mapping:** Documented how Zomato’s platform addresses each challenge with technology-enabled features.
3. **Schema Design:** Broke down the system into entities, attributes, and relationships supporting business operations.
4. **ER Diagram Creation:** Mapped relationships between users, restaurants, orders, payments, and reviews.
5. **Analysis & Conclusion:** Highlighted how Zomato balances customer experience with operational excellence.

---

## Data Model (Schema)

### Entities & Attributes:

1. **User Entity** – UserID, Full\_Name, Email, Phone\_Number, Membership, Rating.
2. **Restaurant Entity** – RestaurantID, Name, Address, Phone\_Number.
3. **Partner Entity** – PartnerID, Name, Contact, Area, Rating, License.
4. **Order Entity** – OrderID, UserID, RestaurantID, PartnerID, Order\_Status, Total\_Amount, Discount.
5. **Payment Entity** – PaymentID, OrderID, Payment\_Mode, Payment\_Status, Amount.
6. **Menu Entity** – ItemID, RestaurantID, Item\_Name, Price, Availability.
7. **Address Entity** – AddressID, UserID, Address.
8. **Review Entity** – ReviewID, UserID, RestaurantID, Rating, Comments, Review\_Date.

### Relationships:

* Users — Orders: One-to-Many
* Restaurants — Orders: One-to-Many
* Orders — Payment: One-to-One
* Restaurants — Menu: One-to-Many
* Users — Reviews: One-to-Many
* Restaurants — Reviews: One-to-Many
* Users — Address: One-to-Many

---

## Top Features of Zomato

* **Restaurant Discovery** – Search and filter by cuisine, ratings, location.
* **Menu Exploration** – Detailed menus with images and pricing.
* **Order Placement** – One-click ordering through app/web.
* **Real-Time Tracking** – Track food from preparation to delivery.
* **User Reviews & Ratings** – Crowdsourced decision-making.
* **Discounts & Deals** – Personalized offers to increase loyalty.

---

## Project Files Description

* **Documentation File:** Product Dissection – Zomato (this document).
* **ER Schema Design:** Entity relationship diagram outlining users, restaurants, orders, payments, and reviews.
* **SQL Scripts (Optional):** To simulate schema creation and queries for insights.

---

## Execution Instructions

1. Review schema to understand entity relationships.
2. Create ER Diagram based on entity list.
3. Implement schema in SQL database.
4. Run sample queries:

   * Top 5 most-ordered restaurants.
   * Average delivery partner ratings.
   * Customer order frequency analysis.


### 🍽️ Zomato Case Study – PostgreSQL Project 

This project is a **Product Dissection of Zomato** focusing on how its data model supports restaurant discovery, food ordering, delivery, and reviews.
It includes **PostgreSQL schema design, sample data, and queries** for insights.



---

##  Queries

### 1. Top 5 Most-Ordered Restaurants

```sql
SELECT r.Name AS Restaurant, COUNT(o.OrderID) AS Total_Orders
FROM Orders o
JOIN Restaurants r ON o.RestaurantID = r.RestaurantID
WHERE o.Order_Status = 'Delivered'
GROUP BY r.Name
ORDER BY Total_Orders DESC
LIMIT 5;
```

### 2. Average Delivery Partner Ratings

```sql
SELECT Partner_Name, ROUND(AVG(Partner_Rating),2) AS Avg_Rating
FROM Partners
GROUP BY Partner_Name;
```

### 3. Customer Order Frequency Analysis

```sql
SELECT u.Full_Name, COUNT(o.OrderID) AS Order_Count
FROM Users u
JOIN Orders o ON u.UserID = o.UserID
WHERE o.Order_Status = 'Delivered'
GROUP BY u.Full_Name
ORDER BY Order_Count DESC;
```

---

## ✅ This project demonstrates how **Zomato’s platform** can be modeled in PostgreSQL with:

* Relational schema for users, restaurants, orders, and reviews.
* Sample dataset for quick testing.
* SQL queries that provide **business insights** like top restaurants, partner ratings, and customer frequency.



---

## Conclusion

Zomato’s platform addresses inefficiencies in traditional food delivery by providing **convenience, transparency, and personalization**. Its robust schema supports millions of users, orders, and restaurants while enabling scalable growth. The dissection shows how Zomato blends **technology, data, and operations** to become a transformative force in the food service industry.



## 🚀 About Me - Hi, I'm Anshuman Chawhan
Innovative Data Analyst with a Creative Edge in Data Solutions
www.linkedin.com/in/anshumanchawhan


