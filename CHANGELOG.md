# Changelog

All notable changes to the Public API will be documented in this file.
The changelog has been tracked since March 15, 2024. Changes prior to this date are not documented here.

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
