# Background Information & Decision Log

When developing solutions we prefer Agile and Lean methods over legacy waterfall ways of thinking. As such it is important to move the focus from detailed up-front design to a living document that captures the important discussions and decisions that contain the real value and which influence what we build (or omit).

This document is intended as a place to record such information. As a starting point it lists a number of key questions and considerations that should be evaluated for all data focussed solutions however feel free to suplement these with your own points.

This document should be kept in your projects GitHub repository and so will contain historical changes. If important feel free to tag updates and changes with name / date directly in the document if such a history is useful to have visable without searching through git commits.

This document is split into 2 sections:

* Background Information - Relevant facts and information upon which to base decisions.
* Decision Log - Discussion points and decisions that influence what we build.

## Background Information

Relevant facts and information upon which to base decisions that impact the design of the data flow. All solutions need to consider 3 perspectives - the consumer, the enterprise and relevant backend systems. All new data flows should also adhere to recommendations defined in the Enterprise Data Architecture and other governing documentation.

*[Please include any relevant reasoning or assumptions behind answers.]*

### Consumer

**Provide links to documents containing relevant consumer requirements**

*[To ensure there is no misalignment of expectations it is important to understand what requirements consumers of the data might have. There is [a template](https://github.com/equinor/data-engineering/blob/master/docs/Consumer%20Requirements.md) for capturing these requirements on the [data engineering git repository](https://github.com/equinor/data-engineering).]*

### Enterprise

**Who are the potential consumers of this data and for what purposes might it be used**

*[Potential user groups, business areas, systems, ...*

**Has any necessary LRA been performed for making the data available and if necessary for usage, and what is the reference?**

*[See the [legal risk assessment service](https://equinor.service-now.com/selfservice?id=kb_article&sys_id=c5acb55fdb610c94c293199f299619dd)]. In this service you can also ask questions about possible existing LRA's that might be in place*

**What Data Area does the data belong to?**

*[[Data areas](https://eita.equinor.com/companyea/?oid=bd7e452f-a8be-43f7-86fa-9513b8ce95a9) form the basis for naming, ownership and more. If you are unsure what data area something belongs to then contact someone from the EDM team!]*

Level 1: Project\
Level 2: Project Schedule

**Describe the existing lineage of data?**

*[Individual fields might come from different sources so there might be multiple lineage paths. It might be worth consulting an enterprise data architect if needed to understand the full lineage]*

**What are the data sources within the above lineage from where data should be copied from / referenced and why are thse specific sources chosen ?**

**Are any of the data included affected by the General Data Protection Regulation (GDPR)? If Yes, describe which data.**

*[This might be defined in the BII]*

**Are there any specific expectations as to the format, structure or contents of the exposed data?**

*[Ideally internationally recognised standards should be used. If there are no recognised standards then please state this and aim to follow recognised best practices for enterprise data]*

**What fields and sources for master and reference data are available?**

### Backend System

**Is all data needed available and where can it be found**

**What technologies and interfaces are available for interacting with the  source data (e.g. Oracle DB / SQL DB, table / view / API), and what architecture patterns do they allow (e.g. ingest / copy, virtualisation, pull / push, ...)?**

**How scalable are these interfaces and are there performance considerations or limitations that might affect the frequency, query pattern or volume of data returned?**

**Are there several instances of the system(s)? If Yes, should data in any other instance(s) also be collected?**

**Do you know of any other systems in use by Equinor containing the same type(s) of data either the desired data types, or related master / reference data? If Yes, should the data from these systems also be collected?**

**Is any data model/documentation available? If Yes, provide link(s) to relevant model(s)/documentation.**

**Does the data source include data about when entities were last updated?**

## Decision Log

### General

**What queries and operations are being offered to the consumer?**

*e.g. Create, Read, Update, Delete, GetXxx*

**Are there any considerations needed based upon the Lineage of the data?**

*[Consider things like data quality issues, sources of error, delays, operational challenges and follow up of problems]*

### Data

**Which format should the data have in OMNIA after transfer (e.g. DB or file type)?**

**How will the data be modified, including but not limited to the contents, missing data, validation and transformation?**

**Will you do any automated data integrity testing?**

*[If so how will this be done - in real time, periodic monitoring, ...]*

**Will you provide the source data in it's entirety, or only a subset?**

*e.g. a particular time period, a particular asset*

**Will you be aggregating the data, and if so at what level of aggregation / granularity?**

**Do you need to maintain a full audit log / all historical changes to the data for reproducability, traceability. Are there constraints in the source systems that might make this difficult?**

[*When and how will this be done (e.g. snapshots / event based, frequency). If replicating data consider that multiple source updates between subsequent copies might not be readily available if such history is not supported by the source system so if needed how will you solve this?]*

### Architecture

**Through what type of interface will the data be made available (note data architecture and API first guidelines)?**

e.g. API, DB view, File, Queue, ...

**What partitioning requirements should be implemented for the data?**

**What high level architecture(s) pattern will the data flow follow?** 

e.g. copy, virtualisation, streaming, ...

**What caching is implemented and how might this affect consumers?**

#### Considerations when copying data

**How often will the transfer of data occur**

**What is the estimated size of the data during each update and what possibilities are there for doing a delta copy?**

**How long is each copy operation estimated to take**

**Is there a plan for any initial loading of data?**

### Lifecycle

**Who owns the data flow?**

**What operational SLA is being offered?**

**What notifications and alerting are to beimplemented if so what for?**

e.g. on specific errors, non-triggered events, end-to-end, ... 

**What is the deprecation policy for the data flow**
