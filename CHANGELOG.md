# Changelog

All notable changes to the Public API will be documented in this file.
The changelog has been tracked since March 15, 2024. Changes prior to this date are not documented here.

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
-  Endpoints now have XSS protection (Removal of script tags) on all string fields (VV-5265)
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
