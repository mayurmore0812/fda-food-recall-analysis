# FDA Food Recall Analysis and Interactive Review

> **Repository status:** README-only preview. The analytical notebook and interactive edition have not been published here yet.

## Project question

What can a historical food-enforcement dataset reveal about recall workload, recorded severity, recurring issue categories, and communication patterns? 

This academic case study uses an FDA-facing management scenario.

## Data and approach

The reviewed data snapshot contains **22,840 product records** linked to **5,875 distinct recall events**, with report dates from June 2012 through August 2022. I Balance a master table with overlapping category tables, kept product-record and event counts separate, and developed ten management-focused views. A second edition adds Plotly filters and a geographic exploration view.

## Interpretation

The figures describe a historical snapshot, not today's recall status or the risk of a food product. Counts of recalling firms by location do not show where consumers were exposed. Category labels can overlap, and some annual comparisons exclude partial years.

## Planned release

I plan to publish a cleaned analytical notebook, a reviewed interactive edition or static demo, data definitions, provenance notes, and a small preview. Embedded notebook and HTML content will be checked for private data and redistribution rights before upload.

**Tools used:** Python, pandas, Plotly, matplotlib, data reconciliation.

**Code, data, and the interactive demo are not yet available in this repository.**
