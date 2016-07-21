# Location Based Advertisement

## Tables

* `mappables` -- Polymorphic relation with mappable objects

  * `mappable_id`
  * `mappable_type`
  * `long`
  * `lat`

* `ads`

  * `title`
  * `desc`


## Interfaces

* `MappableInterface` 
  All mappable objects must implement this interface. The interface contains 2 methods:
  * `getTitle()`
  * `getDesc()`


## Models

* `Mappable`

  * `[Collection] static nearby($lat, $long, $dist = 500)`  
    Search mappable objects which are _nearby_ given `lat`, `long` and `dist`. 

* `Ad`


## Routes

* **GET** `/{username}`

  Display locations added by user

* **POST** `/{username}`

  Create new location.

  _Params:_

  * `long` : longitude of the location
  * `lat` : latitude of the location
  * `name` : location's name
  * `desc` : description for the location.


* **GET** `/nearby`

  Fetch JSON of nearby locations.

  _Params:_

  * `long` : longitude of current location
  * `lat` : latitude of current location
  * `dist` : distance between current location and nearby in meter


## Authentication

Users can login via oAuth provider like Facebook, GitHub, Twitter, etc. ATM, users can only login via FB.

