# Operational Runbook - {Solution / Data flow name}

## Table of Contents

- [Operational Runbook](#operational-runbook)
  - [Introduction](#introduction)
  - [Summary](#summary)
  - [Authoring Guidelines](#authoring-guidelines)
  - [Legal](#legal)
  - [Architecture](#architecture)
    - [Architecture overview](#architecture-overview)
    - [Hardware](#hardware)
    - [Software](#software)
    - [Information](#information)
    - [Interfaces and dependencies](#interfaces-and-dependencies)
    - [Test and quality assurance](#test-and-quality-assurance)
  - [Configuration](#configuration)
    - [System configuration](#system-configuration)
    - [Security Configuration](#security-configuration)
  - [Operations](#operations)
    - [Change Management](#change-management)
    - [Access Management](#access-management)
    - [Operational Monitoring](#operational-monitoring)
    - [Functional updates](#functional-updates)
    - [Capacity management](#capacity-management)
    - [Backup and restore](#backup-and-restore)
    - [Decommissioning](#decommissioning)
    - [Troubleshooting](#troubleshooting)
  - [Security](#security)
    - [Risk assessment](#risk-assessment)
    - [Vulnerability assessment](#vulnerability-assessment)
    - [Security updates](#security-updates)
    - [Security monitoring](#security-monitoring)
    - [Incident handling](#incident-handling)
  - [Disaster recovery](#disaster-recovery)
    - [Disaster recovery](#disaster-recovery-1)
    - [Business continuity](#business-continuity)
  - [Service level agreements](#service-level-agreements)
  - [Regulatory compliance](#regulatory-compliance)
    - [Sarbanes-Oxley Act (SOX)](#sarbanes-oxley-act-sox)

## Introduction

This runbook provides the complete operational documentation of {System name}.

The document should be used to understand how the system is configured and functions, including how to perform system administrative tasks. The primary audience for this document are personnel responsible for managing and operating the system.

## Summary

*Detailed description of what the operational runbook covers. If there are any
limitations on the system in scope, this must be specified here.*

## Authoring Guidelines

To assist in filling out the runbook correctly, the following applies:

- *Italicized text throughout the template is provided as background information to assist in creating the document. In the final version of the document, this text must be removed and/or replaced by system-specific information.*
- Existing chapters or subchapters shall not be deleted. If a subchapter is considered irrelevant for the system, this must be specified in the body text of the subchapter.
- New subchapters can be added as required. When doing so, the table of contents must be updated.
- Linking to Standard Operating Procedures (SOPs), KB articles and information stored in other systems is encouraged to avoid duplication of content across documents / multiple runbooks.  
- No sensative or confidential information shall be entered in the runbook itself (although referenced SOPs, with appropriate access control, can contain this type of information). This limitation applies to passwords etc. that should be held in a secured key vault.

## Legal

This document contains information that is proprietary to Equinor ASA. Neither the document nor the information contained therein should be disclosed or reproduced in whole or in part, without express written consent of Equinor ASA.  

The document and the information it contains shall be handled according to Equinor’s information classification scheme.

## Architecture

### Architecture overview

*The overall system architecture and description. If available, provide a link
to the relevant system landscape diagram in
[Equinor EA](http://eita.statoil.no/companyea/?oid=b1b18bd9-9cca-45a7-9289-9eacf4c7f462/).*

![Data Pipeline Architecture](./architecture-data-pipelines.drawio.svg)
*(edit this diagram on the draw.io site, or using the VS Code draw.io integration plugin)*

The main components in the system architecture are described in the table below. See also [Interfaces and dependencies](#interfaces-and-dependencies).

#### *[Component Type]*

##### *[Feature]*

- *[Name]* - *[Usage]*
- *[Name]* - *[Usage]*

#### *[Component Type 2]*

##### *[*Feature*]*

- *[Name]* - *[Usage]*
- *[Name]* - *[Usage]*

### Hardware

*Hardware architecture and inventory for the system, including virtual
servers/appliances. Should also include an overview of which components are
critical for the system operation. Detailed information on hardware can
typically be found in [DRM](https://drm.statoil.com) and
[Services@Equinor](https://statoil.service-now.com/).*

See also [Interfaces and dependencies](#interfaces-and-dependencies) for an overview of shared hardware components used.

### Software

*Software architecture and inventory for the system. Should also include an
overview of which components are critical for the system operation. Detailed
information on software can typically be found in
[DRM](https://drm.statoil.com) and
[Services@Equinor](https://statoil.service-now.com/).*

See also [Interfaces and dependencies](#interfaces-and-dependencies) for an overview of shared software components used.

### Information

*Information architecture and inventory for the system. Should describe where
information is stored, as well as the information flows within the system.*

### Interfaces and dependencies

*Interfaces and dependencies towards other systems, both internal and external, regardless of the dependency direction.*

#### *[Component Type]*

- Name - *[Name]*
- Subscription - *[Name]*
- Resource Group - *[Name]*
- Usage - *[Dev|Test|Prod]*
- Criticality - *[Low|Medium|High]*

#### *[Component Type]*

- Name - *[Name]*
- Subscription - *[Name]*
- Resource Group - *[Name]*
- Usage - *[Dev|Test|Prod]*
- Criticality - *[Low|Medium|High]*

### Test and quality assurance

*Description of the test and/or quality assurance environment.*

## Configuration

### System configuration

*Description of how the system is and shall be configured. Should include
details on all configuration done throughout the lifecycle of the system, not
just during initial installation.*

#### Configuration, custom code and deployment scripts

### Security Configuration

*Description of how the system is configured in terms of security (system hardening). Should include details on all configuration done throughout the lifecycle of the system, not just during initial installation.
Equinor’s information security governance, WR1211, contains topics relevant for this chapter. These include, but are not limited to:*

- *Access control*
- *Authentication*
- *Authorization*
- *Data segregation*
- *Malware protection*
- *Network security*
- *Removal of unused services and accounts*
- *Password policies*
- *Security logging*  

#### *[Component Type]*

- *[Name or 'See [Software](#software)']* - *[Access permissions description]*
- *[Name or 'See [Software](#software)']* - *[Access permissions description]*

#### *[Component Type]*

- *[Name or 'See [Software](#software)']* - *[Access permissions description]*
- *[Name or 'See [Software](#software)']* - *[Access permissions description]*

## Operations

### Change Management

*The process for making changes to the system.*

e.g. *[All changes to code and configuration are tracked through github. CI/CD is used for deployment with manual approvals required for release to Production. Checklists are used to ensure quality and complience at key decision points.]*

### Access Management

*Management and procedures for handling access to the system (joiners, movers
and leavers). This description shall cover all accesses provided by IT, both
for privileged and unprivileged users.*

e.g. *[Access permissions for all Azure components except the SQL databases are managed using groups in Azure Active Directory, through the Azure portal. SQL database users and permissions are defined using SSMS.]*

*[All members of XXX have administrator access to all system components in the development and test environments. Selected members have administrator access in the production environment. Other access permissions are specified in the [Security configuration](#security-configuration) section.]*

### Operational Monitoring

*Monitoring of aspects related to system health and stability.*

e.g. *[[Azure Log Analytics](LINK) is used for monitoring the data flow.]*

### Functional updates

*Operational procedures for identifying, implementing and verifying updates to
the system. This does not include security updates, as these are covered in
[Security](#security).*

### Capacity management

*Procedures for scaling the system according to business needs. These
procedures should cover both up- and downscaling of the system.*

### Backup and restore

*Procedures for managing backup and restore of the system.*

### Decommissioning

*Procedures for decommissioning the system or parts of the system.*

### Troubleshooting

*All procedures related to handling of errors and faults in the system.*

*[Enter any procedures (actions) below – for each specific issue (case):]*

#### Case title

*[Actions description]*

#### Case title

*[Actions description]*

## Security

### Risk assessment

*Link to the current information security risk assessment for the system.*

### Vulnerability assessment

*Procedures for assessing vulnerabilities in the system. For systems managed by
Equinor, the following standard procedure will in most cases apply:
http://team-2.statoil.com/sites/ts-47273/_layouts/DocIdRedir.aspx?ID=be9d78d4-3704-47b4-9ee9-881b87b7feb9&HintUrl=Metodikk%2fVuln+mgmt+SOP.docx
(Note: Bad URL?, possible replacement
[KB0044227](https://equinor.service-now.com/selfservice?id=kb_article&sys_id=605eaf8bdbac805035e1cd4d0b961966))*

Refer to Standard Operating Procedure (SOP) – Vulnerability Management.

### Security updates

*Procedures for identifying, implementing and verifying security updates to the
system. These procedures shall cover both planned and unplanned (out-of-band)
security updates.  An overview of the considerations which should be made when
creating such a patch management program can be found in
[KB0035618](https://equinor.service-now.com/selfservice?id=kb_article&sys_id=6a5048ba4f97e2c0bd03ce318110c7f9).*

### Security monitoring

*Description on how security monitoring is performed in the system. This
description shall as a minimum cover which events are logged, and how relevant
security logs are monitored and/or reviewed.  A guide to achieving compliance
with Equinor’s logging requirements can be found in
[KB0035619](https://statoil.service-now.com/selfservice/knowledge_detail.do?sysparm_document_key=kb_knowledge,5f90007e4f97e2c0bd03ce318110c7f3)
(Note: Bad URL).*

### Incident handling

*Description of how information security incidents are handled. For systems
managed by Equinor, the procedure should be aligned with [SF103 - Handle safety
and security
incident](http://aris.statoil.no/?objectguid=f9469e01-b2be-11e0-43e7-828060af7619)
(Note: Bad URL, possible replacement [SF103 - Handle safety and security
incident](https://aris.equinor.com/#default/item/c.L5CollaborationDiagram.Production.p4brEjE7EeoAEAANOmTg1g.-1/~AbBbIm1vZGVsVmlld2VyUmVwb3J0cyJd).*

## Disaster recovery

### Disaster recovery Plan

*Description of the disaster recovery procedures. There is no requirement for a
system-specific plan if the system is part of a larger DR plan for the
datacenter, and this is considered sufficient.*

### Business continuity

*Description of the business continuity plans.*

## Service level agreements

*Reference to SLAs relevant to the system.*

### Operational Responsibilities

*e.g. Incidents and Requests are handled in Services@Equinor, and using the CI named [CI Name] in the assignment group [assignment group name].*

## Regulatory compliance

*Description of how the system complies with regulatory requirements. Please
verify whether the system in question is subject to the requirements before
filling out the sections below.*

### Sarbanes-Oxley Act (SOX)

*The remainder of this section only if applicable, otherwise enter "Not applicable" and remove.*

(Please move content from system’s file in SOXcritApps into this chapter)

- Application location:
  - [ ] On prem.
  - [ ] Cloud
  - [ ] Other: {Specify}
- User provisioning (roles & access):
  - [ ] AccessIT
  - [ ] Other: {Specify}, link to procedure: {Link}
- Is provisioning considered (dis-)connected\*?
  - [ ] Connected
  - [ ] Disconnected
- Access approval performed by\*\*
  - [ ] Statoil
  - [ ] Outsourced/3rd party, link to report: {Link}
- Consider all key controls in KC1500. Would you say any of the controls are performed by a 3rd party for the application?\*\*\*
  - [ ] No
  - [ ] Yes
  - [ ] I don’t know

\*: Approval performed in AccessIT, but users manually provisioned in target application/system.

\*\* and \*\*\*: If access approval performed by 3rd party or if your answer is Yes or I don’t know on control performance, we need to consider running "KC0835 Review of internal control environment at suppliers". Contact CIT IS to discuss if this is applicable.

- Application identified as SOX Critical date\*:
  - {Enter date}
- Who (process) nominated the application\*:
  - {List of processes}
- Why was it nominated as SOX Critical\*: 
  - [ ] SGR
  - [ ] Functionality
  - [ ] Data processing
  - [ ] Automatic CTRL

\*: This information can be found in the "KC0419 Identify SOX Critical Applications" documentation.

If "Application location" is "On prem." or "Other", continue to fill this table:

Briefly describe the program stack (application, middleware, DB, OS and other
relevant interfaces/batch jobs) the application operates in. The purpose of
describing the entire program stack is to use that to identify which key
controls are relevant to perform for the application and underlaying stack. The
scope for any key control is the entire program stack. It is not of interest
which technology is used outside Statoil’s domain (at 3rd parties).

| Application stack | Technology/System (Indicate with "N/A" if not applicable) |
|-------------------|-----------------------------------------------------------|

- Application
  - (Same as application above)
- Middleware
  - [ ] N/A
  - [ ] Cisco Information Server
  - [ ] IBM MQ
  - [ ] IBM WebSphere
  - [ ] MS BizTalk
  - [ ] OAQ
  - [ ] SAP BPC
  - [ ] SAP NetWeaver
  - [ ] SSIS
  - [ ] Tibco
  - [ ] Web-Services 
  - [ ] Other: {specify}|
- Database - Brand
  - [ ] N/A
  - [ ] Oracle
  - [ ] MS SQL
  - [ ] Other: {specify}
- Database - Names of DB
  - {Fill in list of db names}
- OS- Platform
  - [ ] MS Windows
  - [ ] Unix/Linux
  - [ ] Other: {specify}
- Other(g-disks, terminal server, teamsites, develop- ment environment, etc)
  - [ ] N/A
  - [ ] Other: {Briefly describe other components included in the solution}
- Batch jobs/Interfaces
  - [ ] N/A
  - [ ] Other: {Scope batch jobs as defined in "KC0xyz Periodic review of batch jobs". List relevant batch jobs and interfaces here.}

*Conduct a meeting with the author of IT900 appendix (for the process that nominated the application.)
Purpose of meeting is to identify any risks associated with the application that needs to be added to an appendix. Add a brief statement describing the outcome of this meeting including any changes that needs to be made to appendices. This step is part of the annual part of KC0006.*

{Brief statement describing meeting outcome and which changes to perform in IT900 appendix}

*Practical info after steps above are completed:*

- Name the file: SOX Crit app - {application name as in ServiceNow}.docx
e.g.:
  - SOX Crit app - Dispatch Europe.docx
  - SOX Crit app - AccessIT - Applications and SAP Roles.docx

File and keep document updated in this team site: SOX Critical Applications
For team site issues, contact me.

Key Controls referenced:

- KC0419 Identify SOX Critical applications
- KC0835 Review of internal control environment at suppliers
- KC0xyz Periodic review of batch jobs *(correct KC-number will be supplied as soon as control is published)*
- KC0179 Completeness in the control mapping and control master data
