# 📚 College Library System - ECS740P Coursework

## ℹ️ About this Repository
This repository contains the project I did with two coursemates as a part of the coursework for **ECS740P - Database Systems**. Together, we designed and implemented database systems for the **College Library System**.

---

## ✅ Task
We were required to **design and implement an Oracle application** that satisfies the given requirements. This included setting up a database schema and providing access methods in the form of queries and views. The key steps involved:

1. **Creating a conceptual schema** using an ER or UML diagram.
2. **Deriving a relational schema** from the ER diagram.
3. **Normalising the relations** to ensure efficiency.
4. **Implementing the schema** in Oracle SQL.
5. **Populating the database** with a representative dataset.
6. **Defining specialised views** for different user groups.
7. **Creating SQL queries** to be used as canned queries for naive users.

---

## ❗️ Requirements

### 📌 General Functionality
#### 📖 Resource Management
- Track various resources, including physical books, eBooks, and electronic devices (e.g., laptops, tablets).
- Record details such as:
  - Class number (if applicable).
  - Number of copies available.
  - Physical location (floor and shelf number, if applicable).
  - Digital access limits for eBooks.

#### 👥 Member Management
- Maintain records of **library members** (students and staff).
- Enforce **borrowing limits**:
  - **Students**: Maximum of **5 items** at a time.
  - **Staff**: Maximum of **10 items** at a time.

#### 🔄 Loan and Reservation Management
- Support different **loan periods**:
  - **Standard**: 3 weeks.
  - **Short loan**: 3 days.
  - **Library-only** resources.
- Manage **reservations**:
  - Notify the **earliest reservation holder** when an item becomes available.
  - Handle **unclaimed reservations** (cancel after three unsuccessful attempts).

#### 💰 Fines and Suspensions
- **Overdue fines**: £1 per day.
- **Suspension**: Members owing more than **£10 in fines** are suspended until all items are returned and fines are paid.

#### 🕵️‍♂️ Historical Records
- Maintain **loan history** to track popular resources.
- Track **suspended members** due to overdue loans or unpaid fines.

### 📌 Specific Records to Be Maintained
- **Resources**: All physical and digital library items.
- **Library Members**: Students and staff records.
- **Reservations**: Current reservations and failed loan offers.
- **Loans**: Active and overdue loans, including statuses.
- **Fines**: Amounts owed and suspension statuses.
- **Loan History**: Previously borrowed resources.

---

## 👩🏻‍💻 Environment
The project was implemented using **Oracle Live SQL**.

---

## 🛠️ Stack
- **Database**: Oracle SQL
- **Diagrams**: ER/UML
- **Schema Design**: Normalisation to 3rd Normal Form

---

## 🌲 Repository Structure
```
.
├── DB_Coursework_1_solution.pdf   # Full documentation with ER diagrams, schema, queries, and views
├── DB_Coursework_1_solution.sql   # SQL scripts for schema, views, triggers, and test data
└── README.md                      # Project overview and details
```

### 📄 `DB_Coursework_1_solution.pdf`
- **Assumptions** made during design.
- **Conceptual schema** (ER diagram) and explanation.
- **Relational schema** (mapping from ER to relational model, including primary and foreign keys).
- **Normalisation process** and justification for 3rd Normal Form.
- **SQL views**: 4 defined views with `CREATE VIEW` commands and outputs.
- **SQL queries**: 12 meaningful and distinct queries with outputs.

### 📜 `DB_Coursework_1_solution.sql`
- **Table creation** (`CREATE TABLE` statements with constraints).
- **Triggers** to:
  - Auto-update **overdue fines**.
  - Suspend members with overdue fines > £10.
  - Enforce **loan limits**.
  - Update **reservation statuses**.
  - Ensure max **3 reservation attempts** per item.
- **Sample test data**.
- **Four `CREATE VIEW` commands**.

---

## 🪞 Reflection

I was actively involved in all aspects of the **College Library System** project, assuming both technical and leadership roles. As an experienced backend developer, I **led two teammates with no prior development knowledge**, mentoring them in fundamental database concepts, **answering technical questions**, and ensuring they understood the key principles of database design. I was responsible for dividing tasks, **reviewing their work**, setting the project's direction, and **making technical decisions** to keep the implementation aligned with our goals. This experience not only strengthened my technical expertise but also enhanced my leadership and mentoring skills.

My contributions included designing the **Conceptual Diagram** and **ER Diagram**, ensuring the database structure was organised and met the project's requirements. I developed efficient SQL queries and **views** to support various use cases, and implemented **triggers** to automate business logic. Additionally, I **reviewed all SQL scripts**, providing constructive feedback to improve code quality and ensuring best practices in database **normalisation** and **query optimisation** were followed. Through this process, I reinforced my ability to design **scalable database systems** while maintaining high code quality and optimising performance. As a result, our project received the **highest score** in the course.