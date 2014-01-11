# Platform Services Declarative Development Standards

## Introduction

Internal Best-Practices for building intuitive, self-describing solution components on the Platform.

Applies to anyone authorized to create or deploy declarative, configured or coded components to one or more Allergan Orgs.

## Table of Contents

* [1. Standard Objects](#1-method-names)
* [2. Custom Objects](#2-variable-names)
* [3. Email Alerts and Templates](#2-variable-names)
* [4. Workflows](#2-variable-names)
* [5. Groups, Queues, Reports](#2-variable-names)
* [6. Validation Rules](#2-variable-names)
* [7. Integrations](#2-variable-names)
* [8. Formula Appendix](#2-variable-names)

## 1. Standard Objects

To ensure single Standard Objects (e.g. Account, Contact) in an Org can be successfully used to support a variety of applications, the following conventions should be followed:

When Standard Fields are shared across multiple applications, each builder should evaluate how specific fields are being employed by other applications to determine feasibility of cross-use 
Custom Fields should be employed when use of standard fields would be otherwise ineffective
In highly shared Orgs, Record Types should be named and employed to segment multiple applications from one another. Use of an application’s solution prefix (e.g. FMV) should be considered in the name of the record type to ease distinction between applications
Page Layouts should be named in such a way that a builder can easily identify their association with a specific application (e.g. FMV)
    
## 2. Custom Objects

Always use custom record types: create one called AGN as default
Record type names per object require a clear naming convention
Limit object reference counts to less than 10
Standard NAME fields should be intelligently formatted when possible (e.g. HCP.20120428)
External ID fields should truly be driven by external system requirement
Should contain the following custom fields: Label, Link, Email Link and Hyperlink (see appendix for formulas)
Leverage Self Status fields containing simple set of AGN universal values: e.g. Pending, Submitted, Approved, Rejected
Leverage a custom checkbox field called Locked to support self-locking
All fields must have descriptions and help text

Avoid using the term “ID” in custom field names and labels
Ensure field labels and field names always match
Use the field qualifier of “Name” when referring to name fields (e.g. User object)
Do not use Encryption attribute
Employ create Locked Field when possible
Avoid Telephone number formatted fields when possible

## 3. Email Alerts and Templates

Email Alert names: should use solution code prefix (e.g. FMV)
Email Template names: should use solution coded message ID’s (FMV001)
Email Template text: body should reference email template number in footer of email to provide traceability

## 4. Workflow

Workflow names: should use solution code prefixes (e.g. FMV) followed by a hyphen
Workflow names: preface with solution code, avoid spaces in the name. Ex: FMV-PredateAssessment
Field Update names: preface with solution code, avoid spaces in the name. Ex: FMV-SetHCPWeight

## 5. Groups/Queues/Reports

Public Group names: should employ solution code prefixes (e.g. SFA) followed by a hyphen. Ex: SFA-Service Providers
Queue names: should employ solution code prefixes (e.g. SFA) followed by a hyphen. Ex: SFA-Service Providers
Report Folder names: should employ either department or solution code prefixes (e.g. SFA, EAS, HR) followed by a hyphen. Ex: HR-NA-Basic Reports, FMV-Essentials …

## 6. Validation Rules

Validation Rule names should employ mixed case convention with no spaces between significant words
Ex: PhysicianLicenseRequired

## 7. Integration

System admin-level API-oriented integrations should use a special user account. User account name will be specific to each Org, will contain the prefix “XBot”, and will be followed by the nickname for the Org in question. 
Examples: XBotAGN, XBotAP1, XBotRD1
Standard and Custom objects that are integrated with boundary systems must employ a custom field called SYS_TAG__c to support traceability and reconciliation between boundary systems.
Example: 20120821_Run1_SAPHR

## 8. Formula Appendix

LABEL:
Formula: concatenation of record standard NAME field and a more user-friendly field.
Example: APP-2108789.Cesar Cortes
Text: Friendly name with no link for use in views and reports.

LINK:
Formula: HYPERLINK( "../" & Id, Label__c , "_blank")
Text: Friendly name and hyperlink that pops a new window.

EMAIL LINK: 
Formula: HYPERLINK( “[URL for instance]/" & Id, Label__c , "_blank")
Text: Hyperlink field for use in delivering single-click references to users via email


