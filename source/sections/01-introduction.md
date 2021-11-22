TODO

- [] Add application-level security
- [] HITRUST decision
- [] Removed BAA from the introduction. Discuss with our legal team about the procedure.
- [] Add aspects related to ePHI and Observability.
- [] Inception Quality Management System perhaps in Github with Github PR for follow up.

# 1. Introduction

Inception Health, Inc ("Inception") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Partners and Affiliated Healthcare Systems (Partners). As providers of compliant, hosted infrastructure used by the Partners, Inception strives to maintain compliance, proactively address information security, mitigate risk for its Partners, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by Inception to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for Inception Partners.

Inception provides secure and compliant cloud-based platform that serves our Partners. Inception leverages a cloud-native infrastructure hosted in Amazon Web Services to deploy, host, and scale custom developed applications, configured databases, and distributed data lakes. Inception manages both the the infrastruture and the application stack. Inception does have insight and access into application level data and, as such, does have the ability to secure or manage risk associated with application level vulnerabilities and security weaknesses. Inception makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of our Partners data through network (firewalls, dedicated IP spaces, etc) and server settings (encryption at rest and in transit, OSSEC throughout the Platform, etc).

## 1.2 Compliance Inheritance

Inception provides compliant cloud-native infrastructure and application stack for its Partners. Inception has been through a HIPAA compliance audit by a national third-party compliance firm to validate and map organizational policies and technical controls to HIPAA rules. Inception's company policies, procedures, and technologies are not HITRUST Certified yet. Current production systems on our cloud-native platform are included in Inception's third-party audits (HITRUST certification not included yet).

In providing infrastructure and managing security configurations that are a part of the technology requirements that exist in HIPAA and HITRUST, as well as future compliance frameworks, Datica manages various aspects of compliance for Customers. The aspects of compliance that Datica manages for Customers are inherited by Customers, and Datica assumes the risk associated with those aspects of compliance. In doing so, Datica helps Customers achieve and maintain compliance, as well as mitigates Customers' risk.

~~Datica does not act as a covered entity. When Datica does operate as a business associate (not a subcontractor), Datica does not interface with users to obtain or provide access to ePHI. Access to ePHI is through our customers' applications.~~

## 1.3 Inception Organizational Concepts

The physical infrastructure environment is hosted at [Amazon Web Services](https://aws.amazon.com/) (AWS). The network components and supporting network infrastructure are contained within the AWS infrastructure and managed by AWS. Inception does not have physical access into the network components. The Inception environment consists of serverless lambda function; Python and Javascript applications; PostgreSQL Aurora and DynamoDB database servers hosted in AWS RDS; Honeycomb.io logging platforms; Docker containers; and developer tool servers running on Linux Ubuntu managed through AWS EC2 instances.

Within the Inception Platform on AWS, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, APIs, log servers, etc. Inception assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption. THis is not the case for Telemtery and Observability data where ePHI information is prohibited and strictly reviewed.

It is the responsibility of Inception to restrict, secure, and assure the privacy of all ePHI data at the Application Level that are hosted and managed by our services. ePHI hosted and managed by other parties, even though connected, exchanged or transmitted by other parties including approved third-party under a Business Associate Agreement (BAA) and Partners IT, are not considered part of our platform as it is not under the purview of Inception.

The data and network segmentation mechanism are managed by a combination of separate accounts through AWS Control Tower and segmentation of data across dedicated Virtual Private Clouds for ePHI and other domains, e.g Bounded Contexts.

~~Additionally, IPtables is used on each server for logical segmentation. IPtables is configured to restrict access to only justified ports and protocols.~~

Inception has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. 

The environment is configured so that data is transmitted from the API Gateways to the application servers over a TLS encrypted session. All Application Programming Interface (APIs) that are public facing are secured and managed through AWS API Gateway. Remote access to internal servers is not accessible except through the API Gateway.

The database servers and the data lake repositories stored in AWS S3 buckets, where the ePHI resides, are located on a separate AWS account (named Data Lake Account). Access to the databases and the S3 buckets are restricted to a limited number of personnel and strictly controlled to only those personnel with a business-justified reason. 

All components built, coded, and maintained by Inception including operating systems and containers are tested end-to-end for usability, security, and impact prior to deployment to production through a Continious Deployment and Continious Integration pipeline.

## 1.4 Requesting Audit and Compliance Reports

Inception, at its sole discretion, shares audit reports, including ~~its HITRUST reports and~~ Corrective Action Plans (CAPs), with Partners on a case by case basis. All audit reports are shared under explicit NDA in Inception format between Inception and party to receive materials. Audit reports can be requested by Inception workforce members for Partners or directly by Inception Partners.

The following process is used to request audit reports:

1. Email is sent to melek.somai@froedtert.com. In the email, please specify the type of report being requested and any required timelines for the report.
2. Inception staff will log an issue with the details of the request into the Inception Quality Management System. The Inception Quality Management System is used to track requests' status and outcomes.
3. Inception will confirm if a current NDA is in place with the party requesting the audit report. If there is no NDA in place, Inception will send one for execution.
4. Once it has been confirmed that an NDA is executed, Inception staff will move the issue to "Under Review".
5. The Inception designated Security Officer or Privacy Officer, in the interim the Chief Technology Officer, must Approve or Reject the Issue. If the Issue is rejected, Inception will notify the requesting party that we cannot share the requested report.
6. If the issue has been Approved, Inception will send the customer the requested audit report and complete the Quality Management System issue for the request.

## 1.5 Version Control

Refer to the GitHub repository at [https://github.com/catalyzeio/policies/](https://github.com/inception-healh/policies/) for the full version history of these policies.
