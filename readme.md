# (Dataset Exploration Title)
## by (your name here)


## Dataset

Prosper Loan Data (prosperloanData.csv) represents personal loans requested through Prosper's peer to peer loan servicing network. Each row represents a loan with information on the listing request, loan details, and borrower's credit worthiness. After assessing the data I found that LoanStatus is the variable of most interest as it will help us to determine if loans go bad (i.e. Default, Miss a Payment, Chargedoff, or Cancelled)

Supporting variables include BorrowerRate, EstimatedReturn, ProsperRating, ProsperScore, ListingCategory, LoanOriginalAmount, LoanOriginationDate, CreditScoreRangeLower, CreditScoreRangeUpper, and Term.

To analyze the data I first needed to clean some of the variables. Below are notes captured during the assessment stage of data wrangling.

    ProsperRating has 29084 missing values
    EstimatedReturn has 29084 missing values 
    Credit Scores are missing on 591 loans.
    ProsperRating and ListingCategory column names contain additional info (Alpha) and (numeric)
    ListingCategory values not descriptive
    ProsperRating will need to be combined with CreditGrade to fill missing data from before July 2009.
    Create CreditScoreAvg metric as an average of lower and upper Credit Score ranges
    LoanStatus contains too many categories that should be combined into favorable and unfavorable
    

After cleaning I moved on to visualizing the dataset for analysis based on the research question: What loan or borrower characteristics contribute to unfavorable loan outcomes (LoanStatus: Cancelled, Chargedoff, Defaulted, PastDue)


## Summary of Findings

BorrowerRates appear similar between good and bad loans.

Estimated Returns are similar between good and bad loans. EstimatedReturn data is very spread with many outliers in the boxplot.

*Estimated Returns and loan amounts are grouped very tightly between 5-15% return and $2500-12500. Iterestingly, lower loan amount resulted in more cases of negative return. This may indicate high value loans are less likely to default as the borrowers are typically more qualified.

\*Unfavorable loans are most common in D and HR grade, while C grade dominates loans in good standing. Overall there is a higher proportion of good standing loans in higher grades. This makes sense as higher ratings correspond with more qualified borrowers, however there were loans of all grades, even AA, that ended in unfavorable outcomes.

Debt Consolidation dominated the number of loans taken out, however Average Loan Amounts for Debt Consolidation are much closer to the other Categories.

\*The proportion of bad to good loans is varies from ~10-25% depending on loan category. Green Loans and Baby&Adoption categories lead in proportion of loans going bad.

Lower ProsperScore loans are usually lower dollar amount. There is a slight positive correlation between the Score and OriginalLoanAmount

\*Bad loans follow the same distribution and have almost identical proportions amongst all years of data. I assumed there would be more unfavorable loans during economic crisis. This may be because Prosper was more stringent about loans or we need to break down the timeline further.

Credit Scores are similar between good and bad loans. This is suprising because Credit Score is often associated as connected to qualification of paying a loan.

Loan status seems to effect all 3 loan terms about the same

Credit Scores are lowest in E rated, good loans, and highest in High Risk rated good loans. Bad loans are within a few points of their good loan counterparts in each rating category.

Green Loans that turn unfavorable have the highest average Credit Score. Green loans represent the highest proportion of bad loans in listing categories. It seems credit score's have little to do with a loan turning unfavorable

EstimatedReturn & BorrowerRate, and ProsperScore & BorrowerRate are highly correlated however, they do not have have correlation together with LoanStatus



## Key Insights for Presentation


Over each of the years of loan data, proportion of loans in bad status remained constant. I assumed loans durring the 2008 financial crisis would result in higher delinquency proportions. I will continue to investigate for the presentation using a finer timetable of loan quarter year. To make this visualization stand out I will overlay a defined red line of proportions on top of the loan counts for good and bad loans for each quarter year. I will then place a text label for the top and bottom loan proportions right around the financial crash quarters.


There is a high proportion of good standing loans in higher grades and high proportion of bad loans in low grades. This makes sense as higher ratings correspond with more qualified borrowers, however there were loans of all grades, even AA, that ended in unfavorable outcomes. To emphasize this plot I will plot both proportions of LoanStatus on a single axis to show the tradeoffs at each loan rating.

Green Loans have a high proportion of delinquent loans. I will showcase this plot using a barplot. I will add color to the barplot indicating average credit score to showcase there is little correlation between credit scores and delinquency. Green loans even have the highest credit score average of all delinquent loan categories. To show this plot I will use a barplot ordered by loan category and color the bars by credit score.









