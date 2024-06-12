# Changelog

All notable changes to the Public API will be documented in this file.
The changelog has been tracked since March 15, 2024. Changes prior to this date are not documented here.

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
