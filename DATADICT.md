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
| Featured        | ISO 8601 datetime   | none or one or many | Denotes the date or dates on which the place was featured as the place of the day on the [logainm.ie](https://www.logainm.ie) website, if featured. |
| Cluster         | [`placeCluster`](#placeCluster) | none or one |  |
| Placenames      | [`placename`](#placename) | one or many |  |
| Glossary        | [`glossary`](#glossary) | none or one |  |
| Type            | [`placeType`](#placeType) | none or one |  |
| IsIn            | [`placeSummary`](#placeSummary) | none or one or many |  |
| HasIn           | [`placeType`](#placeType) | none or one or many |  |
| Geography       | [`geography`](#geography) | none or one |  |
| GridReference   | [`gridReference`](#gridReference) | none or one or many |  |
| Gaeltacht       | boolean             | one                 |  |
| PostOffice      | boolean             | one                 |  |
| NorthernIreland | boolean             | one                 |  |
