# Linux Authentication Log Investigation with Splunk

## Project Overview
This project investigates repeated SSH authentication failures using Splunk Enterprise and a public Linux sample log dataset.

The goal was to identify suspicious authentication activity, examine source IP values, and determine which user accounts were targeted.

## Tools and Dataset
- Splunk Enterprise
- Public Linux_2k sample log dataset
- Search Processing Language (SPL)

## Investigation Findings
- The search identified repeated SSH authentication failure events.
- The account `root` appeared frequently as a target.
- The highest-count source shown was `150.183.249.110`, associated with 80 events after exact raw-event deduplication.
- The dataset had been uploaded twice, resulting in 980 matching events before deduplication and 490 events after `dedup _raw`.
- The deduplicated summary showed 47 source-IP values.

## Analysis and Limitations
The findings are consistent with suspicious failed SSH authentication activity, potentially password-guessing behavior.

The evidence does not confirm a successful login or system compromise. The source IP values are from the public sample dataset and should not be treated as activity against my own computer or network.

Exact raw-text deduplication was used to account for the duplicate upload. This reduces duplicate records in the search results but does not remove duplicated data from the Splunk index.

## Reports
- [Download the Word investigation report](Linux_Authentication_Log_Investigation_Report.docx)
- [View the PDF investigation report](Linux_Authentication_Log_Investigation_Report.pdf)

## Disclaimer
This project was conducted for educational and defensive cybersecurity learning using public sample logs.
