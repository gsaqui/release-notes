# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)

## Links
- [Platform](#platform)
- [Back office](#back-office)
- [Chameleon Sportsbook](#Chameleon-Sportsbook)


# Platform
## [6.6.427] - 2023-03-16
### Added
- Second iteration of bet performance increases
- Signup bonus when a person passes KYC
- Showing paypal as a preferred payment option after a customer deposits
- Add RabbitMq topology changes for Massachusetts
- Hard limit api updates
- Api for PaySafe bank transfer deposits
- Adding Jurisdiction header - needed for multi-state

### Fixed
- Bet information in slack creating two entries and in wrong currency



## [6.6.425-4] - 2023-03-02
### Added
- First iteration of bet performance increases
- Pushing all bet notes to the BO
- API to allow customers to disable their account.  This is needed as the customer can currently delete their account which causes problems in both SB and FU back offices.
- Accept Geolocation tokens
- Block the `Shipping Address` shown on PayPal deposits
- Rabbit MQ topology changes
- Adding different urls for IDComply based on the state
- 
### Fixed
- Paysafe rejecting single quotes in a persons name
- PayPal withdrawals being rejected for certain floats


## [6.6.424-3] - 2023-02-16
### Fixed
- Bonusing through the backoffice was debiting the user wallet balance by 50 USD
- Very slow query causing the background queues to overload and then the query max the cpu of the database

## [6.6.424] - 2023-02-16
### Added
- Created api for betbuilder
- Updated async betting api to only include one reason why the bet was rejected  
- Add Responsible Gambling deposit limit of 2500 for people under 26

### Fixed
- Store phone in user address for existing users
- Rounding to 2 digits in the user wallet activity endpoint
- Fix an issue with race condition when attempting to withdraw by the same person


## [6.6.423-4] - 2023-02-13

### Fixed
- Changing identifier sent to IDComply to use KeyCloak ID instead of customer internal ID
- Fix max withdrawal amount being blocked

## [6.6.423-2] - 2023-02-11

### Fixed
- Wrapped atom cache around bonus conversion, so it can only happen once

## [6.6.423] - 2023-02-10

### Fixed
- Fixing the order that wallet caches are applied
- Force clearing of wallet caches



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

## Frontend [2.1.69]

### Added

- Adding Stake Factor Trading Group and Cohort columns to Market Activity
- Bulk Credit
- Test Account Filter on Wagering Activity
- Add site_id in all the FE calls
- Backoffice Search Update Basic Search API 
- Compliance Reporting
- Change default credit/debit amount back to 50
- Use userId(customerId) for search and revert personalId page 
- Dark mode proof of concept
- Update WL for betr
- Wallet tab Export XLS 
### Fixed

- adding bet notes in BO is bugged (incorrect username) and unable to add bet notes in general
- newly created user notes do not link with note_user table
- [Betr-US] Bonus being granted not actually being a bonus but a debit from the user wallet
- fix pending withdrawals to match the mock
- Withdrawal data not being reflected in the back office
- Form Submission: Unable to access Empty Competitions in Market Management

## Frontend [2.1.67]  Api [3.11.12.1] - 2023-02-16 

### Added

- Change Betr-OH to Betr
- Change default credit/debit amount back to 50
- Test Account Filter on Customer Sportsbook Performance
- Adding Stake Factor Trading Group and Cohort columns to Market Activity
- Test Account Filter on Wagering Activity
- Bulk Credit
- Each Way Terms in Market Management
- Wallet tab Export XLS

### Fixed

- Adding bet notes in BO is bugged (incorrect username) and unable to add bet notes in general
- Unable to access Empty Competitions in Market Management
- Crediting an account prod back office
- Withdrawal data not being reflected in the back office
- Newly created user notes do not link with note_user table

## [3.11.11] - 2023-02-02

### Added
- Do not allow editing of email address in the Back office
- Add filter to be able to filter out Test Accounts in the financial reports
- Initial display work to show jurisdiction on the Person pages


# Chameleon Sportsbook
