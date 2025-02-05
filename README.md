## ℹ️ About this Repository
This repository contains the project I did with two coursemates as a part of the coursework for **ECS740P - Database Systems**. Together, we designed and implemented database systems for the **University Library System**.

<br/>

### ✅ Task
We were required to **design and implement an Oracle application** that satisfies the given requirements. This included setting up a database schema and providing access methods in the form of queries and views. The key steps involved:

1. **Creating a conceptual schema** using an ER or UML diagram.
2. **Deriving a relational schema** from the ER diagram.
3. **Normalising the relations** to ensure efficiency.
4. **Implementing the schema** in Oracle SQL.
5. **Populating the database** with a representative dataset.
6. **Defining specialised views** for different user groups.
7. **Creating SQL queries** to be used as canned queries for naive users.

<br/>

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

<br/>

## 👩🏻‍💻 Environment
<div align="center">
  <img src="https://img.shields.io/badge/Oracle%20Live%20SQL-f1efec.svg?style=flat-square&logo=data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHN2ZyBpZD0iX+ugiOydtOyWtF8xIiBkYXRhLW5hbWU9IuugiOydtOyWtCAxIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB2aWV3Qm94PSIwIDAgNDUgNDUiPgogIDxpbWFnZSB3aWR0aD0iNDUiIGhlaWdodD0iNDUiIHhsaW5rOmhyZWY9ImRhdGE6aW1hZ2UvanBlZztiYXNlNjQsLzlqLzRBQVFTa1pKUmdBQkFRQUFBUUFCQUFELzRnSFlTVU5EWDFCU1QwWkpURVVBQVFFQUFBSElBQUFBQUFRd0FBQnRiblJ5VWtkQ0lGaFpXaUFINEFBQkFBRUFBQUFBQUFCaFkzTndBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBUUFBOXRZQUFRQUFBQURUTFFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQWxrWlhOakFBQUE4QUFBQUNSeVdGbGFBQUFCRkFBQUFCUm5XRmxhQUFBQktBQUFBQlJpV0ZsYUFBQUJQQUFBQUJSM2RIQjBBQUFCVUFBQUFCUnlWRkpEQUFBQlpBQUFBQ2huVkZKREFBQUJaQUFBQUNoaVZGSkRBQUFCWkFBQUFDaGpjSEowQUFBQmpBQUFBRHh0YkhWakFBQUFBQUFBQUFFQUFBQU1aVzVWVXdBQUFBZ0FBQUFjQUhNQVVnQkhBRUpZV1ZvZ0FBQUFBQUFBYjZJQUFEajFBQUFEa0ZoWldpQUFBQUFBQUFCaW1RQUF0NFVBQUJqYVdGbGFJQUFBQUFBQUFDU2dBQUFQaEFBQXRzOVlXVm9nQUFBQUFBQUE5dFlBQVFBQUFBRFRMWEJoY21FQUFBQUFBQVFBQUFBQ1ptWUFBUEtuQUFBTldRQUFFOUFBQUFwYkFBQUFBQUFBQUFCdGJIVmpBQUFBQUFBQUFBRUFBQUFNWlc1VlV3QUFBQ0FBQUFBY0FFY0Fid0J2QUdjQWJBQmxBQ0FBU1FCdUFHTUFMZ0FnQURJQU1BQXhBRGIvMndCREFBTUNBZ0lDQWdNQ0FnSURBd01EQkFZRUJBUUVCQWdHQmdVR0NRZ0tDZ2tJQ1FrS0RBOE1DZ3NPQ3drSkRSRU5EZzhRRUJFUUNnd1NFeElRRXc4UUVCRC8yd0JEQVFNREF3UURCQWdFQkFnUUN3a0xFQkFRRUJBUUVCQVFFQkFRRUJBUUVCQVFFQkFRRUJBUUVCQVFFQkFRRUJBUUVCQVFFQkFRRUJBUUVCQVFFQkFRRUJEL3dBQVJDQUF0QUMwREFTSUFBaEVCQXhFQi84UUFHd0FBQVFVQkFRQUFBQUFBQUFBQUFBQUFCZ0FFQlFjSUFRTC94QUE0RUFBQkF3SURBZ2tMQlFFQUFBQUFBQUFCQWdNRUFBVUdCeEVVSVFnU0V6RlRWRldTMFJjaUpEUlJWbUZ4ZEtMU0ZTTkJVck9CLzhRQUd3RUFBZ01BQXdBQUFBQUFBQUFBQUFBQUFBTUNCQWNGQmdqL3hBQXRFUUFDQVFNQ0F3UUxBQUFBQUFBQUFBQUJBZ01BQkJFaDBRVVNVVUZoa2FFR0J4WVhVbE5pY29HaXNmL2FBQXdEQVFBQ0VRTVJBRDhBQUlNR0hiWWJNQ0JHYmp4NDZBMjAwMm5SS0VqbUFGR3R1eXB4emVzRnJ4OVk3TXU1V2xoNXhtU1loNVYyTVVBRXFjYkhuQk9oMTQyaEdtdXVsQ05YSmtuWlhzTHhtODJMdG1xbkIxb2p5Rk1odUl2bHAxd1VqUWxwTWZtVWs2NkVyQlNPY2pUZldhMjhZbWt3L2prREhmcnBYcDdpVncxbGJoNFNBUVFBQ0NjL1NBdXVUMkVBNDZWVFpCQjBOS3JDenp6Qnd6bVpqdHpFbUZNTG9za1Baa1IxSkNVSlhLY1NwWkw3aVVBSkMxQlFCRy9jZ2I2cjJsU3FxT1ZVNUE3ZXRXcldXU2VGWkpVNUdJMVVuT083SXBWRTN2Q2VHOFNMYWN2MWxpVGxNQWhzdk5CUlNEcHFCcjhoVXRTcUtzeUhLbkJwc2tTVEx5U0FFZERxS05mSXRtcDdrWEx1anhyMDNrbG11NnJpTjRHdWFpRXFWb0VwNWdDU2VmMkExdXZabSt1TWZkNFU3dGtkQWtySWxzbjBlUU4zRzZKZndydGZzL0I4Ujh0cXg3M2tYL3lrL2Jlc0oyZktmTSswM09OY1hzdEhia2lPdmpxaVRHeVdYaC9WWVF0S3RQa29VY04yckh6cWlsdmd0NFFVUWtxMEVTYnpBYWsrdWV3R3RVN00zMXhqN3ZDblZ0am9FaFoydGsranZqZHh1aVY4S1luQkk0eGhYUGdOcXJUK250MWNIbWtoWDhGeC9HRlljeEpsam1aaUM2S3VVYktkTmxRcENVN0piV2xwWVRvT2NCeHhhdFQvQUQ1MVJma1d6VTl5TGwzUjQxdTNabSt1TWZkNFV0bWI2NHg5M2hVRHdDRmprc2ZMYW5wNnhiNk5RaXdwZ2Zkdlh2WTQvYXNYdXUvaFRxMlJXRXlWa1hLTXIwZDhhQkxuUkszNzBVQVpWWTFkekh5NHc1anQrM3BndVh5M016VnhrdWNvbHBTMGdsSVVRTlIveWphMWV0TCtta2Y0cnJucXp5dWJISDdWaTkxMzhLZFc2SXdtUXNpNXhsZnNQalFKYzZKVy9laW91bmRzOVpYOVBJL3lYUUtLNXNjZnRXTDNYZndwYkhIN1ZpOTEzOEthMW5qaFRjS2E1Y0hlNVlmdDl2d2RHdlg2MHhJZVd0NllwbmsrVFVnQUFCQ3RkZU9hQnJRZEsvL1oiLz4KPC9zdmc+">
</div>

<br/>

## 🛠️ Stack
<div align="center">
   <img src="https://img.shields.io/badge/SQL-0a7dd7.svg?style=flat-square&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAC0AAAAtCAYAAAA6GuKaAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAFFUlEQVRYhe3Z7Y9dVRUG8N+eOTN3OsxLS7XFWgtoqSgBjdqU4EsiSkiMfvU/4J/yLzB+xphADAZfAxprFSGGYtS21jrY0jLtDLf3HD+stb1nbnpbqOklJHclO2fOmX32efaznvXsNZnSdZ2PWix82ADuJuagZxVz0LOKOehZxRz0rGIOelbxkQW9hmN4Di/iHXS3GP/Bj/ClfPdj+D6ex/Up79TR4ip+iGcxQOm67kTbtj9o27argd38zrfQTAP9CZzE1/AoNqZs8EBe38MKHsOT+CL23YGcgnU8jq/i4dzM1VLKdimlP3c5x9T2s8FxfDd3ti5YqTtuex/9PV7GRRzGM3gaD+S8gmGOer+QABbz/pP4HrawXUoZ4ixe77ruOJZwHn/F5WnAG8HssQSykGMLb+ICtnOxM/gddvA5nMCRBCTnXchNXe6tfRSHsCqk+BnB9jUhuYewr5RS62uUoxJ2S9CLCaqvn3/ipWT2XznnbfxbyOMgNu2VxRZ+jVfxVv7uML4upDfIddaFrPYLnR8V0qugax1MjUakczsnVnHtCNZew7neYjXlu6JgdwR7BLtn8FO8ns8PC7YfF2zXrBzJjbdJ2HLv26X381TQg9x9f+Kn8OXczLmcd15I5no+20rwNYZ4N8HLd9/J68he9hpTnCFj0S3suOs6bdtqRLqv5Qcrkxv4hijSK4KN0/gJXsGNfG90mw9zB8amRIebObr+37Bt2+q6ToNL+KOwsQXB/AHhCg+KFDZ5PxKS2MD9uZkaC8ap7t/357xf0LuClK6CrVFK0eAvOeEX+XwgNPis8OAK4iFhcftzE4/hvt7HbuaGruf9SEjjhjtnZBL0ja7rtk0wXaMR7nDZWENLQirH8Wlx8hG6fyLBF1FoK721loWjHErwS/i4yFq/0Aj97+ZmloydpWLaFJmtBtEKYnfRNcKa7jcuxiY/PLC3eBZybgU6WeWbwru3cr0V4RIncu2+pV3CP5KcQ+KEXMv1VpKsk7npkiScz/FukxOeFAfGQu74UH5s1d64nR0dxKkE+nYyuCEyc8DYLUaiqF8Q7nIy563kO2tCnuvCBFaTiFdEb3S2wWfxHeEW1T3q8TtZRDvGNlZENjZy4U18PjdbNVyMD65hgjgrmqznc94mvm2c1X1J5DEhi1Uh36O5zqtNslC11z9gJmMo0nNa+HURunvCOCvVLfqnWklwl5KtX4oD6GJ+c00UdNU0NKWUvo9vdl33FcH+o02ytzsBeNS7r+MCfoUfC4ssycaVZOcRY91OymgkDqSXBcNv5vNBjn7c7K2hlFJPzf1d153Cgw3+ht/a67HDfGnRuEP7k9Dhz4TjED1GLebLeR0KxznSW69NMKNca9W46C/iD3ldFpZZO01oSynLWO+67gHsVtAviXZwOdmqmqyAW1Htr4kmp8YO/mx8Yg4SyCmR9mqXS6I1+KZI8W/yvSv5847Q9pJxa8vY7prc6EFcb0RHd1U0OxVkX48V9HbOG/ZAd/h7Pq99cyOqfQ1fELpvRPP0lCj8A7neGbyRLC8lYZNdXpVpIxxm1Ag99xufDxpD0bJOxnoCeyoBD/J6WGTt5wmynprvO27Xaf0/cU44xDWR1qeN9d2Pu2mo7hno90RPfVUwfp9wmkXh828ICX2QnuR/ca9AE3VQba6IjnEgXOZ0/u7mtJdvF/cSNFFEbwnNbohi2xHH/Ja7BF3m/yiaUcxBzyrmoGcVc9Cziv8C9Qp9a29Fk3oAAAAASUVORK5CYII=">
</div>

<br/>

## 🌲 Repository Structure
```
.
├── DB_Coursework_1_solution.pdf   # Full documentation with ER diagrams, schema, queries, and views
├── DB_Coursework_1_solution.sql   # SQL scripts for schema, views, triggers, and test data
└── README.md                      # Project overview and details
```

📄 `DB_Coursework_1_solution.pdf`
- **Assumptions** made during design.
- **Conceptual schema** (ER diagram) and explanation.
- **Relational schema** (mapping from ER to relational model, including primary and foreign keys).
- **Normalisation process** and justification for 3rd Normal Form.
- **SQL views**: 4 defined views with `CREATE VIEW` commands and outputs.
- **SQL queries**: 12 meaningful and distinct queries with outputs.

<br/>

📜 `DB_Coursework_1_solution.sql`
- **Table creation** (`CREATE TABLE` statements with constraints).
- **Triggers** to:
  - Auto-update **overdue fines**.
  - Suspend members with overdue fines > £10.
  - Enforce **loan limits**.
  - Update **reservation statuses**.
  - Ensure max **3 reservation attempts** per item.
- **Sample test data**.
- **Four `CREATE VIEW` commands**.

<br/>

## 🪞 Reflection

I was actively involved in all aspects of the **University Library System** project, assuming both technical and leadership roles. As an experienced backend developer, I **led two teammates with no prior development knowledge**, mentoring them in fundamental database concepts, **answering technical questions**, and ensuring they understood the key principles of database design. I was responsible for dividing tasks, **reviewing their work**, setting the project's direction, and **making technical decisions** to keep the implementation aligned with our goals. This experience not only strengthened my technical expertise but also enhanced my leadership and mentoring skills.

My contributions included designing the **Conceptual Diagram** and **ER Diagram**, ensuring the database structure was organised and met the project's requirements. I developed efficient SQL queries and **views** to support various use cases, and implemented **triggers** to automate business logic. Additionally, I **reviewed all SQL scripts**, providing constructive feedback to improve code quality and ensuring best practices in database **normalisation** and **query optimisation** were followed. Through this process, I reinforced my ability to design **scalable database systems** while maintaining high code quality and optimising performance. As a result, our project received the **highest score** in the course.