About dataset:
Bank Marketing – donated on 13.02.2012
The data is related with direct marketing campaigns (phone calls) of a Portuguese banking institution. The classification goal is to predict if the client will subscribe a term deposit (variable y).

Additional Information
The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed. 
There are four datasets: 
1) bank-additional-full.csv with all examples (41188) and 20 inputs, ordered by date (from May 2008 to November 2010), very close to the data analyzed in [Moro et al., 2014] 
2) bank-additional.csv with 10% of the examples (4119), randomly selected from 1), and 20 inputs. 
3) bank-full.csv with all examples and 17 inputs, ordered by date (older version of this dataset with less inputs). 
4) bank.csv with 10% of the examples and 17 inputs, randomly selected from 3 (older version of this dataset with less inputs). The smallest datasets are provided to test more computationally demanding machine learning algorithms (e.g., SVM). 

The classification goal is to predict if the client will subscribe (yes/no) a term deposit (variable y).

Data dictionary

  | Variable Name | Role    | Type        | Demographic     | Description | Units | Missing values |
  |---------------|---------|-------------|-----------------|-------------|-------|----------------|
  | age           | feature | integer     | age             |             |       | no             |
  | job           | feature | categorical | occupation      | type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown') |       | no             |
  | marital       | feature | categorical | marital status  | marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed) |     | no |
  | education     | feature | categorical | education level | (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown') |    | no |	
  | default       | feature | binary      |                 | has credit in default? |      | no |      
  | balance       | feature | integer     |                 | average yearly balance |      | no |
  | housing       | feature | binary      |                 | has housing loan?      |      | no |
  | loan          | feature | binary      |                 | has personal loan?     |      | no |
  | contact       | feature | categorical |                 | contact communication type (categorical: 'cellular', 'telephone') |     | yes |
  | day_of_week   | feature | date        |                 | last contact day of the week |     | no |
  | month         | feature | date        |                 | last contact month of year (categorical: 'Jan', 'Feb', 'Mar', ..., 'Nov', 'Dec') |   | no |
  | duration      | feature | integer     |                 | last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model. |    | no |
  | campaign      | feature | integer     |                 | number of contacts performed during this campaign and for this client (numeric, includes last contact) |    | no |
  | pdays         | feature | integer     |                 | number of days that passed by after the client was last contacted from a previous campaign (numeric; -1 means client was not previously contacted) |   | no |
  | previous      | feature | integer     |                 | number of contacts performed before this campaign and for this client |   | no |
  | poutcome      | feature | categorical |                 | outcome of the previous marketing campaign (categorical: 'failure', 'nonexistent', 'success') |    | yes |
  | y             | target  | binary      |                 | has the client subscribed to a term deposit? |    | no |
