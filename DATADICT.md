# Logainm Application Programming Interface (Version 0.5): Data dictionary

**Note:** This documentation describes a **prerelease** version of the Logainm API. Features are being added on an ongoing basis. The documentation will be revised in advance of the v1.0 release.

This document describes the data structure of the results made available via the Logainm Application Programming Interface (API). Logainm is a comprehensive management system for data, archival records and placenames research conducted by the Government of Ireland. For general information regarding the API and for developer guidelines please consult the [developer documentation](https://github.com/gaois/LogainmAPI-docs/blob/master/README.md).

## Contents

- [Places](#places)
  - [`place`](#place)
- [Common entities](#common-entities)
  - [`coordinates`](#coordinates) 
  

## Places

The `place` object is at the core of the Logainm API: it represents a geographic location and includes associated toponymic, lexical, and other metadata. Queries to the API may return one or more `place` objects. The information below describes the properties of this object type.

### `place`

| Property name   | Type                | Cardinality         | Description               |
| :-------------- | :------------------ | :------------------ | :------------------------ |
| ID              | integer             | one                 | The unique place identifier. |
| ReplacementID   | integer             | none or one         | If this value is set the requested place record has been merged into another record in the database. The value is the replacement record identifier. |
| DateCreated     | ISO 8601 datetime   | one                 | The date and time of entry creation.  |
| DateModified    | ISO 8601 datetime   | none or one         | The date and time of most recent modification to entry.  |
| Permalink       | string              | one                 | A permanent static hyperlink where a human reader can find more information about the place. This automatically redirects to the Irish or English version of the place information page. |
| Featured        | ISO 8601 datetime   | none or one or many | Denotes the date or dates on which this place was featured as the place of the day on the [logainm.ie](https://www.logainm.ie) website, if featured. |
| Cluster         | [`placeCluster`](#placeCluster) | none or one | Metadata representing a group of places, of which this place is a member, that share placenames and are colocated or are proximate to each other. |
| Placenames      | [`placename`](#placename) | one or many | One or more placenames, and associated metadata, that are given to this place. |
| Glossary        | [`glossary`](#glossary) | none or one | Describes words commonly found in Irish placenames and which are present in placenames associated with this place. |
| Categories        | [`placeCategory`](#placeCategory) | none or one or many | Describes the categories associated with this place. Only in exceptional cases will places have more than one category. |
| IncludedIn      | [`placeSummary`](#placeSummary) | none or one or many | Summary information regarding the administrative units (counties, civil parishes, etc.) which include this place. |
| Includes        | [`placeCategory`](#placeCategory) | none or one or many | Describes the place categories included within the bounds of this place. |
| Geography       | [`geography`](#geography) | none or one | Geographical location of the place expressed in terms of latitudinal and longitudinal coordinates. |
| GridReferences  | [`gridReference`](#gridReference) | none or one or many | Geographical location of the place expressed in terms of [Irish Grid Reference System](https://www.osi.ie/resources/reference-information-2/irish-grid-reference-system/) coordinates. |
| Gaeltacht       | [`placeProperty`](#placeProperty) | none or one         | Indicates whether the place is in the Gaeltacht. |
| PostOffice      | [`placeProperty`](#placeProperty) | none or one         | Indicates whether there is or was once a post office in this place. |
| NorthernIreland | [`placeProperty`](#placeProperty) | none or one         | Indicates whether this place is in Northern Ireland. |
| Images          | [`image`](#image)   | none or one or many | Describes one or more scanned records from the Placenames Branch archive relating to this place. |
| Resources       | [`resource`](#resource) | none or one or many | Describes one or more toponomy resources available on [logainm.ie](https://www.logainm.ie) relating to this place. |
| Links           | [`placeLink`](#placeLink) | none or one or many | Provides one or more links to related data in external resources. External resources include [OSI](https://www.osi.ie/), [Placenames Northern Ireland](http://www.placenamesni.org/), [Wikipedia](https://www.wikipedia.org/), [Geonames](http://www.geonames.org/), etc. |
| Folklore        | [`folkloreLink`](#folkloreLink) | none or one or many | Provides links to folkloric data from [dúchas.ie](https://www.logainm.ie) associated with this place, if available. |
| SameAs          | [`sameAs`](#sameAs) | none or one or many | Specifies one or more co-references to this place in data sets other than the Placenames Database of Ireland. Consistent with OWL Web Ontology [SameAs](https://www.w3.org/TR/owl-ref/) definition. |

## Common entities

Certain entities may be common to multiple object types. These are described below.

### `coordinates`

| Property name   | Type                | Cardinality         | Description               |
| :-------------- | :------------------ | :------------------ | :------------------------ |
| Latitude        | double              | one                 | The latitudinal coordinate. |
| Longitude       | double              | one                 | The longitudinal coordinate. |
