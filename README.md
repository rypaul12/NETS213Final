# Surprisingly Popular Candidate
### 

Using Crowdsourcing to Predict the Indian General Election

## Motivation

Election prediction faces many challenges in coming years as phone response rates decline and the cost of conducting large polls increases. Traditional polls have also failed to predict recent major votes, including the US 2016 presidential election and the 2016 Brexit vote. The surprisingly popular option algorithm discussed in lecture offers a unique opportunity to harness the power of the crowd to solve for this declining response rate and rising costs by using large numbers of cheap workers. We will test the algorithms effectiveness on Indian General Election taking place in April 11 - May 19, 2019

**Note:** Because the election takes place April 11 our project is fairly front-loaded so that we can post the HIT with plenty of time to get responses before the election begins. Additionally, while we can make predictions, election results are not released until May 23, we will not be able to analyze the effectiveness of our model. All of this has been approved by CCB.


## Project Components

 1. **Meet with Domain Expert** (1 point)
In order to better understand the idiosyncratic indian general election system we will meet with a faculty member from the South Asian Studies Department.
*Due Date: April, 3*
    

2.  **Find Raw Data** (2 pts)
    Based on meeting with the domain expert we will find the correct data for the election. This will likely include district names, state names, election dates, candidate names, party names, alliance names, or some subset of these that can be displayed in the HIT.
    *Due Date*: April, 4
    
3.  **Clean Raw Data** (1 point)
    Convert data into a format useable for HIT.
    *Due Date*: April, 4
    
4.  **Build and Post HIT** (4 pts)
    Our HIT will ask questions related to the upcoming election which we can use in our Surprisingly Popular algorithm. Will also ask questions to determine which district the worker is in and a quality control question. Screenshots of HIT in GIT.
*Due Date*: April, 4
    
5. **Perform Quality Control and Cleaning of Results** (2 pts)
    Filter out workers answers who did not pass our quality control tests
    
6.  **Aggregation of Results** (4 pts)
     Perform aggregation over results and execute Surprisingly Popular algorithm to get predictions


## Data

1. **Sample input/output from your QC module**: 

**Input**
The input is the input gotten from the HIT. We get True/False values for if they voted for NDP, UPA, or other. Additionally, we get their confidence (on a scale from 1-100) on their candidate winning. We also get their thoughts on what percent of people will vote for NDP, UPA, and other respectively. 

**Output**
The output is nearly the same, but we filter out any HITS that fail our preliminary question. The question is "who is the current prime minister of India."

2. **Sample input/output from your aggregation module**: 
**Input**
The input is the input gotten from QC model. All HITS that pass the question.

**Output**
The output is grouped by state, and shows per state the percentage breakdown of turker's personal votes, the average confidence in vote per state, and the average percentage they think other people in their state will vote for.


## Code
The **quality_control** function handles quality control and filtering out bad HITS by checking if the quality control question is correct.

The **aggregation** function handles the aggregation features, and getting the averages of who is voting for what alliance per state.
