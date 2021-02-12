# Opolis API (Proposed)

All documents and data associated with a member's Opolis membership and benefits are automatically stored in a private textile bucket encrypted with the member's public key. Members can retrieve data documents at will using textile's `hub` tool or other tools that use the Textile SDKs.

## Access to documents
* Documents are stored in the `docs` directory of the bucket.
* The file names of all possible files are standardized and defined in this spec to enable the use of automated tools to access and process the documents.

## Access to data
* Data is stored in the `data` directory of the bucket.
* Each field of data is stored in it's own file.
* The data directory is hierarchical so that related data is segregated.
* The data directory hierarchy and field file names are standardized and defined in this spec. This enables the use of automated tools to access and process the data.

## Interoperability
This storage scheme is intended to offer a high degree of flexibility for integration of 3rd party products with Opolis, and yet provide a high level of end-to-end data security. Targetted integrations include:
- document sharing using NuCypher
- life event management with the Endowl estate planning app

## Archiving
Opolis periodically archives all data and documents using Filecoin. Members have access to these archives, but have the ability to create their own Filecoin archives or use other online or offline archiving systems such as dropbox.

## Data Management Application
[FUTURE] Members update any data associated with their membership through an application that writes the data directly to the Textile bucket. Opolis's backoffice systems automatically detect and process any updates the member makes through this mechanism. If the member is allowed to make updates directly to the Textile bucket, the backoffice system also monitors for invalid data. It notifies the user, and until the offending data is corrected, it relies on the most recent version of the data that was correct.

## `docs` Directory Layout
TBD

## `data` Directory Layout
- MemberData
  - Name
  - Address
  - Contact information
  - SSN
- MemberFamilyData
  - InstanceN `multiple instances allowed`
    - Name
    - Relationship
    - Address
    - SSN
- MemberLLCData
  - Name
  - EIN
  - Address
  - State Registration documentation
- Benefits
  - LifeInsurance
  - HealthInsurance
  - LongTermDisability
  - ShortTermDisability
  - Vision
  - Dental
  - 401k
  - FsaAccount
  - HsaAccount
- Payroll
  - MemberInvoices
  - PayStubs
  - PayrollWithholding
  - TaxData
- ClientInvoices
  - Date
  - DueDate
  - Amount
  - LineItems
  - ID
- ClientInformation
  - Name
  - Address
  - PhoneNumber
- Notes


[Submission for the Build an Open API spec bounty](https://www.ethdenver.com/post/opolis) (Bounty #4)
