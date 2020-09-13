---
title: "Technical Overview"
date: 2020-09-14T04:23:32+09:00
draft: false
# hide: header, nav, breadcrumb, footer
---

{{% notice %}}
[Security Assertion Markup Language (SAML) V2.0 Technical Overview](http://docs.oasis-open.org/security/saml/Post2.0/sstc-saml-tech-overview-2.0.html) の日本語訳です。  
公式なドキュメントでは無いため、参考にされる場合は原文と合わせてご利用ください。
{{% /notice %}}


## 1 Introduction
### 1.1 References

- [SAMLAuthnCxt]	J. Kemp et al. Authentication Context for the OASIS Security Assertion Markup Language (SAML) V2.0. OASIS SSTC, March 2005. Document ID saml-authn-context-2.0-os. See http://docs.oasis-open.org/security/saml/v2.0/saml-authn-context-2.0-os.pdf.
- [SAMLBind] S. Cantor et al. Bindings for the OASIS Security Assertion Markup Language (SAML) V2.0. OASIS SSTC, March 2005. Document ID saml-bindings-2.0-os. See http://docs.oasis-open.org/security/saml/v2.0/saml-bindings-2.0-os.pdf.
- [SAMLConform]	P. Mishra et al. Conformance Requirements for the OASIS Security Assertion Markup Language (SAML) V2.0. OASIS SSTC, March 2005. Document ID saml-conformance-2.0-os. See http://docs.oasis-open.org/security/saml/v2.0/saml-conformance-2.0-os.pdf.
- [SAMLCore]	S. Cantor et al. Assertions and Protocols for the OASIS Security Assertion Markup Language (SAML) V2.0. OASIS SSTC, March 2005. Document ID saml-core-2.0-os. See http://docs.oasis-open.org/security/saml/v2.0/saml-core-2.0-os.pdf.
- [SAMLErrata]	J. Moreh. Errata for the OASIS Security Assertion Markup Language (SAML) V2.0. OASIS SSTC, May, 2006. Document ID sstc-saml-errata-2.0-draft-nn. See http://www.oasis-open.org/committees/security/.
- [SAMLExecOvr]	P. Madsen, et al. SAML V2.0 Executive Overview. OASIS SSTC, April, 2005. Document ID sstc-saml-exec-overview-2.0-cd-01. See http://www.oasis-open.org/committees/security/.
- [SAMLGloss]	J. Hodges et al. Glossary for the OASIS Security Assertion Markup Language (SAML) V2.0. OASIS SSTC, March 2005. Document ID saml-glossary-2.0-os. See http://docs.oasis-open.org/security/saml/v2.0/saml-glossary-2.0-os.pdf.
- [SAMLMDExtQ]	T. Scavo, et al. SAML Metadata Extension for Query Requesters. OASIS SSTC, March 2006. Document ID sstc-saml-metadata-ext-query-cd-01. See http://www.oasis-open.org/committees/security/.
- [SAMLMDV1x]	G. Whitehead et al. Metadata Profile for the OASIS Security Assertion Markup Language (SAML) V1.x. OASIS SSTC, March 2005. Document ID sstc-saml1x-metadata-cd-01. See http://www.oasis-open.org/committees/security/.
- [SAMLMeta] S. Cantor et al. Metadata for the OASIS Security Assertion Markup Language (SAML) V2.0. OASIS SSTC, March 2005. Document ID saml-metadata-2.0-os. See http://docs.oasis-open.org/security/saml/v2.0/saml-metadata-2.0-os.pdf.
- [SAMLProf]	S. Cantor et al. Profiles for the OASIS Security Assertion Markup Language (SAML) V2.0. OASIS SSTC, March 2005. Document ID saml-profiles-2.0-os. See http://docs.oasis-open.org/security/saml/v2.0/saml-profiles-2.0-os.pdf.
- [SAMLProt3P] S. Cantor. SAML Protocol Extension for Third-Party Requests. OASIS SSTC, March 2006. Document ID sstc-saml-protocol-ext-thirdparty-cd-01. See http://www.oasis-open.org/committees/security/.
- [SAMLSec]	F. Hirsch et al. Security and Privacy Considerations for the OASIS Security Assertion Markup Language (SAML) V2.0. OASIS SSTC, March 2005. Document ID saml-sec-consider-2.0-os. See http://docs.oasis-open.org/security/saml/v2.0/saml-sec-consider-2.0-os.pdf.
- [SAMLWeb]	OASIS Security Services Technical Committee web site, http://www.oasis-open.org/committees/security.
- [SAMLX509Attr] R. Randall et al. SAML Attribute Sharing Profile for X.509 Authentication-Based Systems. OASIS SSTC, March 2006. Document ID sstc-saml-x509-authn-attrib-profile-cd-02. See http://www.oasis-open.org/committees/security/.
- [SAMLXPathAttr]	C. Morris et al. SAML XPath Attribute Profile. OASIS SSTC, August, 2005. Document ID sstc-saml-xpath-attribute-profile-cd-01. See http://www.oasis-open.org/committees/security/.
- [ShibReqs]	S. Carmody. Shibboleth Overview and Requirements. Shibboleth project of Internet2. See http://shibboleth.internet2.edu/docs/draft-internet2-shibboleth-requirements-01.html.
- [WSS]	A. Nadalin et al. Web Services Security: SOAP Message Security 1.1 (WS-Security 2004). OASIS WSS-TC, February 2006. Document ID wss-v1.1-spec-os-SOAPMessageSecurity. See http://www.oasis-open.org/committees/wss/.
- [WSSSAML]	R. Monzillo et al. Web Services Security: SAML Token Profile 1.1. OASIS WSS-TC, February 2006. Document ID wss-v1.1-spec-os-SAMLTokenProfile. See http://www.oasis-open.org/committees/wss/.
- [XACML]	T. Moses, et al. OASIS eXtensible Access Control Markup Language (XACML) Version 2.0. OASIS XACML-TC, February 2005. Document ID oasis-access_control-xacml-2.0-core-spec-os. See http://www.oasis-open.org/committees/xacml.
- [XMLEnc] D. Eastlake et al. XML Encryption Syntax and Processing. World Wide Web Consortium. See http://www.w3.org/TR/2002/REC-xmlenc-core-20021210/.
- [XMLSig] D. Eastlake et al. XML-Signature Syntax and Processing. World Wide Web Consortium. See .http://www.w3.org/TR/xmldsig-core/

## 2 Overview
### 2.1 Drivers of SAMK Adoption
### 2.2 Documentation Roadmap

## 3 High-Level SAML Use Cases
### 3.1 SAML Participants
### 3.2 Web Single Sign-On Use Case
### 3.3 Identity Federation Use Case

## 4 SAML Architecture
### 4.1 Basic Concepts
### 4.2 Advanced Concepts
#### 4.2.1 Subject Confirmation
### 4.3 SAML Components
### 4.4 SAML XML Constructs and Examples
#### 4.4.1 Relationship of SAML Components
#### 4.4.2 Assertion, Subject, and Statement Structure
#### 4.4.3 Attribute Statement Structure
#### 4.4.4 Message Structure and the SOAP Binding
### 4.5 Privacy in SAML
### 4.6 Security in SAML

## 5 Major Profiles and Federation Use Cases
### 5.1 Web Browser SSO Profile
#### 5.1.1 Introduction
#### 5.1.2 SP-Initiated SSO: Redirect/POST Bindings
#### 5.1.3 SP-Initiated SSO: POST/Artifact Bindings
#### 5.1.4 IdP-Initiated SSO: POST Binding

### 5.2 ECP Profile
#### 5.2.1 Introduction
#### 5.2.2 ECP Profile Using PAOS Binding

### 5.3 Single Lougout Profile
#### 5.3.1 Introduction
#### 5.3.2 SP-Initiated Single Logout with Multiple SPs

### 5.4 Establishing and Managing Federated Identities
#### 5.4.1 Introduction
#### 5.4.2 Federation Using Out-of-Band Account Linking
#### 5.4.3 Federation Using Persistend Pseudonym Identifiers
#### 5.4.4 Federation Using Transient Predonym Identifiers
#### 5.4.5 Federation Termination

### 5.5 Use of Attributes

## 6 Extending and Profiling SAML for Use in Other Frameworks
### 6.1 Web Service Security (WS-Security)
### 6.2 eXtensible Access Control Markup Language (XACML)
