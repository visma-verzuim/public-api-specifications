# Changelog

All notable changes to the Public API will be documented in this file.
The changelog has been tracked since March 15, 2024. Changes prior to this date are not documented here.

## Release 2024-05-08

### Added
- New endpoints:
  - `POST` method for `EmployerContract` endpoint to allow adding new (or past) employment contracts for employees. (VV-4912)
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
