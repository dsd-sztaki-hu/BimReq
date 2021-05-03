# BimReq
BimReq is a ligtweight ontology to represent regulations and requirements in RDF for construction projects. 

Markdown documentation created by [pyLODE](http://github.com/rdflib/pyLODE) 2.9.1

# BimReq

## Metadata
* **URI**
  * `http://demo.dsd.sztaki.hu/bimreq`
* **Creators(s)**
  * András Micsik, Ádám Kovács
* **Version Information**
  * 0.9
* **Imports**
  * [express:](https://w3id.org/express#)
  * [foaf:](http://xmlns.com/foaf/0.1/)
  * [sh:](http://www.w3.org/ns/shacl#)
* **Ontology RDF**
  * RDF ([bimreq.ttl](turtle))
### Description
BimReq is a ligtweight ontology to represent regulations and requirements in RDF for AEC (Architecture, Engineering, Construction) projects. The requirements can refer to regulations and may contain SHACL validation shapes for compliance checking of BIM models.

Example use ([bimreqExample.ttl](turtle))

## Table of Contents
1. [Classes](#classes)
1. [Object Properties](#objectproperties)
1. [Namespaces](#namespaces)
1. [Legend](#legend)


## Overview

**Figure 1:** Ontology overview
## Classes
[Regulation](#Regulation)
[Report](#Report)
[Requirement](#Requirement)
[RequirementSet](#RequirementSet)
### Regulation
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#Regulation`
Description | Regulations for Architecture, Engineering & Construction (AEC) projects. Describe primarily with the metadata necessary for identification using Dublin Core terms. For example, creator is the regulator authority. Ideally, regulations would be provided by the regulators themselves. It may contain a SHACL Shape for automated checking of BIM models.
In range of |[sourceRegulation](#sourceRegulation) (op)<br />
### Report
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#Report`
Description | The outcome of evaluation of a BIM model against a RequirementSet.
In domain of |[basedOn](#basedOn) (op)<br />[hasResult](#hasResult) (op)<br />
### Requirement
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#Requirement`
Description | Requirements may be raised by the client or a designer, but may also be derived from regulations. A SHACL Shape may be added to a requirement for automated checking of BIM models in IFC OWL.
In domain of |[validatorShape](#validatorShape) (op)<br />[sourceRegulation](#sourceRegulation) (op)<br />
### RequirementSet
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#RequirementSet`
Description | A group of requirements. Useful for coupling with projects or BIM models.
In domain of |[contains](#contains) (op)<br />
In range of |[basedOn](#basedOn) (op)<br />[inSet](#inSet) (op)<br />

## Object Properties
[basedOn](#basedOn),
[contains](#contains),
[hasResult](#hasResult),
[inSet](#inSet),
[sourceRegulation](#sourceRegulation),
[validatorShape](#validatorShape),
[](basedOn)
### basedOn
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#basedOn`
Description | The requirement set checked in this report.
Domain(s) |[Report](#Report) (c)<br />
Range(s) |[RequirementSet](http://demo.dsd.sztaki.hu/bimreq#RequirementSet) (c)<br />
[](contains)
### contains
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#contains`
Description | The requirements (or requirement sets) in this requirement set.
Domain(s) |[RequirementSet](#RequirementSet) (c)<br />
Range(s) |http://demo.dsd.sztaki.hu/bimreq#Requirement<br />http://demo.dsd.sztaki.hu/bimreq#RequirementSet<br />
[](hasResult)
### hasResult
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#hasResult`
Description | The result of the validation.
Domain(s) |[Report](#Report) (c)<br />
Range(s) |[sh:ValidationReport](http://www.w3.org/ns/shacl#ValidationReport) (c)<br />
[](inSet)
### inSet
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#inSet`
Description | The sets containing the requirement or requirement set.
Domain(s) |([Requirement](#Requirement) (c) or [RequirementSet](#RequirementSet) (c))<br />
Range(s) |[RequirementSet](http://demo.dsd.sztaki.hu/bimreq#RequirementSet) (c)<br />
[](sourceRegulation)
### sourceRegulation
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#sourceRegulation`
Description | The regulation from which the requirement has been derived.
Domain(s) |[Requirement](#Requirement) (c)<br />
Range(s) |[Regulation](http://demo.dsd.sztaki.hu/bimreq#Regulation) (c)<br />
[](validatorShape)
### validatorShape
Property | Value
--- | ---
URI | `http://demo.dsd.sztaki.hu/bimreq#validatorShape`
Description | The SHACL shape that can be used for validation the requirement.
Domain(s) |[Requirement](#Requirement) (c)<br />
Range(s) |[sh:Shape](http://www.w3.org/ns/shacl#Shape) (c)<br />

## Named Individuals
## Namespaces
* **default (bimreq)**
  * `http://demo.dsd.sztaki.hu/bimreq`
* **:**
  * `http://demo.dsd.sztaki.hu/bimreq#`
* **cc**
  * `http://creativecommons.org/ns#`
* **dc**
  * `http://purl.org/dc/terms/`
* **dce**
  * `http://purl.org/dc/elements/1.1/`
* **express**
  * `https://w3id.org/express#`
* **foaf**
  * `http://xmlns.com/foaf/0.1/`
* **ifcowl**
  * `http://ifcowl.openbimstandards.org/IFC4#`
* **owl**
  * `http://www.w3.org/2002/07/owl#`
* **prov**
  * `http://www.w3.org/ns/prov#`
* **rdf**
  * `http://www.w3.org/1999/02/22-rdf-syntax-ns#`
* **rdfs**
  * `http://www.w3.org/2000/01/rdf-schema#`
* **sdo**
  * `https://schema.org/`
* **sh**
  * `http://www.w3.org/ns/shacl#`
* **skos**
  * `http://www.w3.org/2004/02/skos/core#`
* **vann**
  * `http://purl.org/vocab/vann/`
* **xsd**
  * `http://www.w3.org/2001/XMLSchema#`

## Legend
* Classes: c
* Object Properties: op
* Functional Properties: fp
* Data Properties: dp
* Annotation Properties: dp
* Properties: p
* Named Individuals: ni
