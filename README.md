# DSND Capstone Project (The final project in the Data Scientist NanoDegree)
A quick analysis review of simulated data provided by Starbucks to identify which groups of people are most responsive to each type of offer sent by Starbucks rewards app.

## by Michael F. H. Georgy

## Motivation
Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free)

A. In a BOGO offer, a user needs to spend a certain amount to get a reward equal to that threshold amount.

B. In a discount, a user gains a reward equal to a fraction of the amount spent.

C. In an informational offer, there is no reward, but neither is there a requisite amount that the user is expected to spend. Offers can be delivered via multiple channels.

The basic task is to use the data to identify which groups of people are most responsive to each type of offer.

I have decided to develop a set of heuristics to help determine what offer should be sent to each customer through the following steps:

1- Combine transaction, demographic and offer data after necessary cleaning.

2- Find correlation between income and purchase.

3- Determine which demographic group pays more in purchases.

4- Determine which demographic groups respond best to which offer type.

You can find the link to my original work in this [Github repo](https://github.com/michael-fawzy/DSND-Capstone).

## Libraries
Just the regular libraries:

1. pandas
2. numpy
3. math
4. json
5. matplotlib.pyplot
6. import seaborn

## Data Understanding and Preparation
The data set used contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. The program used to create the data simulates how people make purchasing decisions and how those decisions are influenced by promotional offers.

The data is contained in three files that can be found in the project GitHub repository mentioned above:

A-	portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)

B- 	profile.json - demographic data for each customer

C-  transcript.json - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

- A. Portfolio.json	
Offers sent during 30-day test period (10 offers x 6 fields)

    -	id (string) - offer id
    
    -	offer_type (string) - type of offer ie BOGO, discount, informational (an advertisement for a drink).
    
    -	difficulty (int) - minimum money required to be spent to complete an offer and receive reward.
    
    -	reward (int) - reward given for completing an offer (money awarded for the amount spent).
    
    -	duration (int) - time for offer to be open, in days.
    
    -	channels (list of strings) - web, email, mobile, social.
 
- B. Profile.json
Rewards program users (17000 users x 5 fields)

    -	age (int) - age of the customer. Missing value encoded as 118
    
    -	became_member_on (int) - date when customer created an app account (date format YYYYMMDD)
    
    -	gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
    
    -	id (str) - customer id
    
    -	income (float) - customer's income
 
- C. Transcript.json
Event log (306648 events x 4 fields)
    -	event (str) - record description (ie transaction, offer received, offer viewed, offer completed).
    -	person (str) - customer id
    -	time (int) - time in hours since start of test. The data begins at time t=0
    -	value - (dict of strings) - different values depending on event type:
        -	offer id: (string/hash) not associated with any "transaction"
        -	amount: (numeric) money spent in "transaction"
        -	reward: (numeric) money gained from "offer completed"



## Summary of Findings

- According to the problem statement, the basic task is to use the data to identify which groups of people are most responsive to each type of offer. After this analysis, I can now say that all customers are more responsive to discount offers than they are to bogo offers although more females (48.5%) responded to bogo offers than males (45.6%).
- Since there is a direct correlation between customer income and the amount they spend, we can safely assume that Starbucks should focus more on targeting customers of higher income as they tend to pay more.
- An interesting fact, however, that requires more research, is why there is a group of people whose purchase is not directly correlated to their income and keep a fixed payment amount.
- On a side note, it was also interesting to find that some customers were 100 years old, and even more, who not only still make purchases from Starbucks, but they also use a mobile app. to do this.! Wow! Now that's what I call adaptation to technology..
- **As a final conclusive result, the company should focus more on sending discount offers to higher income customers of all genders in the age group 59-64 since this group tends to pay more and complete more offers. However the data still hides a lot under the hat, and the possibilities look endless!**


You can find more detailed explanation with plots in this [Medium post](https://michaelfawzy.medium.com/offers-offers-offers-from-starbucks-88707094a5fa)

## Files

1. Data sets.rar: A rar file containing the dataset files mentioned above, since some files are larger than 25 Mb.
2. Starbucks_Capstone_notebook.ipynb: This is the main file where all the work was done.
3. Starbucks_Capstone_notebook.html: The HTML version of the previous file.
4. Readme file: A file to provide project description and summary of the results.
5. Blog Poston Medium.docx: An MS Word file used to write the post before publishing it on Medium.
6. pic1.png & pic2.png: Photos used for illustration inside the Jupyter notebook file.


