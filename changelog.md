# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)

## Links
- [Platform](#platform)
- [Back office](#back-office)
- [Chameleon Sportsbook](#Chameleon-Sportsbook)


# Platform

## [6.6.424] - 2023-02-16
### Added
- Created api for betbuilder
- Updated async betting api to only include one reason why the bet was rejected  
- Add Responsible Gambling deposit limit of 2500 for people under 26

### Fixed
- Store phone in user address for existing users
- Rounding to 2 digits in the user wallet activity endpoint
- Fix an issue with race condition when attempting to withdraw by the same person



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


## [2.1.67.RC] - 2023-02-09 

### Added

- Change Betr-OH to Betr
- Change default credit/debit amount back to 50
- Test Account Filter on Customer Sportsbook Performance
- Adding Stake Factor Trading Group and Cohort columns to Market Activity
- Test Account Filter on Wagering Activity
- Bulk Credit
- Each Way Terms in Market Management
- Wallet tab Export XLS
- [Bulk Credit] Import Table API

### Fixed

- Adding bet notes in BO is bugged (incorrect username) and unable to add bet notes in general
- Unable to access Empty Competitions in Market Management
- Crediting an account prod back office
- Withdrawal data not being reflected in the back office
- Newly created user notes do not link with note_user table

# Chameleon Sportsbook
