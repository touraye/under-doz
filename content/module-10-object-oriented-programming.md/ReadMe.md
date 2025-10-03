# Object Oriented Programming

This chapter introducing one of the most fascinating topic as far as Java is concerned.  

Topic to cover:

* [What is a class]()
* [What is an object]()
* [Object Oriented Programming]()
  * [Property]()
  * [Behavior]()
* [Constructor]()
  * [Types of constructor]()
* [keywords]()
  * [this]()
  * [new]()
* [Packages]()
* [Wrapper classes]()
* [static and none static]()
* [Principles of OOP]()
  * [Inheritance]()
  * [Polymorphism]()
  * [Encapsulation]()
  * [Abstraction]()





Google Sheets: I have small business venture that I wish to keep track of expense and income using Google Sheets. This Google sheet will record transaction (expense and income) on a monthly basis and split the income among three parties: business, person1, and person2. 

The Google Sheet should give an insight in the expense and income column figuratively and via analytic. The expense and incom should compound, firgured together throughout. The Google Sheet will be divided in different Sheets from structural purpose. This sheet includes: Dashoard, Transaction, and Setting. 

1. Dashboard will some insights and analytics between income and expense using charts and calculated flieds. 
2. Transaction will be the main interactive Sheet where all the transaction will the inputed. 
3. Setting Sheet will serve as configurations (splitting up shares between the three parties) and setting predefined type like (income and expense). 

**Entities / column** 

* **Setting:** The Setting sheet will not have traditional columns and row setting like Transaction rather will have scattered values. It will have Income and Expense under Tab columns. Shares column (around column f) will have the parties: business, person1 and person2. Each will have a percentage value to receive for example the business will take 20% and person1 and person2 split the rest. So, therefore this split will happen on a monthly basis and for each month the record should be kept in s table in the Setting Sheet.
* **Transaction:** This sheet will be use to enter transaction of the business for both income and expense. It will have the following columns: 
  * ID: incremental value
  * Type: a dropdown-menu picking from Setting Sheet which are income/expense
  * Amount: A Formatted GMD value with constraints of no negative value.
  * Remarks:  A short note/description about a particular transaction which is optional.
  * Time: Tracking the dame and time dynamically each time the transaction the inputted.
* **Dashboard:** Showing matrix's and analytics in charts and computational values (accumulated: expense and income). The dashboard should also display the shares for each month in charts

Relationships and connectivity: 

Setting Sheet will serve as the base where all the other two Sheets are pulling data from.
