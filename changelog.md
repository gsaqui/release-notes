# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)

## Links
- [Platform](#platform)
- [Back office](#back-office)
- [Chameleon Sportsbook](#Chameleon-Sportsbook)


# Platform

## [6.6.422] - 2023-02-02

### Added
- Added Paypal as a payment service (deposit & withdrawal) 
- Added API to get the KYC status of the Person
- On detection of duplicate account, create back office note on both accounts
- Adding configuration for Massachusetts future release
- Added API to limit the amount of time a Person can be on the site in 24 hours

### Fixed
- Handling identical bet create message (stopping replay) 
- Fixed an issue with the hashing the last 4 digits of SSN
- Stopped making calls to support system when logged out API is called 
- Updated IdComply integration to pass Person ID opposed to email


# Back Office

## [3.11.11] - 2023-02-02

### Added
- Do not allow editing of email address in the Back office 
- Add filter to be able to filter out Test Accounts in the financial reports
- Initial display work to show jurisdiction on the Person pages



# Chameleon Sportsbook