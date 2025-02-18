# kaggle_HomeCreditDefaultRisk
Participation in the kaggle competition Home Credit Default Risk, 
see [competition details](https://www.kaggle.com/c/home-credit-default-risk#description)

## DESCRIPTION OF PROBLEM TO SOLVE
Many people struggle to get loans due to insufficient or non-existent 
credit histories. And, unfortunately, this population is often taken 
advantage of by untrustworthy lenders.
Home Credit strives to broaden financial inclusion for the unbanked 
population by providing a positive and safe borrowing experience. 
In order to make sure this underserved population has a positive 
loan experience, Home Credit makes use of a variety of alternative 
data--including telco and transactional information--to predict their 
clients' repayment abilities.
While Home Credit is currently using various statistical and machine 
learning methods to make these predictions, they're challenging Kagglers 
to help them unlock the full potential of their data. 
Doing so will ensure that clients capable of repayment are not rejected 
and that loans are given with a principal, maturity, and repayment calendar 
that will empower their clients to be successful.

## DESCRIPTION OF EVALUATION CRITERION AND SUBMISSION FILE

Submissions are evaluated on area under the ROC curve between the 
predicted probability and the observed target.
Submission File: For each SK_ID_CURR in the test set, you must predict a 
probability for the TARGET variable. The file should contain a header and 
have the following format:

SK_ID_CURR,TARGET
100001,0.1
100005,0.9
100013,0.2
etc.

## DESCRIPTION OF DATA TABLES
-	application_{train|test}.csv
    -	This is the main table, broken into two files for Train (with TARGET) and Test (without TARGET).
    -   Static data for all applications. One row represents one loan in our data sample.
- 	bureau.csv
    - All client's previous credits provided by other financial institutions that were reported to Credit Bureau (for clients who have a loan in our sample).
    - For every loan in our sample, there are as many rows as number of credits the client had in Credit Bureau before the application date.
-	bureau_balance.csv
    -	Monthly balances of previous credits in Credit Bureau.
    -	This table has one row for each month of history of every previous credit reported to Credit Bureau – i.e the table has (#loans in sample * # of relative previous credits * # of months where we have some history observable for the previous credits) rows.
-	POS_CASH_balance.csv
    -	Monthly balance snapshots of previous POS (point of sales) and cash loans that the applicant had with Home Credit.
    -	This table has one row for each month of history of every previous credit in Home Credit (consumer credit and cash loans) related to loans in our sample – i.e. the table has (#loans in sample * # of relative previous credits * # of months in which we have some history observable for the previous credits) rows.
-	credit_card_balance.csv
    -	Monthly balance snapshots of previous credit cards that the applicant has with Home Credit.
    -	This table has one row for each month of history of every previous credit in Home Credit (consumer credit and cash loans) related to loans in our sample – i.e. the table has (#loans in sample * # of relative previous credit cards * # of months where we have some history observable for the previous credit card) rows.
-	previous_application.csv
    -	All previous applications for Home Credit loans of clients who have loans in our sample.
    -	There is one row for each previous application related to loans in our data sample.
-	installments_payments.csv
    -	Repayment history for the previously disbursed credits in Home Credit related to the loans in our sample.
    -	There is a) one row for every payment that was made plus b) one row each for missed payment.
    -	One row is equivalent to one payment of one installment OR one installment corresponding to one payment of one previous Home Credit credit related to loans in our sample.
-	HomeCredit_columns_description.csv
    -	This file contains descriptions for the columns in the various data files.


![dataset connections]()https://storage.googleapis.com/kaggle-media/competitions/home-credit/home_credit.png)
