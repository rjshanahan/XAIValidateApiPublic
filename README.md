## Welcome to XAI Validate  
    
XAI Validate is powered by [Tic:Toc](https://tictoc.ai), a technology solutions company providing innovative products to make financial services processes faster, smarter and simpler.
    
    
XAI Validate solves for digital financial data validation using Explainable Artificial Intelligence (XAI) models to distil and render the customers’ financial data into an application decision summary. It is powered by a set of sophisticated normalisation, categorisation and assessment models, supported by an intuitive user interface that allows assessors to interact with and understand your customers' financial data. This will dramatically reduce the time required for assessment and to increase conversion, while ensuring process assurance and credit quality. We prove all technology against our direct to consumer home loans business, [Tic:Toc Home Loans](https://tictoc.com.au/).
     
If you're a lender you can use XAI Validate in two ways:
- **Detect and Position** (Actuals only): instantly identify income, expenses, assets and liabilities, behavioural and risk insights.
- **Verify and Decision** (Stated vs Actuals): ingest and verify customers’ declared financials against the actual financial position identified in the data. This also allows you to configure your credit policy automating responsible lending assessment decisions.      
      
XAI Validate supports a range of data sources including:
- popular data aggregators
- connect your own data
- Consumer Data Right support (coming soon!)
          
## Getting Started  
    
The XAI Validate API provides a way to seamlessly integrate assessment of financial poistion into your workflow. The table below provides a summary of endpoints, which allow you to get "data in" and then "data out". You can use the [XAI Validate user interface](https://app.tictoc.ai) at any time to interact with your data and the automated assessment of financial position.
      
You'll need the following to start developing:
- sign-up for XAI Validate. [Contact us](mailto:enterprise@tictoc.ai) to discuss the right product and access to our `sandbox`
- your client credentials for the XAI Validate user interface and API. These will provided to you by Tic:Toc, and must be stored securely
- you're then ready to start developing against our test environment using the endpoints below. 
      
| Endpoint Name| Description |
|-----|-----|
| [`/application/create`](#/financialvalidation/application/create) | Create an application linking your applicants, and their external data aggregator reference identifiers.  |
| [`/application/manage`](#/financialvalidation/application/manage) | Update an existing application including adding "declared/stated" financials, updating applicant details or adding new xternal data aggregator reference identifiers.  |
| [`/provideaccounts`](#/financialvalidation/provideaccounts) | Connect your customers' account and transaction data against an existing application and applicant. This is ideal if you've sourced your own raw transaction data from core systems or through Open Banking.  |
| [`/application/getstatus`](#/application/getstatus) |  Monitor the progress of automated financial assessment.  |
| [`/result/getsummary`](#/result/getsummary)| Retrieve the results of automated financial assessment. The endpoint will surface automated assessments against your configured credit policy (where relevant), and validation figures for income, expenses, assets and liabilities. |
| [`/serviceability/getserviceability`](#/serviceability/getserviceability)| Calculate serviceability for your application including income, expense, debt, borrowing amount and ratios. |
| [`/token`](#/token) | XAI Validate uses OAuth2 authentication. Every time you call these endpoints you'll need to ensure you have a valid token.  |
      
      
## Data Model  
      
When you interact with the XAI Validate user interface and APIs you'll notice there's a clear structure to the data. We've designed the XAI Validate data model to be optimised for automating assessment of financial position. The data hierarchy is:
- **application**: this is the structure that holds all other elements and represents a point-in-time product application from your customer
- **applicants**: an application can have one or more applicants (currently limited to two). Applicants can belong to multiple applications, e.g. a customer applying for a credit card and a home loan would exist in two applications
- **households**: your applicants belong to households. For convenience we will assign applicants to a single, default household at the start of application
- **accounts**: applicants own accounts, which can be held individually or jointly with the other  applicant on the application
- **transactions**: these are the credits and debits against each account. Transactions are enriched with attributes such as categories, high risk flags and expense management. 
      
## References
    
Here are a few resources to help you on your way:
- **User guide**: you can access this through the XAI Validate application. Simply login and navigate to your name in the top right.
- **SDKs**: coming soon
- **Postman 'Collection'**: download this collection to help you interact with the XAI Validate APIs using Postman (coming soon).
