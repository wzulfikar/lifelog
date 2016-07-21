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

* `MappableInterface` : all mappable objects must implement this interface, which contains 2 methods:
  * `[string] getTitle()`
  * `[string] getDesc()`
    ## Models



* `Mappable`

  * `[Collection] static nearby($lat, $long, $dist = 500)`

* `Ad`


## Routes

* **GET** `/{username}` : display locations added by user

* **POST** `/{username}` : create new location. 

  _Params:_
  * `long` : longitude of the location
  * `lat` : latitude of the location
  * `name` : location's name
  * `desc` : description for the location.


* **GET** `/nearby` : fetch JSON of nearby locations. 

  _Params:_
  * `long` : longitude of current location
  * `lat` : latitude of current location
  * `dist` : distance between current location and nearby in meter


