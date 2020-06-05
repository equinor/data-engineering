# Consumer Requirements
This document contains requirements for the data share from the consumer perspective for {ENTER_ CONSUMER_HERE}. It does not touch on other important related requirements such as handling of data consumed from such services.

All new data shares should adhere to the recommendations defined in the Enterprise Data Architecture and other governing documentation. What is entered here might differ from what is actually provided and so it is important to understand such changes and their possible impact.

*Note: There should be a seperate document for each consumer. Feel free to suplement the points in this document with additional information as suitable*


## General

**What type of data object are you interested in?**

*[Please be as specific as possible. If you have any information about what this data can be retrieved from please include details]*

**Has any necessary LRA been performed for using this data, and what is the reference?**

*[See the [legal risk assessment service](https://equinor.service-now.com/selfservice?id=kb_article&sys_id=c5acb55fdb610c94c293199f299619dd)]*

## Data Content

**Are there any specific expectations as to the format, structure or contents of the data?**


**What queries and operations are you expecting to be able to perform?**

*[e.g. Create, Read, Update, Delete, GetXxx]*

**What expectations do you have in relation to data quality, including but not limited to the contents, missing data, validation and transformation**

*[Should any changes from the 'source' system be applied. See the point on lineage below as there may be multiple systems the data passes through]*

**Will you consume the data in it's entirety, or only a subset?**

*[e.g. particular fields, a particular time period, a particular asset]*

**Will you be aggregating the data, and if so at what level of granularity?**


**For data that can be modified, do you need access to older versions of the data?**

*[Do you need access to older versions of data objects to see possible changes, or is it sufficient to just see the latest entry]*

## Communication

**How will you query the specified operations in terms of 1) frequency and 2) expected request / response size?**

*[Please specify for every operation and mode of querying]*

**Can you further optimise the querying of data through additional architecture layers?**

The application will cache the data and wont necessarylity affect our service 

**What are the preferred and maximum times you can wait before updates (originating from the original source, your application or elsewhere) are reflected in returned data?**

*[Specify relative to the full lineage of the data, including any delay caused by manual steps]*

**How do you hope to access the data (note API first guidelines)**?

*[e.g. API, DB query, File, Queue, ...]*

## Lifecycle

**Do you have any particular operational SLA requirements?**

*[e.g. Latency, Quality, Technical Support, Service Availability, Revovery Point Objective (potential for lost data in failure), Recovery Time Objective (time to restore service / data)]*

**Do you need any notifications or alerting and if so what for and under what conditions?**

*[e.g. on specific errors, non-triggered events, end-to-end, ... ]*

**Do you have requirements outside the specified data share deprecation policy**

*[All data shares / API's should have a deprecation policy that mandates how quickly deprecated versions will be removed]*

## Other

Whilst not specifically requirements for the data share, you should also consider how it will fit as a part of your wider system. Amongst other points, you might consider:

**The lineage of the data and how this might impact usage?**

*[Do you know all the steps that data takes from when it is produced, including physical, electronic and otherwise and what adverse situations can occur across all of these?]*

**Handling and impact of unavailability of the share**

*[How will you handle unavailability of the share and what impact will this have on your system. Are alternative needed incase of downtime?]*

**Handling and impact of missing, delayed or corrupted data**

*[What impact might this have and how will you detect, and handle such data?]*

**Other...**

*[Anything else that you can think of that might be relevant?]*

*This document is based upon a template from: https://github.com/equinor/data-engineering*
