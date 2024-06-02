# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

I used MYSQL workbench to make the ERD. I found it more intuitive than making tables in Dawio or lucidchart.




## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._


Type 1 - Overwriting Address changes
Type 2 - Retain address chjanges.

Bonus: Are there privacy implications to this, why or why not?
```
Your answer...
```
Yes there are massive privacy implications here . 

Type 1 changes, which overwrite existing data with new data, offer significant privacy advantages by minimizing the amount of personal information stored. 
This approach reduces the risk of data breaches, as only current data is held, and simplifies compliance with privacy regulations like GDPR or CCPA. 
Managing data subject requests is more straightforward since only the latest data needs to be reviewed or deleted, enhancing overall data security and privacy. 
However, the lack of historical data can limit the ability to perform detailed analyses that rely on tracking changes over time, which might be necessary for certain business operations and workforce management.

In contrast, Type 2 changes retain historical data by adding new records for each update, which provides a comprehensive view of a customer's history. While this approach offers valuable insights for personalized marketing,
customer support, and fraud detection, The risk of data breaches is higher because more sensitive information is available, and managing compliance 
becomes more complex as all historical records must be reviewed and possibly deleted upon request.

I'd still argue that maintaining historical data is a bonus, not a flaw. if malicious actors needed access to customer addresses, they'd get it elsewhere. Not visit the local bookstore. The only worrying possibility is if the employees with 
access to the data are bad actors themselves.


## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
Your answer...
```
Well... apart from the given ERD being large and complex, with many cardinalities and relationships. I noticed the following differences.

1. The AdventureWorks schema is highly normalized and designed to handle a complex, enterprise-level database with many tables and relationships. It includes detailed tables for products, inventory, suppliers, and various sales channels. 
My bookstore ERD is simplified to suit a local bookstore and focuses on essential business operations without the extensive granularity seen in AdventureWorks.

2. The AdventureWorks schema has a few central tables with a lot of foreign-key references ( like the person table for instance ) . I'd argue my ERD is a little less centralized, but it's way less ubiquitous.

Understanding such a complex ERD can be tedious, I'd use Graph DBs when I can here.






# Criteria

[Assignment Rubric](./assignment_rubric.md)	

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `June 1, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-3-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
