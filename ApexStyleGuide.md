# Platform Services Development Style Guide

Style Guide borrowed from DF13.

## Introduction

More on this later.

## Table of Contents

* [1. Method Names](#1-method-names)

* [2. Variable Names](#2-variable-names)

## 1. Method names

Method names should start with lowercase, Verb and follow CamelCase later.
    
**For example:**
```
prepareVendorResponse()
exportResults()
fixEverythingRightNow()
```
Boolean methods should start with “is”.

**For example:**
```
isValid()
```
## 2. Variable Names

Make sure that variable names start with lowercase and use camel case after that. No underscores. Constants can be all capital letters with underscores.

**For example:**
```
string strTest = 'test';

public static final string ACCOUNT_RT_PRESCRIBER_NAME = 'Prescriber';
```

## 3. Avoid nesting for loops more than 3x
```
 
    for() {
       for() {
          for() {
                  ….
                  System.debug('At this point I have no idea what is going on.')
          }
       }
     }
```

## 4. Avoid Procedual Code

Do not write large methods (say more than 100 lines). See if you can divide them into smaller piece of functionality which will help not only in readability/ maintainability of code but also in writing apex test classes/ getting more code coverage. In bigger methods typically some of alternate paths don’t get executed and we will get less coverage.
 
## 5. OOP Principles

Follow basic object oriented principles like Encapsulation, Abstraction, Polymorphisms, Inheritance, Delegation, etc.
  
## 6. Sharing

“with sharing” should be defined for classes which are public-facing to avoid them running in a without sharing/admin mode.

```
public with sharing class sharingClass {

// Code here

}
```

## 7. XML

Do not treat XML as a string. Instead use XML libraries like XMLStreamReader (SAX Parser) and XMLDom (DOM Parser) provided by Salesforce.

8. SOQL injections

Make sure SOQL injections are avoided
http://www.salesforce.com/us/developer/docs/apexcode/Content/pages_security_tips_soql_injection.htm


