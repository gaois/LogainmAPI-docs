# Logainm Application Programming Interface (Version 0.5): Developer documentation

**Note:** This documentation describes a **prerelease** version of the Logainm Application Programming Interface (API). Features are being added on an ongoing basis. The documentation will be revised in advance of the v1.0 release.

## Contents

1. [Introduction](#introduction)
2. [API overview](#api-overview)
3. [API versioning](#api-versioning)
4. [API authentication](#api-authentication)
5. [API access privileges](#api-access-privileges)
6. [Security](#security)
7. [Resource paths](#resource-paths)
8. [HTTP status codes](#http-status-codes)
9. [Data retention and data protection](#data-retention-and-data-protection)

## Introduction


## API overview

The Logainm API provides access to a number of resources by means of a defined URL schema. Specific resources are accessed via unique paths appended to the main website host. In some cases the resources that are returned may be filtered using optional query parameters. Attempts to access a resource provided by the API are referred to as requests. Following a successful request, resources are returned in the form of JSON. An unsuccessful attempt to access a resource will receive, at a minimum, a relevant HTTP status code in response to the request. An example of a valid request to the API is as follows:

> `https://www.logainm.ie/api/v0.5/1375542`

Users or applications (clients) requesting a resource via the API must authenticate their identity. This is achieved by providing an API key with each request. Each client must obtain a unique API key prior to interacting with the interface. Authentication is required to prevent abuse of the service and to track general usage statistics. Further details are provided below.

## API versioning

Multiple API versions are facilitated. This is to say, more than one version of the API may be accessible at the same time. Newer API versions may offer additional resources or functionalities but may require a different request syntax to older versions. The target API version is indicated by the second path parameter in the request URL:

> /api/**v0.5**/glossary

Older versions will be supported for developer convenience: without versioning, frequent changes to API syntax might cause dependent client applications to malfunction. We will endeavour to add new resources incrementally and will implement breaking changes only as a last resort. The API is versioned using [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html) (semver) and follows the semver specification. For brevity, however, only major and minor version points are reflected in request URLs.

After a period of time it may become necessary to deprecate older API versions for maintenance or performance reasons. When you register for your API key, you will be asked if you are willing to receive communications from Fiontar & Scoil na Gaeilge from time to time. Agreeing to receive such communication means you will receive advance notice of any such changes.

## API authentication

Clients requesting a resource via the API are required to authenticate their identity. This is achieved by passing an API key to the service with each request. Authentication offers some protection to the service provider from abuse of the API involving request overloads. It also allows us to retain some usage statistics, with a view to performance monitoring and service enhancement. Learn more about the data we retain in the following sections.


- `https://www.logainm.ie/api/v0.5/1412322`
- `https://www.logainm.ie/api/v0.5/1411548`
- `https://www.logainm.ie/api/v0.5/1384618`
- `https://www.logainm.ie/api/v0.5/26783`
- `https://www.logainm.ie/api/v0.5/1375542`
- `https://www.logainm.ie/api/v0.5/2425`
- `https://www.logainm.ie/api/v0.5/administrative-units/`
- `https://www.logainm.ie/api/v0.5/features/`
- `https://www.logainm.ie/api/v0.5/glossary/`
- `https://www.logainm.ie/api/v0.5/counties/`
