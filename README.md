# Platform Services Development Standards

This guide outlines the Force.com development standards required by the Platform Services team at AGN. 

## Introduction

The Salesforce documents linked below informed our standards. If something isn't fully addressed here, it's probably covered in great detail in one of these:

* [Apex Code Best Practices](http://wiki.developerforce.com/page/Apex_Code_Best_Practices)

* [How to Write Good Unit Tests](http://wiki.developerforce.com/page/How_to_Write_Good_Unit_Tests)

* [An Introduction to Exception Handling](http://wiki.developerforce.com/page/An_Introduction_to_Exception_Handling)

* [Best Practice: Bulkify Your Code](http://wiki.developerforce.com/page/Best_Practice%3A_Bulkify_Your_Code)

* [Best Practice: Ensure Test Methods Verify Large Datasets](http://wiki.developerforce.com/page/Best_Practice:_Ensure_Test_Methods_Verify_Large_Datasets)

## Table of Contents

* [1. Solution Code Prefix](#1-solution-code-prefix)

* [2. Commenting: JavaDoc for structure / Inline for readability](#2-commenting-javadoc-for-structure--inline-for-readability)

* [3. Bulkify](#3-bulkify)

* [4. Unit Tests: Positive and Negative Cases](#4-unit-tests-positive-and-negative-cases)

* [5. Unit Tests: Data](#5-unit-tests-data)

* [6. Unit Tests: Coverage](#6-unit-tests-coverage)

* [7. Unit Tests: Naming](#7-unit-tests-naming)
 
 
## 1. Solution Code Prefix

Class, Trigger, Component, Page, and Static Resource  names should be prefixed with a 2-4 uppercase **solution code** followed by an underscore.

**For example:**
```objc
FMV_Utils
SFA_SummaryPage
RUSH_CreateProgramAllocations
```

**Not:**
```objc
fmvUtils
SFASUMMARYPAGE
mysupervaguecontrollername
```

## 2. Commenting: JavaDoc for structure / Inline for readability

Apex comments should adhere to the JavaDoc style so that AGN can produce documentation from code. Please note that **all methods** are commented, as is the class header. 

Inline comments are strongly encouraged as well. The more **frequent** and **meaningful**, the better.

```java
/**
 * UM1 APP: Standards Demonstration (SDEM)
 * <p>
 * Class for supporting SDEM* Triggers.
 * 
 * @author          Centerstance, Sebastian Kessel
 * @version         1.101 PRD
 * @date            04/29/2013
 * @description     Class for supporting SDEM* Triggers. Primary functionality is creation of awesome comments that make the code more maintainable.
  
*/

public without sharing class SDEM_GlobalUtils {
/**
* @author           Centerstance, Sebastian Kessel
* @version          1.101 PRD
* @date             04/29/2013
* @description      Adds VF pagemessage
* @param            String strText
* @return           Void
*/
public static void addMessage(String strText) {
  //adding message
  ApexPages.Message myMsg = new ApexPages.Message(ApexPages.Severity.WARNING,text);
  ApexPages.addMessage(myMsg);
}
/**
* @author          Centerstance, Sebastian Kessel
* @version         1.101 PRD
* @date            04/29/2013
* @description     Checks string for null/empty
* @param           String strText
* @return          Boolean
*/
public static boolean isNullOrEmpty(String strText) {
  //test incoming string
  if (text == '' || text == null) {return true};
    return false;
  }
}

```

## 3. Bulkify

All Apex should be **"bulkified"** in order to process more than one record at a time.

Seriously.

## 4. Unit Tests: Positive and Negative Cases

Unit tests should cover **every use case** of the application, including positive and negative cases, as well as bulk and single record scenarios.

Please make clear assertions. Simply covering the code is not sufficient.

## 5. Unit Tests: Data

Unit tests may **not rely on real data**, or set `SeeAllData=true`

## 6. Unit Tests: Coverage

Unit test coverage must be greater than or equal to **85%**

## 7. Unit Tests: Naming

Unit tests should reside in an adjacent class with a **_TEST** suffix

**For example:**
```objc
FMV_Utils
FMV_Utils_TEST
```

**Not:**
```objc
FMV_Utils
FMV_Utilstests
TEST_FMV_Utils
miscdevtestsfor2009
```

## Motivational Quotes

> The place to express yourself in programming is in the quality of your ideas, and the efficiency of execution. The role of style is the same as in literature. A great writer doesn't express himself by putting the spaces before his commas instead of after, or by putting extra spaces inside his parentheses. A great writer will slavishly conform to some rules of style, and that in no way constrains his power to express himself creatively. See for example William Strunk's [The Elements of Style](http://www.crockford.com/wrrrld/style.html). I think this applies to programming as well. 

> Conforming to a consistent style improves readability, and frees you to express yourself in ways that matter. JSLint here plays the part of a stern but benevolent editor, helping you to get the style right so that you can focus your creative energy where it is most needed.
>
> -- <cite>[Douglas Crockford on JSLint, the The JavaScript Code Quality Tool](https://gist.github.com/textarcana/1745829)</cite>
