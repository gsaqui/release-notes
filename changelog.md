# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)

## Links
- [Platform](#platform)
- [Back office](#back-office)
- [Chameleon Sportsbook](#Chameleon-Sportsbook)


# Platform
## [6.6.431] - 2023-04-25
### Added
- Failed deposits do not block withdrawals
- Reworking logic around closed loop
- Adding geo session to bet_groups

### Fixed
- Create only one customer across multiple jurisdictions 
- Fix double credit bug
- Fix bonus not appearing until 1 hour after being given

### Hashes of critical files
```
21593,4a77529762784aa0db93df116a12b004,d668e663a53554ea7c4acfcf5973914ba415c56c36db497b40126c20e1d8f5b7,app/Services/AsyncApiHelperService.php
4505,64ea9c0baf798a8e180da5e3b909e3a2,a17ccf4df0fbf8171e9716192862f308caf0fcfbeb7b6775daa533d9750df865,app/Services/KeycloakService.php
54312,739af43851e7ccc73671976a3acd12c9,42481cde162bb55ffcada02a61088ded21430c9ca1450cb9aacd5e7ea86b876a,app/Services/UserService.php
58529,f6d88272cf5305ed973ecad2c78ef2fc,b78881be30546211b0d59f167903c8b72655831fa327ee8bcadc78b822a5b635,app/Services/WalletService.php
195639,cb7aaf29518b500d97ed06d71bcb0bf1,eb2f7ec48002be36cabc1a6be0797918e88e10b3b8d9306042acf6dba2a9a5c0,app/Services/Gambling/BetService.php
81349,0f7984f7b5e24fe409d803bff1c7abcc,b00d806be224b011fa2277337f91489b43bc050d4a0966c6a56ca8332ef5a34c,app/Services/Gambling/CreateBetService.php
8043,28d76bf83483c1468b1994a3f5c8e78c,4ca0e73984b9ef1b4ff11a79f3e2cd97b443c97ea02143989a9a34668a9dfad2,app/Services/Gambling/ResolveBetGroupService.php
97679,371ce4ed0c7b194a64ba5538bceda368,4ddaa186d158ecd302fb5ea369ff038ebba5e18af14701799c78db6a0204ea46,app/Services/Gambling/BetResponseService.php
37877,231b7d46bbb734cc818038abb1b25b3d,a4cedc46912386f9b55b7bd539855927c85f848b790826914ebc15516ebb3372,app/Services/Guvnor.php
19114,fec6bd2356c308b55c90becf863e6f48,d6e93b15a52a418c1cbb92a51990a12df15b550fac7f9686ffcddf8b50628a1b,app/Console/Commands/RabbitMQ/ConsumeBetUpdate.php
2819,8b149e84dd38d8454741aa710fc32209,71cda567eea295c382b9951f7db69e8aecd9a86719e774697944989059208f18,app/Console/Commands/RabbitMQ/BetCreateEmitter.php
47740,165adfd09bab8e7e88262840074a2230,9fbe8e3290fee2438a779c77ec5102b6977be9753d6cc1c485f84c84179dc2c1,app/Console/Commands/RabbitMQ/ConsumeBase.php
8245,9fdb9dfca134911cd64b295491e0af01,ffc396ed4736abe3e319f8c658002acbf5f96479eff5424014b9894242168ae8,app/Console/Commands/RabbitMQ/CreateAsyncBettingQueues.php
2938,dd3f6eee8f78a228ae88f09e1977a420,bf87196221fb390311cc3496271fd282dafb2e919a59a8e541db2495daac6af2,app/Console/Commands/RabbitMQ/BetUpdateEmitter.php
17596,958ff09eb6fc5d3662a7105703021a4d,95eebb9974cf49e426c76cf8f58e97e86332bb39dc4d75db359fde5f7eff24dd,app/Console/Commands/RabbitMQ/ConsumeBetCreate.php
20906,c0bb62338cf0507e79610fbdc9661af8,e041d63fa3cff0093b8b1f2fa88a42c2a58c60a428029e03d04fb4ef709baca0,app/Helpers/GamblingTrait.php
49061,d6b089f15032f3bcfa4de6057359d0ab,b6e651dbb513442ee31ac2a84fda36feb4c3ee91b2c08e9522bd8c6bbc785ff8,app/Models/esp/Users/User.php
13432,c5351ca41f6dc74afa1bc79bcb0f1710,7ac01abb728ffcdd6517b577347ab61828e80450a505314c9933c96d834bbd1f,app/Models/esp/Gambling/Bet.php
20257,67be82e43d4a4d5ba2ba844f662065aa,d00fee6a261eff3ef818bb50f706464fe556ee24369580f23dcc5b41480a33a8,app/Models/esp/Gambling/BetGroup.php
54359,63316cf0530d16bc3d73d698c897bd91,95570a5215e6fec1bf75c9d398b72c3db0450cc58d7f61280d8db7870679f934,app/Models/esp/Users/UserWallet.php
```

## [6.6.428] - 2023-03-30
### Added
- Jurisdiction header (feature switched off)
- Handling of encrypted geotoken (feature switched off)
- First release of multi state bet acceptance (featured switched off)
- Convert user_wallet queue to fanout exchange
- Datadog metrics for async api
- Long term self exclusion list (multi state solution)
- Trigger alert when sum of total successful deposits for an account > 1000 USD + Sum accepted stakes (bets placed, not rejected) <= 100 USD, withdrawal request for full balance

### Fixed
- Increasing speed data flowing to BO



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

## Backend [3.11.18]

## Added
- Turning on BigQuery functionality for Betr

## Backend [3.11.17]

## Added
- Improved the performance of the flow between the CSB platform and Backoffice
- Added tracking information to the logs into the whole data flow process

## Frontend [2.1.71]
## Added

- Individual Market Limits to Event Page changes
- Individual Market Limits Individual Limits Modal
- Casino Base Page
- Casino Tabs and Tables
- Casino Tabs and Tables Filters
- Casino Order Games
- Executive Summary Improvements
- Activity Overview Charts Improvements
- Activity Overview Amendments Acquisition

### Fixed

- Layout issues on smaller screen
- Unable to access Empty Competitions in Market Management
- Executive Summary FE broken - Backoffice
- Unable to access event details and markets offered for HR competitions with a special character
- Bulk Credit not leaving correct notes / Accounts not being credited when there is no Note
- BO Pending withdrawals table gets smaller or disappears  Backoffice
- TypeError showing 5.9k in 24 hours
- Selecting WL and closing the nav bar should persist after reload
- Market settlement navigation 404 error
- Getting error message when trying to add a selection on the HR Antepost (Marsh Chase)

## Frontend [2.1.70]

## Added

- Add Bonus Stake and Bonus GGR fields to the XLS Export of Wagering Activity report
- Test Account Filter on Customer Sportsbook Performance
- Change bet stop time to be directly associated with futures flag
- Separate out filters by feature on Audits Report

### Fixed

- The BO user can not finish a review when only one is displayed
- Betr - no longer able to finish review on an account
- use the base button fix button colors for darkmode
- SE and time-out missing type in compliance report - self exclusion page
- Unable to access Empty Competitions in Market Management
- WL Aggregate not applying to Security Alerts - BO
- Unable to view entries on the wallet tab and getting error message (some accounts only)
- Bulk Credit not leaving correct notes / Accounts not being credited when there is no Note

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
