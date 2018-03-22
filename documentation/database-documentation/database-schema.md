# Interfaith Donation Database Schema

## Tables
* *Example for clarification will be donations needed for summer*
* **need** - A need represents a particular need or item that Interfaith Sanctuary requires. A need for summer would be sunsreen. Needs are uniquely identified by their ID. A need has a name, description, unit of measurement, a created date, active or inactive (such as winter needs in summer would be inactive), and an Amazon url link for the particular item associated with the need. Units of measurements are represented by strings; such as lbs, oz, number of items, etc...
* **callout** - A callout is where a need gets represented. In our example our callout would be Summer. A callout is uniquely identified by its ID. A callout has a name, a description message, whether it is active or inactive, a created date and also an end date. An example would be creating a callout for Summer in March or April and having it end in September, while having an attached description message for the callout.
* **calloutneed** - This table represents the intermediate step for connecting our many-to-many relationship between need and callout. A calloutneed is uniquely identified by its ID. A calloutneed also has a particular need_id and callout_id associated. Calloutneed is the collection of needs for a particular callout. In our example we could have a Summer callout as well as another Summer related callout, where our sunscreen need can be represented in either callout, both, or neither. There is one need to many calloutneeds and one callout for many calloutneeds. This table is a join table between callout and need, because ideally there can be many needs to a callout and vise-versa.
* **donation** - A donation is the physical donation, gift, or transaction that for a particular calloutneed. A donation is uniquely identified by its ID. A donation also has an associated calloutneed_id and donor_id. A donation has a date, quantity, and timestamp as a record of the donation. A donation can be for multiple calloutneeds. That is for example a donation could be sunscreen as well as hats. A donation is also made by a particular donor. A donor can make multiple donations towards multiple calloutneeds. There is no limitation on the quantity a donor can donate. The only limitation would be a donor can only donate for particular calloutneeds that Interfaith Sanctuary needs, which was the point of this project initially. In our example a donation would be X amount of sunscreen for the Summer callout on a particular timestamp.
* **donor** - A donor is exactly what it sounds like, which is a person who donates. A donor is uniquely identified by their ID. A donor has standard personal information such as, city, state, zip, address, phone number, name, and email. A donor is different than a user since a user does not need all the information a donor does. A donor can make multiple donoations.
* **user** - A user is different than a donor. A user can be either an employee, administrator, director, manager, etc... A user is uniquely identified by their ID. A user needs a password, permissions, an email, and considered active or not. A user can be a donor, but does not have to be unless they want to be a donor. A user would basically be an employee, who can be a donor but is not required.
* **alerts** - An alert is a push notification system based on emergency or urgent callouts. An example of this would be if Interfaith Sanctuary decided to have a breakfast cookout on a weekend and the day decided of the cookout was Wednesday. The admin could then create an alert calloutneed with given needs under a callout and push that out immediately.
