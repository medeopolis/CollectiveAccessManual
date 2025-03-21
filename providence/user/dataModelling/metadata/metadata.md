---
title: Metadata Elements
---

Attribute types represent all of the different varieties of fields
supported by CollectiveAccess. Each one is slightly different because
each is designed to accept and normalized data in different formats. See
below for more details about the unique nature of each Attribute type.
The full list of attribute types is listed
[here](https://github.com/collectiveaccess/providence/blob/master/app/conf/attribute_types.conf).


| Type Code | Description | Settings |
|----|----|----|
|Container|Unlike all other attribute types, containers do not represent data values. Rather their sole function is to organize attributes into groups for display. In a multi-attribute value set (for example an address with separate attributes for street number, city, state, country and postal code), there will be at least one container serving as the “root” (or top) of the attribute hierarchy. Other containers may serve to further group items in the multi-attribute set into sub-groups displayed on separate lines of a form.|Attribute settings: Container|
| Text|Represents a free-text value.|Attribute settings: Text|
|DateRange|Represents an historic date range accepting date/time range expressions in the formats acceptedby the CA TimeExpressionParser module.|Attribute settings: DateRange|
|List|Represents a value chosen from a drop-down list populated with values from a specified list as defined in the ca_lists table.|Attribute settings: List|
|Geocode|Represents one or more latitude/longitude coordinates. Coordinates can be entered as decimal latitude/longitude pairs (ex. 40.321,-74.55) or in degrees-minutes-seconds format (ex. 40° 23’ 10N, 74° 30’ 5W). Multiple latitude/longitude coordinates should be separated with semicolons (“;”). Non-coordinate entries are converted to coordinates using the Google Maps Geocoding service, which works well for most full and partial addresses worldwide. To unambiguously distinguish coordinate data from address data to be geocoded, it is strongly suggested that coordinate lists be enclosed in square brackets (ex. [40.321,-74.55; 41.321,-74.55;41.321,-75.55;40.321,-75.55;40.321,-74.55]. More notes on the Geocode types [GeocodeAttributeTypeNotes here]|Attribute settings: Geocode|
|Url|Accepts a properly formatted URL value. Currently does fairly limited checking on overall syntax and specified protocol. May be expanded in the future to verify the URL’s HTTP return code.|Attribute settings: Url|
|Currency|Accepts a currency value composed of a currency specifier and a decimal number. The current specifier should be a standard three letter currency code (see http://www.xe.com/iso4217.php) or one of the following special currency symbols: $ (US Dollar), ¥ (Japanese Yen), £ (English Pound) or € (Euro). Examples of valid input: $14.95, £32.50, CAD 20 [Canadian dollars], DKK 75 [Danish Kroner]|Attribute settings: Currency|
|Length|Accepts length measurements in metric, English and points units (the latter being typographical points). Entries are simply a numeric quantity + a unit specifier. Supported units specifiers are described on the measurement input formats page. While any supported length unit may be used for input, output units are dictated by the user’s units preference setting. This preference may be set to use English units, metric units or to display the measurement using the units with which it was initially entered.|Attribute settings: Length|
|Weight|Accepts weight measurements in metric and English units. Entries are simply a numeric quantity + a unit specifier. Supported units specifiers are described on the measurement input formats page. While any supported unit of weight may be used for input, output units are dictated by the user’sunits preference setting. This preference may be set to use English units, metric units or to display the measurement using the units with which it was initially entered.|Attribute settings: Weight|
|Timecode|Accepts time offsets in a number of time code formats. Time code values are typically used to express a duration or temporal position within time-based media (eg. a location in a video or audio stream). Formats supported include: hh:mm:ss (ex. 2:10:52 = 2 hours, 10 minutes, 52 seconds); XXh XXm XXs (ex. 2h 10m 52s); or XXs (ex. 7852s = 7852 seconds).|Attribute settings: TimeCode|
|Integer|Accepts integer values, but no floats. In effect everything that contains only the digits 0-9 is accepted.|Attribute settings: Integer|
|Numeric|Accepts numeric values. Numeric strings consist of optional sign, any number of digits, optional decimal part and optional exponential part. Thus +0123.45e6 is a valid numeric value. Hexadecimal notation (0xFF) is allowed too but only without sign, decimal and exponential part.|Attribute settings: Numeric|
|LCSH|Library of Congress Subject Heading value. Takes LCSH heading or first part of heading (the LCSH search service only supports truncation searches), does a lookup and returns a list of possible matches. Selected LCSH heading is stored as both text and the service URL identifier.|Attribute settings: LCSH|
|GeoNames|GeoNames value. Takes search text, passes it to the GeoNames search service and provides a dropdown with search results (ordered by score). Selected geoname is stored as both text (name, country, continent and ID) and the service URL identifier.|Attribute settings: GeoNames|
|File|Uploaded file. CA will try to identify the file and extract limited metadata, but even if it can’t identify the file it will accept and store it.|Attribute settings: File|
|Media|Uploaded media (image, sound video). CA will try to identify the file, extract metadata and create derivatives as configured in media_processing.conf. If CA cannot identify and parse the file it will reject it.|Attribute settings: Media|
|Taxonomy|Not Used anymore. [Git commit](https://github.com/collectiveaccess/providence/commit/d517ed3c388cc480ff50f1986dfe4678ceabeacb)||
|InformationService|Remote webservice lookup. Lookup values web services including the Getty TGN, ULAN and AAT, another CollectiveAccess instance, Wikipedia, WorldCat and uBio. See [Information Services](https://camanual.whirl-i-gig.com/providence/user/dataModelling/metadata/informationServices).|Attribute settings: InformationService|
|ObjectRepresentations|Reference object representations within your CollectiveAccess instance.|Attribute settings: ObjectRepresentations|
|Entities|Entity value. Searches the CollectiveAccess entity authority for given text and creates a typeless pseudo-relationship with the selected entity.|Attribute settings: Entities|
|Places|Place value. Searches the CollectiveAccess place authority for given text and creates a typeless pseudo-relationship with the selected place (typeless). Can be restricted to a single place type.|Attribute settings: Place|
|Occurrences|Occurrence value. Searches the CollectiveAccess occurrence authority for given text and creates a typeless pseudo-relationship with the selected occurrence (typeless). Can (and should) be restricted to a single occurrence type.|Attribute settings: Occurrence|
|Collections|Collection value. Searches the CollectiveAccess collection authority for given text and creates a typeless pseudo-relationship with the selected collection (typeless). Can be restricted to a single occurrence type.|Attribute settings: Collection|
|StorageLocations|Storage Location value. Searches the CollectiveAccess storage location authority for given text and creates a typeless pseudo-relationship with the selected storage location (typeless). Can be restricted to a single storage location type.|Attribute settings: StorageLocation|
|Loans|Loan value. Searches the CollectiveAccess loan authority for given text and creates a typeless pseudo-relationship with the selected loan (typeless). Can be restricted to a single occurrence type.|Attribute settings: Loan|
|Movements|Movement value. Searches the CollectiveAccess movement authority for given text and creates a typeless pseudo-relationship with the selected movement (typeless). Can be restricted to a single movement type.|Attribute settings: Movement|
|Objects|Object value. Searches the CollectiveAccess object authority for given text and creates a typeless pseudo-relationship with the selected object (typeless). Can be restricted to a single object type.|Attribute settings: Object|
|ObjectLots|Object Lot value. Searches the CollectiveAccess object lot authority for given text and creates a typeless pseudo-relationship with the selected object lot (typeless). Can be restricted to a single object lot type.|Attribute settings: ObjectLot|
|Floorplan|Implements an interactive floorplan user interface for place authority records|Attribute settings: Floorplan|
|Color|Represents a color in standard RGB hex format (Ex. FFCC33). In the editing interface this data type is typically displayed with a color picker.|Attribute settings: Color|
|Filesize|Accepts digital file size values with commonly used suffixes (B, KB, KiB, MB, MiB, GB, GiB, TB, TiB, PB, PiB). Available from version 1.8.|Attribute settings: Filesize|




  
