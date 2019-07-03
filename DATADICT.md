# Logainm Application Programming Interface (Version 0.5): Data dictionary

**Note:** This documentation describes a **prerelease** version of the Logainm API. Features are being added on an ongoing basis. The documentation will be revised in advance of the v1.0 release.

This document describes the data structure of the results made available via the Logainm Application Programming Interface (API). Logainm is a comprehensive management system for data, archival records and placenames research conducted by the Government of Ireland. For general information regarding the API and for developer guidelines please consult the [developer documentation](https://github.com/gaois/LogainmAPI-docs/blob/master/README.md).

## Contents

- [Places](#places)
  - [`place`](#place)

## Places

Queries to the Logainm API may return one or more `place` objects. The information below describes the properties of this object type.

### `place`

| Property name   | Type                | Cardinality         | Description               |
| :-------------- | :------------------ | :------------------ | :------------------------ |
| ID              | integer             | one                 | The unique place identifier. |
| DateCreated     | ISO 8601 datetime   | one                 | The date and time of entry creation.  |
| DateModified    | ISO 8601 datetime   | none or one         | The date and time of most recent modification to entry.  |
| Permalink       | string              | one                 | A permanent static hyperlink to the public place entry on logainm.ie. |
| Featured        | ISO 8601 datetime   | none or one or many | Denotes the date or dates on which this place was featured as the place of the day on the [logainm.ie](https://www.logainm.ie) website, if featured. |
| Cluster         | [`placeCluster`](#placeCluster) | none or one | Metadata regarding a group of places, of which this place is a member, that share placenames and are colocated or are proximate to each other. |
| Placenames      | [`placename`](#placename) | one or many | One or more placenames, and associated metadata, that are given to this place. |
| Glossary        | [`glossary`](#glossary) | none or one | Describes words commonly found in Irish placenames and which are present in placenames associated with this place. |
| Type            | [`placeType`](#placeType) | none or one | Describes the place type. |
| ContainedBy     | [`placeSummary`](#placeSummary) | none or one or many | Summary information regarding any other places which contain, by virtue of being geographically larger or belonging to a higher-order administrative unit, this place. |
| Contains        | [`placeType`](#placeType) | none or one or many | Information regarding the place types present within the bounds of this place. |
| Geography       | [`geography`](#geography) | none or one | Geographical metadata related to this place. |
| GridReferences  | [`gridReference`](#gridReference) | none or one or many | One or more sets of [Irish Grid Reference System](https://www.osi.ie/resources/reference-information-2/irish-grid-reference-system/) coordinates. |
| Gaeltacht       | boolean             | one                 | If true this place is in the Gaeltacht. |
| PostOffice      | boolean             | one                 | If true is or was once a post office in this place. |
| NorthernIreland | boolean             | one                 | If true this place is in Northern Ireland. |
| Images          | [`image`](#image)   | none or one or many |  |
| Resources       | [`resource`](#resource) | none or one or many |  |
| Links           | [`placeLink`](#placeLink) | none or one or many |  |
| Folklore        | [`folkloreLink`](#folkloreLink) | none or one or many |  |
| SameAs          | [`sameAs`](#sameAs) | none or one or many |  |
