<h2>OKR and KPI</h2>

I am responsible for bringing the first flying taxi service to market by analyzing data and building a product proposal. 
My team and me have discussed and defined Objectives and Key Results (OKR) we want to hit. We want to tackle the most important one right now:

<b>Objective</b>: “Introduce Flyber Taxi as a trustworthy & unique experience to the market in Q2”

The Objective is focused on <b>User Acquisition</b>. At this point in the Product Development Cycle, we want to introduce our service into the market and gain trust of the customers and show them the benefit of Flying Taxis. In the Growth Phase we can focus more on User Engagement where we can improve the awareness and incorporate lessons learned through our first service flights. Later on in the Maturity Phase we can focus more on <b>User Retention & Profitability</b> to secure revenues and improve margins. <b>Key Performance Indicators</b> will help us to measure our actions.

1. Customer Acquisition Costs :arrow_right: 1/3 of the income per User (CLV) Source: https://blog.hubspot.com/service/what-does-cac-stand-for
2. Number of Flights/ Week :arrow_right: ~ 105 Flights each Aircraft per Week	 
   - Best Days and Time to operate is Friday and Saturday between 8am – 4pm as well as 5pm – 9pm	
   - This makes up 24 operating hours per week which equals 1.440 minute per week
   - 1440 minutes divided through median duration (11min) = 131 Flights per Week
   - Using Pareto Principle (80/20) we estimate that 131*80% = 105 Flights per Week are doable
3. Number of Weekly active Users :arrow_right: ~ Assuming 3% Conversion rate => 7000 weekly active Users Source: https://blog.hubspot.com/marketing/conversion-rate-optimization-guide
   - Having two aircrafts we are aiming for 105 *2 = 210 Flights per Week in Total
   - Assuming that 210 Flights is the result of a 3% conversion rate we expect 6.982 weekly active Users	which makes up approx. 7000 Users
4. Net Promoter Score :arrow_right: in average 10 out of 10 times the customer would most likely refer us for network effects
5. Average Score of Recommendation :arrow_right: in average around 8 out of 10 times the customer had a good experience for gaining trust

<h2>Creation of an Instrumentation Plan</h2>
Having well designed KPIs we need to make sure that we collect the right data. By creating an <b>instrumentation plan</b> for the events, we need to collectand log, we will be able to physically measure the KPIs. The events will be stored in databases for access. First we start with KPIs & breakdown the user steps that contribute to the KPI. Next, we understand the transaction flow and build in events that should be recorded. Here is the result: 

1. Customer Acquisition Costs (UserSignUp, UserRideHistory, MarketingCosts)
2. Number of Flights/ Week (AircraftPaidTakeoffs, UserOnboard, UserOffboard)
3. Number of Weekly active Users (UserLogIn, UserFlightSearch)
4. Net Promoter Score (RatingNPS)
5. Average Score of Recommendation (UserRideHistory, UserRatings)

A distinction is made between Entity and Event data. 
An <b>Entity</b> is a unique object such as a customer, product, order, etc. 
Entity Attributes are the properties that describe it. Entity data is stored in a table, for every entity there is a separate table, and every table has columns that describe these entities. One row is dedicated to recording one type of each entity. The drawback of the entity data model is that the joins might get complicated and introduce latency. The advantages are the removal of data duplication and a simple, easy to understand basic structure. <b>Event</b> data mainly describes the actions performed by entities. A Few key pieces of information that are captured in event data might be the action, timestamp and state. Below you see examples how Entity and Event Data can be required:

<img src="https://user-images.githubusercontent.com/72414477/150946847-8ae491f1-6b29-4148-93fb-dc2044e911c5.png" width="200" height="300"> 

Having an instrumentation plan, we also would need to think about the <b>Data Strategy</b> in terms of 
 - Data Processing (ELT vs ETL/ Batch vs Stream), 
 - Data Storage (SQL vs NoSQL/ Data Lake/ Data Warehouse), 
 - Data Infrastructure Strategy (Build vs Buy/ Cloud vs On-Prem) and Security & Compliance. 

While we are running business and collecting data, we would also like to test features to improve our product (here helps the <b>Design Thinking</b> Framework). Therefore we need enough data to run experiments (MVP sample size). Assuming we are able to get 7k new sign ups per week we might be able to have sufficient users to build up two variations within a month. We expect to have first insights after 2 months of the launch. Source: https://www.optimizely.com/sample-size-calculator?conversion=3&effect=20&significance=95

<img src="https://user-images.githubusercontent.com/72414477/150948628-250cc4a6-d795-45cf-b2dc-a919cb73bb62.png" width="250" height="100">

<h2> Building a Data Pipeline with AWS </h2>

Having considered all of the areas above, we are able to structure <b>data pipeline</b>. 

<img src="https://user-images.githubusercontent.com/72414477/150949133-2587b91d-1e50-4fb1-8139-19c6e3f4a22e.png" width="400" height="150">

<h4>How does the life cycle of data and processes work?</h4>

1. Data is collected from the user (either through usage of desktop or app version) & from Taxi Drones
2. Data is transferred through an Load Balancer to our Servers who are writing entity data to a structured database and event data into an unstructured database (S3 bucket as Data Lake)
3. Data Storages are hosted through <b>AWS</b>. Location is Frankfurt (Germany). 
4. Both data storages will send their information regularly to the Data Warehouse.
5. Databases and the Data Warehouse are mirrored in another AWS data center (Milan) for Disaster Recovery purposes.
6. Flyber is evaluating the information with Tableau, MS Excel and an Integrated Development Environment for applying Machine Learning Frameworks like Scikit-Learn, Keras/Tensorflow. Access is enabled through an authorization concept and custom build APIs.

➡️Data is collected with each User2Product and Drone Interaction (aka not time dependent); Storage Duration: 1 year and unlimited after anonymization

<h4>Are the data accurate and kept up to date?</h4>

Data is collected based on action and stored in the connected database/ data lake. From there the data will be forwarded to the Data Warehouse during night (supports completeness & accuray of data through usage of low latency timeframes).  Data Validation after transfer is automatically done via scheduled job between data sources and Data Warehouse. Deviation will be investigated & solved by employees.
