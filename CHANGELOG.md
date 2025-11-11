# Changelog

All notable changes to the Public API will be documented in this file.
The changelog has been tracked since March 15, 2024. Changes prior to this date are based on the git log of the project.

## Update November 11th 2025
### Added
- `GET` `BillableAvailability` is now officially available (VV-8569)
- `GET` `BillableOperation` has a new `executedBy` include to retrieve the user who executed the operation (VV-8642)
- `GET` `Appointment` has a new `billing` include which exposes billing information for the appointment and the schedule it belongs to (VV-8710)

## Release October 28th 2025

### Changed
- `POST` `Employer` takes (a lot) less time to complete, further improvements are coming (VV-8556)
- `POST` `ContactPerson` no longer mixes up `firstName` and `lastName` properties (VV-8377)

### Documentation
- `POST` `OrganizationalUnit` request body now correctly shows `dateStart` and `dateEnd`, these are removed from `company` (VV-8738)


## Release October 2025

### Added
- `POST` `User` endpoint for creating `Employee` users (VV-8080)
- `GET` `DossierContent` endpoint for retrieving `Upload` content (VV-7998)

### Changed
- `GET` `Task` - removed 'templateId' property from response (VV-8391)
- `POST` and `PATCH` `OrganizationalUnit` - fixed misleading validation error for `visitAddress` (VV-8395)
- `POST` and `PATCH` `EmployerContract` now allows setting `outgoingDossiers` (VV-8257)
- `PATCH` `Dossier` endpoints no longer allow `employmentId` and `employmentKey` properties to be set (VV-7704)
- `POST` `OrganizationalUnit` now correctly stores the `payrollTaxIdentificationNumber` (loonheffingsnummer) property (VV-8423)
- `PATCH` `Dossier` - some endpoints now allow nulling certain dates (VV-7703)
- `GET` `LinkedUser` now includes the `toUser` and `fromUser` relations by default (VV-8201)
- `PATCH` `Dossier` - `illness` and `illness-plus-zwerd` endpoints now allow updating the `pa` and `pva` properties (VV-8330)
- `GET` `Appointments` endpoint received performance improvements for large datasets (VV-8519)
- `PATCH` `User` endpoints now allow changing `welcomeEmailSent` (VV-7712)
- A mechanism was implemented to add `Deprecated` and `Sunset` headers to endpoints that are deprecated or scheduled for removal (VV-8140)

### Documentation
- `GET` `EmploymentType` endpoint now returns the correct schema for the `meta` response property (VV-8572)
- The API-management version of the documentation shows optional `Deprecated` and `Sunset` headers for endpoints that are deprecated or scheduled for removal (VV-8139)


## Release September 2025

### Added
- `PATCH` `AbsenceCourse` can now update `externalKey` (VV-8195)

### Changed
- `Organizational Unit` property `company` is now nullable when the OU is not a legal entity (VV-8358)
- Removed property `absenceCourse` from `PATCH` and `POST` `DossierTask`, it is only for internal use (VV-8251)
- `GET` `DossierTask` has a new `billableOperation` include (VV-8337)
- `POST` and `PATCH` `EmployerContract` property `accountNumber` now actually accepts strings (VV-8276)


## Documentation update August 22nd 2025

### Documentation fixes
- Added 'modules' to `POST` and `PATCH` `EmployerContract` endpoints (VV-8310)
- Added 'operations' to `Task` and `DossierTask` resources (VV-8310)
- `POST` `DossierTask` response is now a DossierTask (VV-8310)


## Release August 2025

### Changed
- `operations` includes have been added to `GET` `Task` and `GET` `DossierTask` endpoints (VV-8229)
- `PATCH` endpoints for `Dossiers` now allow updating the `externalKey` property (VV-7705)
- WGA dossiers can now be created for employments that have ended (VV-8205)
- Fixed spelling for status property "cancelled" for `GET` `DossierTask` endpoint (VV-8219)

### Documentation fixes
- Removed trailing 's' in the documentation for API routes (VV-8203):
  - `GET` `DossierType` endpoint
  - `PATCH` `ContactPerson` endpoint

## Release July 2025

### Added
- New `GET` `LinkedUsers` endpoint (VV-7540)
- New `POST` `LinkedUsers` endpoint (VV-7527)
- New `GET` `ContactPerson` endpoint (VV-7512)
- New `DELETE` `User` endpoint (VV-7297)
- New `PATCH` `Dossier` endpoint for the `illness-plus-zwerd` dossier type (VV-7520)
- New `PATCH` `Dossier` endpoint for the `occupational-expert` dossier type (VV-7830)

### Changed
- `PATCH` `Employee` now allows changing the `externalKey` property (VV-7997)
- `GET` `DossierTask` now allows filtering by dossier (VV-7743)
- `GET` `Employee` now allows including the country as part of the address via the `addresses.country` include (VV-6586)
- `POST` `EmployerContract` validation errors fixed (dates + contractNumber) (VV-7840)
- `AbsenceCourse` and `Dossier` resources should now return enums in kebab-case instead of snake_case (VV-8024)
- Additional enum options were added for `ContactPerson.type` (VV-7324)

### Documentation fixes
- paths for `UploadType` and `DocumentType` have been corrected; a trailing 's' has been removed (VV-8112)
- `GET` `EmployerContract` had `includes` added for `organizationalUnit` and `partnership` (VV-8026)
- `POST` `EmployerContract` now returns the `organizationalUnit` property in its response (VV-8026)
- `GET` `ContractType` now shows the `code` filter in the OpenAPI documentation (VV-8068)
- The `Employment` resource documentation now correctly shows that `employmentNumber` is an integer (VV-8068)

## Update June 2025-06-27

### Changed
- Fixed some documentation issues and oversights that were reported
- Be aware: the documentation references a new `GET` `LinkedUsers` endpoint, this is not yet available on the `staging` environment. It will be part of the next release.

## Release June 2025

### Added
- New `GET` appointment endpoint (VV-5613)
- New `PATCH` endpoints for newly introduced dossier types (VV-7238)
- New `PATCH` endpoint for `Pregnancy` dossier (VV-7173)
- New `employee` includes added to `GET` `Employment` and `EmploymentContract` endpoints (VV-7758)
- New `employee` include added to `GET` `BillableOperation` endpoint (VV-7565)

### Changed
- Fixed OpenAPI description of `arbosServiceId` for `POST` `Employer` endpoint (VV-7806)


## Release May 2025

### Added
- New `POST` endpoints have been introduced for several new dossier types (VV-7237)
- New `PATCH` `ContactPerson` endpoint (VV-7041)
- `PATCH` User now allows updating the `externalKey` property (VV-7254)
- `GET` User now returns the `ssoKey` property (VV-7298)

### Changed
- Validation of the OpenAPI documentation has been added to our CI pipeline (VV-7300)
- Various documentation updates and improvements

## Release April 2025

### Changed

- `POST` `Employee` now correctly accepts strings for the `employeeNumber` field as indicated in the documentation. (VV-7197)
- Documentation: GET endpoint documentation have been improved in order to make it easier to generate a client based on the OpenAPI documentation. (VV-7013 / VV-7380)
- Documentation: all endpoints have had an `operationId` property added to them. This field is used internally for API Management purposes. (VV-7161)
- Documentation: several GET endpoints now use enums for their `sort` and `include` parameters. (VV-7283)

### Added

- `POST` `ContactPerson` has been introduced to allow adding contact persons to OUs and Employers. (VV-7040)


## Release February 2025

### Added

- Implemented `GET` method for `Users` endpoint (VV-2623)
- Added employer relation to `GET BillableOperation` endpoint (VV-6496)

### Changed

- Improved `POST/PATCH` methods for `OrganizationalUnit` (VV-7082)
- OpenAPI docs: Added field requirements for `Employer` (VV-7012)
- Documentation improvements for APIM + OpenAPI (VV-6809)

### Fixed

- Fixed incorrect scope on `GET DossierContent` requests (VV-7083)



## Release January 2025

### Added

- Added `Communications`, `ContactPerson`, and `Addresses` to `GET/POST/PATCH OrganizationalUnit` endpoints (VV-4212)
- Implemented `POST` method for `User` to send a welcome email (VV-6782)

### Changed

- Updated `GET/POST/PATCH OrganizationalUnit` endpoints to include supervisors (VV-4858)
- Public API documentation fixes (VV-6443)

### Fixed

- Fixed `Patch Dossier Uploads` issue where `forBothParties` property caused an error after validation (VV-6155)



## Release December 2024

### Added

- Implemented `POST` method for `UserAuthorizations` endpoint (VV-6054)

- Implemented `PATCH` method for `DossierTask` endpoint (VV-4038)

- Implemented `PATCH` method for `User` endpoint (VV-2625)

### Changed

- Improvements on `POST` and `PATCH` methods for `EmployerContracts` endpoint (VV-5898)

- Fixed `POST AbsenceCourse` only accepts 1 AbsenceCourse per day, per dossier (VV-6450)

## Release November 2024

### Added

- Implemented `POST` method for `WGA-Dossier` endpoint (VV-6202)

- Implemented `PATCH` method for `WGA-Dossier` endpoint (VV-6223)

- Added `code` field in `Operations` endpoints (VV-6270)

- Implemented `POST` method for `User` endpoint (VV03080)

### Changed

- `POST` method of `Employer` should accepts `contract.incomingDossiers` (VV06147)

- Improvements on filtering `employerId` and `parent` on `GET OrganizationalUnit` (VV-6145)

## Release October 2024

### Added

- Implemented `GET` method for `Task` endpoint (VV-5926)

- Implemented `POST` method for `DossierTask` endpoint (VV-4037)

### Changed

- Specify formats in OpenAPI Specifications (VV-5700)

- Add UUID to `ContactPerson` (VV-5928)

## Release 2024-09-18

### Changed

- `GET` `BillableOperation` now returns (soft-)deleted records when the 'withDeleted' filter is applied or if one of the new 'dateDeleted' filters is used (VV-4995)
- OpenAPI documentation improvement: many Resources now correctly indicate that the string 'id' property is of format "uuid" (VV-5700)

## Release 2024-09-04

### Changed

- `GET` `Employee` now has an 'employments.employmentContracts' include to retrieve full employment details (VV-5889)
- `GET` `Employee` - The `EmployerPersonAddress` resource now includes the address type (VV-5472)
- `GET` `Employer` - The `ContactPerson` resource now includes a `fullSalutation` property (VV-5472)
- `POST` `Employer` allows specifying the `contract.status` (VV-5472)
- `PATCH` `OrganizationalUnit` now supports updating 'externalKey' (VV-5911)
- `PATCH` `Employer` has had its documentation updated, it previously (incorrectly) included a `contract` property (VV-5472)
- Date filters that accept a 'date-time-offset' can now parse the 'Z' time zone offset notation (VV-5856)
- Various occurrences of the UWV `riskCode` have had their documentation updated to reflect the correct type (string) (VV-5742)

## Release 2024-08-28

### Added

- New endpoints
  - `PATCH` method for `Dossier` `Birth Leave` endpoint. (VV-5824)
  - `PATCH` method for `Dossier` `Paid Parental Leave` endpoint. (VV-5722)

## Release 2024-08-21

### Added

- New endpoints
  - `PATCH` method for `Dossier` `Zwerd` endpoint. (VV-5450)
  - `PATCH` method for `Dossier` `Spoor2` endpoint. (VV-5450)
  - `PATCH` method for `Dossier` `Preventive` endpoint. (VV-5450)
  - `PATCH` method for `Dossier` `Medical Preventive` endpoint. (VV-5450)

### Changed

- Changes to `EmploymentResource` to return correct `employmentEndReason` data (VV-5676)

## Release 2024-08-07

- New endpoints
  - `DELETE` method for `DossierContent` endpoint for `Uploads`. (VV-5732)
  - `PATCH` method for `DossierContent` endpoint for `Uploads`. (VV-5481)

## Release 2024-08-05

- New endpoints
  - `DELETE` method for `DossierContent` endpoint for `Documents`. (VV-5733)

### Changed

- PublicAPI XSS protection is causing server errors on Azure (VV-5766)

## Release 2024-08-02

- New endpoints
  - `DELETE` method for `DossierContent` endpoint for `Notes`. (VV-5698)

### Changed

- `GET` `OrganizationalUnit` now supports dateCreated/dateUpdated filters (VV-4994)
- `GET` `Dossier` now supports dateCreated/dateUpdated filters (VV-4997)
- `GET` `Employee` now supports dateCreated/dateUpdated filters (VV-4993)
- Endpoints now have XSS protection (Removal of script tags) on all string fields (VV-5265)
- `POST` `Dossier` no longer allows the creation of dossier types that are not enabled for that partner (VV-5576)
- `GET` `Dossier` no longer allows incorrect includes (VV-5392)
- `OrganizationalUnit` dateStart/dateEnd are now returned in ISO8601 date formats (VV-5726) 

## Release 2024-07-23

### Added

- New endpoints
  - `PATCH` method for `DossierContent` endpoint for `Document` (VV-5603)
  - `PATCH` method for `Employment` (VV-5401)

### Changed

- `GET` `OrganizationalUnitResource` now supports dateCreated/dateUpdated filters (VV-5670)

## Release 2024-07-17

### Added

- New endpoints
  - `DELETE` method for `DossierExternalResource` endpoint. (VV-5649)
  - `PATCH` method for `DossierExternalResource` endpoint. (VV-5510)
  - `DELETE` method for `Employment` endpoint. (VV-5635)
  - `DELETE` method for `EmploymentContract` endpoint. (VV-5630)

### Changed

- `PATCH` `Employer` now allows updating 'externalKey' (VV-5644).

## Release 2024-07-10

### Added

- New endpoints
  - `PATCH` method for `DossierContent` endpoint for `Notes`. (VV-5477)
  - `DELETE` method for `Dossier` endpoint. (VV-5539)

### Changed

- Date filters for `GET` `AbsenceCourse` and `EmployerContract` now support ISO8601 date formats (VV-5231)
- `BirthLeave` and `PaidParentalLeave` dossier resources now correctly return UUIDs for `id` fields. (VV-4045 + VV-4046)

## Release 2024-07-03

### Added

- New endpoints
  - `PATCH` method for `EmploymentContract` endpoint. (VV-5264)
  - `GET` method for `ArboService` endpoint - this is a supporting endpoint for the `POST` and `PATCH` `Employer` endpoint. (VV-5520)

### Changed

- The `EmployerDivisionResource` now returns datetime strings for `dateCreated` and `dateUpdated` instead of just dates. (VV-5561)
- The `PublicApiOrganizationalUnitResource` now includes `dateCreated` and `dateUpdated` fields. (VV-5561)
- Documentation improvements for several Resources regarding their `dateCreated` and `dateUpdated` fields. (VV-5561)

## Release 2024-06-26

### Added

- New endpoints
  - `GET` method for `DossierContent` endpoint for `Uploads`. (VV-5418)
  - `GET` method for `DossierContent` endpoint for `Documents`. (VV-5417)
  - `DELETE` method for `EmployerContract` endpoint. (VV-5513)

### Changed

- `POST` method for `Employment` endpoint now supports `employmentTypeCode`. (VV-5291)
- `POST` method for `EmploymentContract` endpoint now supports `employmentTypeCode`. (VV-5351)
- Documentation improvements for `DossierNoteResource`. (VV-5496)
- Documentation fixes for `EmployerServiceContract` and `EmployerContract` resources (VV-5496)
- Documentation fix for Pregnancy Dossier schema (VV-5495)
- Documentation fix for `normHours` on `CompanyResource` - it is now a `number` instead of an `int` (VV-5417)

## Release 2024-06-21

### Added

- New endpoints
  - `PATCH` method for `EmployerContracts` endpoint. (VV-5257)
  - `GET` method for `Dossier` `PaidParentalLeave` endpoint. (VV-5422)
  - `GET` method for `Dossier` `Pregnancy` endpoint. (VV-5464)

## Release 2024-06-19

### Added

- New endpoints:
  - `POST` method for `DossierContent` endpoint for `Uploads` - allows uploading files to a dossier. (VV-5317)
  - `GET` method for `DossierContent` `Note` endpoint. (VV-5416)
  - `GET` method for `Dossier` `Birth Leave` endpoint. (VV-5412)

### Changed

- Fixed a problem with the `GET` `Employer` endpoint when using the `contactPersons.details` filter. (VV-5204)
- The `POST` `Token` method used to obtain a bearer token now accepts UUIDs for 'client_id' (VV-5140)
- Admin portal: the 'Applications' page now shows UUID instead of numerical ID for 'client_id' (VV-5407)

## Release 2024-06-12

### Added

- New endpoints:
  - `POST` method for `DossierContent` endpoint for `Documents` - allows adding documents to a dossier. (VV-5182)
  - `GET` method for `DossierExternalResource` endpoint. (VV-5278)
  - `GET` method for `UploadType` endpoint - this is a supporting endpoint for the `POST` `DossierContent` endpoint. (VV-5315)

## Release 2024-06-05

### Added

- New endpoints:
  - `GET` method for `Dossier` endpoint. (VV-5107)
  - `GET` method for `Dossier` `Spoor 2` endpoint. (VV-5107)
  - `GET` method for `Dossier` `ZWERD` endpoint. (VV-5107)
  - `GET` method for `Dossier` `Medical Preventive` endpoint. (VV-5107)
  - `GET` method for `Dossier` `Preventive` endpoint. (VV-5107)

### Changed

- Admin portal: QoL improvement which allows the user to "select all" and to modify scopes on an existing 'application' (VV-5253)
- Fixed validation for `PATCH` `Employee` endpoint - resolves an issue which required an OU to be provided when updating an employee. (VV-5310)

## Release 2024-05-29

### Added

- New endpoints:
  - `POST` method for `Employment`. (VV-4965)
  - `GET` method for `EmploymentContract` endpoint. (VV-5217)
  - `GET` method for `Employment` endpoint. (VV-5239)
  - `POST` method for `DossierExternalResource` endpoint - allows adding links to a dossier, for example to access related resources in the customer's application. (VV-5099)
  - `POST` method for `DossierContent` endpoint for `Notes` - allows adding notes to a dossier. (VV-4966)
  - `GET` method for `DossierDocumentType` endpoint - this is a supporting endpoint for the `POST` `DossierContent` endpoint. (VV-5186)

### Changed

- The `GET` `Employer` endpoint has had `dateUpdated` filters added to allow polling for changes. (VV-4992)
- (most) existing POST endpoints have been updated to return an HTTP status code of `201 - Created` instead of `200 - OK`. (VV-5214)

## Release 2024-05-22

### Added

- New endpoints:
  - `GET` method for `DossierNoteType` endpoint - this is a supporting endpoint for the upcoming `POST` `DossierContent` endpoints. (VV-5092)
  - `GET` method for `EmployerContracts` endpoint. (VV-4047)
- The `POST` method for the `Employee` endpoint now allows setting an External Supervisor on the employee's employment. (VV-4222)

## Release 2024-05-15

### Added

- New endpoints:
  - `POST` method for `Dossier` endpoint to support Birth Leave dossiers. (VV-4074)
  - `DELETE` method for `Employee` endpoint. (VV-5067)
  - `DELETE` method for `AbsenceCourse` endpoint. (VV-5178)
  - `GET` method for `DossierSection` endpoint - this is a supporting endpoint for the upcoming `POST` `DossierContent` endpoint. (VV-5091)

### Changed

- OpenAPI documentation minor corrections. (VV-5190)

## Release 2024-05-08

### Added

- New endpoints:
  - `POST` method for `EmployerContract` endpoint to allow adding new (or past) employer contracts for employers. (VV-4912)
  - `POST` method for `Dossier` endpoint to support Paid Parental Leave dossiers. (VV-4082)

### Changed

- Sending a null value for an 'id' (UUID) field in a POST request will no longer result in a server error (VV-5130)

## Release 2024-05-01

### Added

- New endpoints:
  
  - `POST` method for `EmploymentContracts` endpoint to allow adding new (or past) employment contracts for employees. (VV-4969)

- As requested:
  
  - Added `dateUpdated` sorting option to `GET` `Billable-operation` endpoint. (VV-5075)

### Changed

- Using an invalid token should no longer return a 'server error' when proxying through 'input' (VV-5005)

## Release 2024-04-24

### Added

- New endpoints:
  - `POST` method for `Dossier` endpoint to support pregnancy dossiers. (VV-4073)
  - `DELETE` method for `Employer` endpoint. (VV-5060).

### Changed

- Improved OpenAPI documentation - corrected dossier/task route + improved Employee resource documentation. (VV-5063)

## Release 2024-04-22

### Added

- New endpoints:
  - `DELETE` method for `OrganizationalUnit` endpoint. (VV-4982).

### Changed

- Improved validation for PATCH employee lastNamePreference (VV-5048).
- Updated OpenAPI documentation for publicAPI (VV-5028).
- Billable operation documentation fix (VV-5017).

## Release 2024-04-17

### Added

- New endpoints:
  - `GET` method for `Operation` endpoint.
  - `GET` method for `ContractType` endpoint.
  - `POST` method for `Dossier` endpoint, supporting multiple dossier types such as Preventive, Medical Preventive, Spoor-2, and ZWERD.
  - `GET` method for `Partnership` endpoint.
  - `GET` method for `Billable-operation` endpoint.
  - `GET` method for `Dossier-task` endpoint.

### Changed

- Enhanced `GET` `AbsenceCourse` to exclude soft-deleted employments.
- Implemented validation for `namePreference` in both `POST` and `PATCH` requests for employee data.
- Improved documentation by removing Dutch translations from legal forms enum.
- Various other documentation fixes to improve accuracy and consistency.

---

*The list below is auto-generated by using the `git log`*

## Release March 2024

### Added

- Implemented `GET` method for `ContractType` endpoint

- Implemented `GET` method for `Operations` endpoint

- Implemented tests for `PATCH` method of `OrganizationalUnit` endpoint

- Implemented `GET` method for `ServiceType` endpoint

- Implemented `GET` method for `ExternalSupervisor` endpoint

### Changed

- Validation on `namePreference` and `lastNamePartner` for `POST` and `PATCH` `Employee` endpoint
- Exclude soft-deleted employments in the `AbsenceCourse` endpoint

---

## Release February 2024

### Added

- Implemented `PATCH` method for `OrganizationalUnit` endpoint.
- Implemented `PATCH` method for `Employer` endpoint
- Implemented `Health` endpoint.

### Changed

- Added property `organizationalUnitTypeKey` to `POST` `OrganizationalUnit`.
- Fixed issues with `POST` and `PATCH` methods in `Employee` endpoint.

---

## Release January 2024

### Added

- Implemented`GET` method for `AbsenceReason` endpoint.
- Implemented `POST` method for `OrganizationalUnit` endpoint.

### Changed

- Validation changes for `POST` `Employer`.

---

## Release December 2023

### Added

- Implemented`GET` method for `OrganizationalUnitType` endpoint.
- Implemented `POST` method for `Employee`endpoint
- Implemented `PATCH` method for `AbsenceCourse` endpoint
- Implemented `GET` method for `Employer` endpoint
- Added dossier officer and company doctor searchability in `Employer`.

### Changed

- Allowing address-extensions on `POST` `Employee`.

---

## Release November 2023

### Added

- Implemented `GET` method for `Employee`.
- Implemented`POST` method for `AbsenceCourse`.
- Implemented the OAuth2.0 token-based access
- Implemented `POST` method for `Employer`

### Changed

- Refactoring for `Arbo-roles` and `Employer-roles`.

---

## Release October 2023

### Added

- Integrated employee profiles into API output for absence and employee data.
- Implemented`GET` method for `EmployerDivision`.

### Changed

- Fixed incorrect validation for user event `date_start`/`date_end`.

---

## Release September 2023

### Added

- Implemented`GET` method for `DossierOfficer`.
- Implemented `GET` method for `CompanyDoctor`.
- Implemented `GET` method for `AbsenceReason`.
- Implemented`GET` method for `EmploymentType`.
- Implemented`GET` method for `OrganizationalUnit`.

### Changed

- Enhanced `GET` method for `AbsenceCourse`.
- Improved tests and implementation for `GET Authorized Users`.

---

## Release July & August 2023

### Added

- Implementation of API Testing Framework.

### Changed

- Updated OpenAPI documentation URL for User endpoint.
- Fixed duplicate returns in `AbsenceCourses` Public API.

---

## Release June 2023

### Changed

- Adjusted Public API user event to not require child-level.

## Release May 2023

### Added

- Implemented `GET` method for arbo_roles
- Implemented `GET` method for employer_roles

---

## Release March 2023

### Added

- Implemented `EVENT` for user. 
- Implemented `GET` method for absence courses.
