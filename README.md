# Platform Services Development Standards

This guide outlines the devlopment standards required by the Platform Services team at AGN. 

## Introduction

Here are some of the documents from Salesforce that informed our standards. If something isn't fully addressed here, it's probably covered in great detail in one of these:

* [Apex Code Best Practices](http://wiki.developerforce.com/page/Apex_Code_Best_Practices)

* [Best Practice: Bulkify Your Code](http://wiki.developerforce.com/page/Best_Practice%3A_Bulkify_Your_Code)

* [Best Practice: Ensure Test Methods Verify Large Datasets](http://wiki.developerforce.com/page/Best_Practice:_Ensure_Test_Methods_Verify_Large_Datasets)

## 1. Class, Trigger, Component, and Page names should be prefixed with a 2-4 uppercase character solution code followed by an underscore

**For example:**
```objc
FMV_Utils
SFA_SummaryPage
```

**Not:**
```objc
fmvUtils
SFASUMMARYPAGE
```
