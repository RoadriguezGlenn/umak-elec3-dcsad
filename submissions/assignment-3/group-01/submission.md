# Assignment 3 Submission

## About us

* Group number: 1
* Section: IV-DCSAD
* Lab 3 client: A school canteen ordering app

## Three estimates

Asia Pacific (Singapore), MySQL, OnDemand, 100% utilization, RDS Proxy No, Database Insights No.

| Option | Instance | Deployment | Nodes | Storage | Total monthly cost (USD) |
| --- | --- | --- | --- | --- | --- |
| A. Small and cheap | db.t4g.micro | Single-AZ | 1 | 20 GB gp3 | 21.01 |
| B. High availability | db.t4g.micro | Multi-AZ | 1 | 20 GB gp3 | 42.75 |
| C. Read scaling | db.t4g.micro | Single-AZ | 2 | 20 GB gp3 | 42.02 |

Share link of our estimate: https://calculator.aws/#/estimate?id=9ffc44b7c9e846fbee1584bf0e6fec004eb2325

## Recommendation

Option A (Small and cheap) is the best fit for the school canteen ordering app at $21.01 per month. The app's users are students and school staff ordering meals primarily during predictable recess and lunch breaks on school days, rather than generating continuous 24/7 global traffic. The cost of downtime is low because a brief database interruption only delays digital pre-orders temporarily while the canteen can still accept cash or walk-up counter orders without permanent financial or safety loss. Its read load is light and bursty around meal windows, which a single `db.t4g.micro` instance can easily serve without needing a separate read replica. Choosing Option A keeps monthly hosting affordable for a school operation while avoiding the doubled cost of Multi-AZ failover or multi-node read scaling.

## Question

Why is a Multi-AZ standby not the same as a read replica?

A Multi-AZ standby is a synchronous, passive replica maintained strictly for high availability and automatic failover, so applications cannot connect to it to run read queries during normal operation. In contrast, a read replica is an asynchronous, active database instance with its own endpoint that offloads read-heavy traffic from the primary database, and it does not provide automatic failover for writes.

## Contribution

| GitHub username | What this groupmate did |
| --- | --- |
| <glenn-github-username> | Configured the three AWS Pricing Calculator RDS estimates, verified the share link, and drafted the client recommendation. |
| <jhone-github-username> | Reviewed the AWS RDS configuration parameters, storage calculations, and Multi-AZ vs. read replica comparison. |
| <jean-lee-github-username> | Verified the Lab 3 client requirements, checked the submission formatting, and prepared the repository pull request. |
