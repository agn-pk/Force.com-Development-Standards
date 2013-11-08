# Platform Services Development Standards

This guide outlines the Force.com development standards required by the Platform Services team at AGN. 

## Introduction

The Salesforce documents linked below informed our standards. If something isn't fully addressed here, it's probably covered in great detail in one of these:

* [Apex Code Best Practices](http://wiki.developerforce.com/page/Apex_Code_Best_Practices)

* [Best Practice: Bulkify Your Code](http://wiki.developerforce.com/page/Best_Practice%3A_Bulkify_Your_Code)

* [Best Practice: Ensure Test Methods Verify Large Datasets](http://wiki.developerforce.com/page/Best_Practice:_Ensure_Test_Methods_Verify_Large_Datasets)

## 1. Solution Code Prefix

Class, Trigger, Component, Page, and Static Resource  names should be prefixed with a 2-4 uppercase solution code followed by an underscore.

**For example:**
```objc
FMV_Utils
SFA_SummaryPage
RUSH_SRO_CreateProgramAllocations
```

**Not:**
```objc
fmvUtils
SFASUMMARYPAGE
mysupervaguecontrollername
```

## 2. Commenting: JavaDoc for structure / Inline for readability

Apex comments should adhere to the JavaDoc style so that Allergan can produce documentation from code . Please note that all methods are commented, as is the class header. 

Inline comments are strongly encouraged as well. The more frequent and meaningful, the better.

```objc
public without sharing class AGN_GlobalUtils {
/**
* @author Centerstance, Sebastian Kessel
* @version 1.0 BETA
* @date 03/15/2013
* @description Adds VF pagemessage
* @param String strText
* @return Void
*/
public static void addMessage(String strText) {
  //adding message
  ApexPages.Message myMsg = new ApexPages.Message(ApexPages.Severity.WARNING,text);
  ApexPages.addMessage(myMsg);
}
/**
* @author Centerstance, Sebastian Kessel
* @version 1.0 BETA
* @date 03/15/2013
* @description Checks string for null/empty
* @param String strText
* @return Boolean
*/
public static boolean isNullOrEmpty(String strText) {
  //test incoming string
  if (text == '' || text == null) {return true};
    return false;
  }
}

```

## 3. All Apex should be “bulkified” in order to process more than one record at a time.

## 4. Unit Tests: Positive and Negative Cases

Unit tests should cover every use case of the application, including positive and negative cases, as well as bulk and single record scenarios.

Please make clear assertions. Simply covering the code is not sufficient.

## 5. Unit tests may not rely on real data, or set SeeAllData=true

## 6. Unit test coverage must be greater than or equal to 85%

## 7. Unit tests should reside in an adjacent class with a _TEST suffix

**For example:**
```objc
FMV_Utils
FMV_Utils_TEST
```

**Not:**
FMV_Utils
FMV_Utilstests
TEST_FMV_Utils
```
