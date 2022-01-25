Assuming we have also Operations going on in Germany. We have already launched Drone Taxis there and are looking forward to improve our Product. Therefore we need some more Data and would like to collect it through our App and Desktop Version. Specifically we need Behavioral Data from our Users to be able to investigate if our Multivariate Testing Approach gives insights on how to decrease dropoff rates for certain User Segments. 

There are some steps we need to check from a Data Protection point of view. 

<h2>1. Do we need to consider GDPR?</h2> 
Yes, according to Art 3 (1) GDPR. We do business in the EU and deal with data of EU customers.  

<h2>2. What exactly do we need to consider when GDPR does apply?</h2>
<h3>a. Lawfulness of Processing</h3>
We will meet the conditions according to Art 6 (1) lit. a, b GDPR. The User will give a consent through the acknowledgment of the Terms of Service while signing up. We will work with Cookies to gather Data and therefore the User needs to confirm the usage as well. We will do this via Cookie Banner.
 
<h3>b. Principles relating to processing of personal data</h3>
We need to keep an eye on the principles according to Art 5 GDPR:
Lawfulness, fairness and transparency/ Purpose limitation/ Data minimisation/ Accuracy/ Storage limitation/ Accountabilty

<h3>c. Security of processing</h3> 
According to Art 32 GDPR we need to have appropriate technical and organisational measures in place to ensure a certain level of security. To understand what a certain level of security means we can look into Art 32 (2) GDPR. Our measures must cover the processing risks, in particular accidental or unlawful destruction, loss, alteration, unauthorised disclosure of, or access to personal data transmitted, stored or otherwise processed. 
To address these risks our goals are Confidentiality, Integrity, Availability and Resilience of processing systems and services as well as the ability to Restore the Availability and Access to personal data in a timely manner in the event of a physical or technical incident. Pseudonymisation and encryption of personald data support our goals. 
A regular audit for evaluating the effectiveness of technical and organisational measures should be conducted to ensure that the level of security is sufficient.

<h3>d. Automated individual decision-making, including profiling</h3>
According to Art 22 (1) GDPR our customers shall have the right not to be subject to a decision based solely on automated processing, including profiling, which produces legal effects concerning him or her or similarly significantly affects him or her. We do meet the definition of profiling (Art 4 (4) GDPR). 
Art 22 (2) GDPR shows us when profiling is allowed. We will ask for explicit consent (lit. b) or we will mention that this profiling is necessary for entering into a contract with us (e.g. Terms of Service, see lit. a).


<h2>3. Anything else what could give us some Headaches?</h2>
 <h3>e. Tools for gathering data</h3>As we want to use Cookies to collect the data, we need to consider the Telecommunications and Telemedia Data Protection Act (German Law, aka "TTDSG"), because of § 1 (3) TTDSG. It is the same as above in step 1. It is derived from Art 5 (3) of the European ePrivacy Directive. This Article has been transposed into German Law as of 1/12/2021.
Looking into §25 TTDSG, we understand, that we need explicit consent of our Users to implement a Cookie on their end device. As mentioned above in 2a., we will take care of this by using a Cookie Banner. How an explicit consent must look like, is described in Art 7 & 8 GDPR.

<h3>f. Dealing with Data Processors</h3>While our Data Pipeline is designed on the basis of Amazon Web Services we need to consider Art 28 GDPR which is about Data Processors. We need to make sure that the Data Processor has sufficient technical and organisational measures in place. We do this by having a contract with AWS which will be enriched by standard contractual clauses (Art 28 (6) GDPR).

<h3>g. Being able to fulfill the rights of our customers</h3> To meet the the Principles (see 2b.) Lawfulness, fairness and transparency, we should ensure that we are able to meet the expectations set in Art 12 GDPR (Transparent information, communication and modalities for the excercise of the rights of the 'customer'). In addition to the information that needs to be provided to the customer (Art 13 & 14 GDPR) we need to make sure to be able to fulfill the rights of the customers according to Art 15-22 & 77 GDPR.

<h3>h. Conducting an Impact Assessment</h3> Profiling collects a lot of personal data which is specifically adressed by GDPR. A Data Protection Impact Assessement (Art 35 GDPR) is necessary when one of the aspects in Paragraph 4 or one requirement in Paragraph 3 is met. For Paragraph 4 we need to check with the supervisory authority if our planned activities are on their black list. If it is not on the black list, we still meet the requirement in Paragraph 3, lit. a (Profiling).  We could run down the specifics of the impact assessment in Art 35 GDPR, but we can also make use of the open-source PIA Tool (https://github.com/LINCnil/pia-back), which is provided by the french supervisory authority.

The PIA Tool offers a workflow to ensure the Data Protection Impact Assessement is properly done. Everything that was mentioned above will be asked while you go through the workflow. I have attached some of Screens out of the PIA Tool (see enclosed file PIA_Tool_example.pdf). At the end of the evaluation process we have a Risk Overview (see enclosed file risk_overview.png). In a perfect world, the Process Owner is responsible to do the Impact Assessment and the Data Privacy Officer ("DPO") is reviewing. There are different scenarios when a company must have a <b>DPO</b>. You can have a look into Art 37 (1) GDPR in conjunction with §38 (1) German Federal Data Protection Act ("BDSG"). According to BDSG we need to have a designated DPO if we do Data Protection Impact Assessements.


As you see there is a bit that we need to consider in our use case. There are touchpoints with areas where I used to work in previously. I would like to mention them quickly here. 

<h2>4. Areas of Overlap</h2>
From a DPO perspective we generally want to follow the Principles relating to processing of personal data (Art 5 GDPR). Meeting the requirements for Lawfulness of Processing (Art 6 GDPR) and for Security of processing (Art 32 GDPR) will materially help us with that. Security of processing is sufficiently covered if we address the risk in Art 32 (2) GDPR appropriately. This risks can be aggregated to 3 main risks: Illegitimate access to data, Unwanted modification of data & data disappearance. When we look at the Risk Overview, we find the Risk on the right side.

<img src="https://user-images.githubusercontent.com/72414477/150956273-5f30091f-c187-4c73-b577-e02c1f6a4858.png" width="750" height="400"> 

If we go to the top left we see the Potential Damage which can effect us if the risk occurs. Reasons why the risk could occur can be found under
Threats. The Sources of the Threats are also listed in the overview. Ultimately the Threats needs to be covered through measures. 
The measures are derived from Art 32 (1) GDPR:
 
 - Confidentiality, Integrity, Availability and Resilience of processing systems and services 
 - ability to Restore the Availability and Access to personal data in a timely manner in the event of a physical or technical incident
 - Pseudonymisation and encryption of personal data

A big part of my work was to identify relevant IT applications and test on a regular basis the effectivness of technical and organisational measures. Mostly I was concerned about the Confidentiality & Integrity: 
- making sure that the Change Mgmt Process is working so that applications are working reliably and making sure that Patchmgmt is working on database level (the <b>ITIL</b> Framework helps to structure IT processes)
- auditing Logical Access to IT applications and databases which deals with Identity and Access Mgmt (the <b>ISO 2700x</b> Framework provides security technique approaches), this includes checking physical access to data centers & the disaster recovery process (e.g. uninterruptable power supply, emergency generators) 
- while Availability (e.g. working backup strategy) was part of my work, Resilience of processing systems and services (e.g. usage of Load Balancers within the Network) has not been a focus. 

Going through this steps, we are able to decide whether an IT system is reliable or not. In the context of financial reporting that impacts the reliability of information that is gathered through an IT system. Which implications that has on financials will be explained by me in another use case. 
