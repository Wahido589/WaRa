# Applying iterative design principles to the live product

The introduction went well and now we would like improve our product continously. 
Below you will find mostly excerpts of Tableau visualizations. You can find the corresponding workbook on my [Tableau Public](https://public.tableau.com/views/4_iterative_design_principles/Dashboard2?:language=de-DE&publish=yes&:display_count=n&:origin=viz_share_link) account.

First we look how our product is performing. We have designed KPI in chapter 1 which we use to measure our success. There are different layers which we could check:
 - KPI on business level (depending on business model, e.g. # of purchases, renewal of subscriptions, paying customer satisfaction)
 - KPI on customer journey level 
   - Acquisition (# of visitors/day)
   - Activation (# of account creations)
   - Retention (average customer lifespan)
   - Revenue (Customer Lifetime Value)
   - Referral (#new customers through referral)
- KPI on feature level
   - Acquisition (Who saw the features?)
   - Activation (Who used the feature?)
   - Retention (How often did a user return?)
   - Revenue (How much revenue through the feature?)
   - collected customer data provides further insights like: 
     - who used or used not the new feature
     - when and how a user use the new feature
 
 <p>In this chapter we will focus on <b>KPI on feature level</b>.</p>
 
<h1>Funnel Analysis</h1>
A funnel analysis is a good way to look at the performance on feature level. You can see the dropoff rates for each feature and investigate when users are stop experiencing our product. In our scenarion we have already run a multivariate test experiment, where we test new features to improve our product. Lets see hot that worked out. 
 
<h3> Impact on the conversion rate of users booking a flight (out of all users opening the app)</h3>

<img src="https://user-images.githubusercontent.com/72414477/151531086-e550c54f-f7bf-404e-baf3-35c742e30769.PNG" width="350" height="250">

<h3> Impact on the conversion rate of users booking a flight pear each group (out of all users opening the app)</h3>

<img src="https://user-images.githubusercontent.com/72414477/151531424-b71994e5-4f25-42bf-8540-3ecd0b4cd0cb.png" width="400" height="200">
Before we talk about the meaningfulness of the experiment we should check if the results are statistical significant. Doing this, we make sure the likelihood that the results are du to random chance is below a certain threshold (p value). In order to achieve statistically significant results, it is important to have a large enough group of participants in our experiment. The number of participants needed for the experiment to produce statistically significant results is called sample size. 

We will follow this checklist:
1. Set Null Hypothesis: “Results of the Control State are not different than the experimental states”
2. Set Alternative Hypothesis:”Experimental States are significantly different than the control state”
3. Confidence Threshold => 95%
   - p value would be 0.05, but we have a two-tailed t-test, therefore p value = 0.025






  
