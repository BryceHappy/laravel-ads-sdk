Change Log
==========

### 02/02/2018 - 1.2.7

#### Changed
* Added `getCampaigns()` and `getAdGroups()` to now work with paging. Google allows only 10,000 results per page. Pre-defined 5,000 per page in this SDK for safety. It will be handled automatically and give you the entire total in the response.
* Added `$filters` array within the `getCampaigns()` and `getAdGroups()`, using the `Predicate` and `setPredicates` Google Ads functionality. (Note: this currently will only use the `PredicateOperator::IN` operator.)


### 02/01/2018 - 1.2.6

#### Changed
* Updated GoogleAds API from `v201802` to  `v201809`


### 01/25/2018 - 1.2.5

#### Changed
* GoogleAds Reports now allow for advanced customization, making `reportDownload()` a public method.
* GoogleAds Reports now allow `aggregate()` to be used with multiple calls.

### 01/22/2018 - 1.2.4

#### Added
* GoogleAds: `AveragePosition` which equals `avg_position` within AdGroup Report `getAdGroupReport`.
* BingAds: `AveragePosition` which equals `avg_position` within AdGroup Report `getAdGroupReport()`.


### 01/18/2018 - 1.2.3

#### Added
* `setTargetCpa()` on Bing/Google campaigns.


### 01/17/2018 - 1.2.2

#### Changed
* Fixed bing report response once again!


### 01/17/2018 - 1.2.1

#### Changed
* Fixed Bing Report Download when download fails due to "no data in report" (now returns a empty response)


### 01/17/2018 - 1.2.0

* Overhaul of Google and Bing APIs
* Includes Google/Bing Campaign and AdGroup Management Features.
* Updated Readme with all Documentation for both Google/Bing
* Improved consistency between both Google/Bing

### 01/14/2018 - 1.1.6

#### Fixed
* Fixed new bid type method returns the correct types now.


### 01/14/2018 - 1.1.5

#### Fixed
* Added `Campaign Id` into Bing Ad Group response.


### 01/14/2018 - 1.1.4

#### Changed
* Changed Bing Ad Group status from `Active` to `ENABLED` (matching GoogleAds)
* Fetching AdGroups now use the AdGroup Response object.


### 01/14/2018 - 1.1.3

#### Added
* Google: Added `type` for `AdGroupType` in `getAdGroups()`

#### Changed
* Changed the Bid Type to always return a uniform set (`CPC`,`ECPC`,`CPA`,`CPM`)


### 01/14/2018 - 1.1.2

#### Added
* Google: Ability to check if an ad group is Enhanced CPC using `isEnhancedCpc()`
* Google: Added `ENHANCED_CPC` for bid strategy response in fetch ad groups


### 01/05/2018 - 1.1.1

#### Added
* For Google/Bing get the active bid with `getBid()` on adgroups.


### 01/05/2018 - 1.1.0

#### Changed
* Response of `adGroup` for both Google/Bing
* Request to the servers will use `AdGroupRequest`
* Response from the servers will use `AdGroupResponse`
* Bing now has edit ability (and uses the same methods as Google)
* Added new Set/Get Methods to Google/Bing


### 12/30/2018 - 1.0.7

#### Added
* Added `toCollection()` on `ReportDownload`, instead of sending back raw array, we will send back as a Collection. You can use `all()` if you want the basic array response.

#### Changed
* The default `ReportDownload` response to `toCollection()` instead of `toArray()`

### 12/29/2018 - 1.0.6

#### Added
* Console `RefreshTokenCommand`, you can now generate a refresh token and follow authentication steps for BingAds
* Command: `php artisan laravelads:token:generate --service=BingAds`
* BingAds: Added new fetch methods `getCampaigns()` and `getAdGroups()`
* GoogleAds: Added `bid_type` on `getCampaigns()`

#### Changed
* Simplified the GoogleAds/BingAds Reports and made the responses consistent with both.

### 12/29/2018 - 1.0.5

#### Added
* Console `RefreshTokenCommand`, you can now generate a refresh token and follow authentication steps for GoogleAds
* Command: `php artisan laravelads:token:generate --service=GoogleAds`

### 12/29/2018 - 1.0.4

#### Changed
* Services: `googleAds()`, `bingAds()` and `facebookAds()` methods.

### 12/28/2018 - 1.0.3

#### Added
* GoogleAds: `AdGroupOperation` new method `getBidType()`.

#### Fixed
* GoogleAds: `AdGroupOperation` updated pull from the server when loaded.

### 12/28/2018 - 1.0.2

#### Added
* GoogleAds: `AdGroupOperation` with ability to change adgroup bids using `setBid()`
* GoogleAds: `AdGroupOperation` ability to change name and status of adgroups.
* GoogleAds: `AdGroupOperation` with a `save()` method that posts changes to Google Ads.
* GoogleAds: `AdGroupOperation` Added getter methods `getName()`, `getStatus()`, `getCampaignId()`, `getId()`

### 12/28/2018 - 1.0.1

#### Added
* Bing Reports (Account, Campaign and Ad Group Level)
* Bing Authentication Session and basic Bing service methods

### 12/27/2018 - 1.0.0
Initial Release for `Google Ads`
