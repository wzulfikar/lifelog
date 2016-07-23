# Location Based Advertisement

## Tables

* `mappables`

  This table uses polymorphic relation to store all mappable objects.

  * `mappable_id`
  * `mappable_type`
  * `lat`
  * `lng`

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

  Fetch JSON of locations added by user.

* **POST** `/{username}`

  Create new location.

  _Params:_

  * `lat` : latitude of the location
  * `lng` : longitude of the location
  * `name` : location's name
  * `desc` : description for the location.


* **GET** `/nearby`

  Fetch JSON of nearby locations.

  _Params:_

  * `long` : longitude of current location
  * `lat` : latitude of current location
  * `dist` : distance between current location and nearby in meter


## Authentication

Users can login via oAuth provider like Facebook, GitHub, Twitter, etc. At the moment, users can only login via FB.

use http:\/\/www.latlong.net to find lat & long of nearby

## Seeding

Currently the provided seed is for ads nearby USM area. To generate new seed, use `php artisan db:seed`

## Possible Features

- ***Dynamic Markers***
    - Diff current markers againts fetched data & update its informations when necessary
    - Remove expired or deleted markers


