# Platform Services Deployment Standards

## Introduction

Internal Best-Practices for deployments on the Platform.

Applies to anyone authorized to create or deploy declarative, configured or coded components to one or more Allergan Orgs.

## Table of Contents

* [1. Credentials](#1-credentials)
* [2. Approaches/Tools](#2-approaches)


## 1. Credentials

Deploy as yourself. Do not use a service account, or anyone else's account
    
## 2. Approaches/Tools

Change Sets will suffice for minor deployments. Otherwise Ant should be used.

The Eclipse IDE should never be connected to an AGN production environment.

## 3. Verification

Verify that the existing unit tests run to completion after a change is made, especially if the change does not trigger all tests - such as adding a unique constraint to an existing field.


