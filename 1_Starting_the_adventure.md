I am responsible for bringing the first flying taxi service to market by analyzing data and building a product proposal. 
My team and me have discussed and defined Objectives and Key Results (OKR) we want to hit. We want to tackle the most important one right now:

<b>Objective</b>: “Introduce Flyber Taxi as a trustworthy & unique experience to the market in Q2”

The Objective is focused on <b>User Acquisition</b>. At this point in the Product Development Cycle, we want to introduce our service into the market and gain trust of the customers and show them the benefit of Flying Taxis. In the Growth Phase we can focus more on User Engagement where we can improve the awareness and incorporate lessons learned through our first service flights. Later on in the Maturity Phase we can focus more on <b>User Retention & Profitability</b> to secure revenues and improve margins. <b>Key Performance Indicators</b> will help us to measure our actions.

<p>1. Customer Acquisition Costs :arrow_right: 1/3 of the income per User (CLV) Source: https://blog.hubspot.com/service/what-does-cac-stand-for </p>
<p>2. Number of Flights/ Week :arrow_right: ~ 105 Flights each Aircraft per Week<p>	 
- Best Days and Time to operate is Friday and Saturday between 8am – 4pm as well as 5pm – 9pm	
- This makes up 24 operating hours per week which equals 1.440 minute per week</p>
- 1440 minutes divided through median duration (11min) = 131 Flights per Week</p> 
- Using Pareto Principle (80/20) we estimate that 131*80% = 105 Flights per Week are doable</p>	
<p>3. Number of Weekly active Users :arrow_right: ~ Assuming 3% Conversion rate => 7000 weekly active Users Source: https://blog.hubspot.com/marketing/conversion-rate-optimization-guide<p>
- Having two aircrafts we are aiming for 105 *2 = 210 Flights per Week in Total</p>
- Assuming that 210 Flights is the result of a 3% conversion rate we expect 6.982 weekly active Users	which makes up approx. 7000 Users</p>
 <p>4. Net Promoter Score :arrow_right: in average 10 out of 10 times the customer would most likely refer us for network effects </p>
 <p>5. Average Score of Recommendation :arrow_right: in average around 8 out of 10 times the customer had a good experience for gaining trust</p>

Having well designed KPIs we need to make sure that we collect the right data. By creating an instrumentation plan for the events, we need to collectand log, we will be able to physically measure the KPIs. The events will be stored in databases for access. First we start with KPIs & breakdown the user steps that contribute to the KPI. Next, we understand the transaction flow and build in events that should be recorded. Here is the result: 

<p>1. Customer Acquisition Costs (UserSignUp, UserRideHistory, MarketingCosts)</p><p<2. Number of Flights/ Week (AircraftPaidTakeoffs, UserOnboard, UserOffboard)</p><p>3. Number of Weekly active Users (UserLogIn, UserFlightSearch)</p><p>4. Net Promoter Score (RatingNPS)</p><p>5. Average Score of Recommendation (UserRideHistory, UserRatings)</p>

A distinction is made between Entity and Event data. 
An <b>Entity</b> is a unique object such as a customer, product, order, etc. 
Entity Attributes are the properties that describe it. Entity data is stored in a table, for every entity there is a separate table, and every table has columns that describe these entities. One row is dedicated to recording one type of each entity. The drawback of the entity data model is that the joins might get complicated and introduce latency. The advantages are the removal of data duplication and a simple, easy to understand basic structure. <b>Event</b> data mainly describes the actions performed by entities. A Few key pieces of information that are captured in event data might be the action, timestamp and state. Below you see examples how Entity and Event Data can be required:

<img src="https://user-images.githubusercontent.com/72414477/150946847-8ae491f1-6b29-4148-93fb-dc2044e911c5.png" width="200" height="200"> 



