# Logainm Application Programming Interface (Version 0.5): Developer documentation

**Note:** This documentation describes a **prerelease** version of the Logainm Application Programming Interface (API). Features are being added on an ongoing basis. The documentation will be revised in advance of the v1.0 release.

## Contents

1. [Introduction](#introduction)
2. [API overview](#api-overview)
3. [API versioning](#api-versioning)
4. [API authentication](#api-authentication)
5. [Security](#security)
6. [Resource paths](#resource-paths)
7. [HTTP status codes](#http-status-codes)
8. [Data retention and data protection](#data-retention-and-data-protection)

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


## API authentication

Clients requesting a resource via the API are required to authenticate their identity. This is achieved by passing an API key to the service with each request. Authentication offers some protection to the service provider from abuse of the API involving request overloads. It also allows us to retain some usage statistics, with a view to performance monitoring and service enhancement. Learn more about the data we retain in the following sections.

### How to obtain your API key

Visit the Gaois Developer Hub at [gaois.ie](https://www.gaois.ie/). Log in or register to create an account and you will be able to access your unique API key.

**Note:** This registration service is coming soon. In the meantime, please contact us at [logainm@dcu.ie](mailto:logainm@dcu.ie) to request or reset your API key.

### How to pass your API key

Your API key may be passed to the service in a few different ways. Choose whichever method is easiest for you.

#### HTTP header

Pass the API key into an `X-Api-Key` header:

> `'X-Api-Key: <API_KEY_HERE>' 'https://www.logainm.ie/api/v0.5/1384618'`

#### GET query parameter

Pass the API key into an `apiKey` GET query string parameter:

> `'https://www.logainm.ie/api/v0.5/1384618?apiKey=API_KEY_HERE'`

**Note:** The GET query parameter may be used for non-GET requests (such as POST and PUT).

#### HTTP Basic Authentication username

As an alternative, pass the API key as the username (with an empty password) using HTTP basic authentication:

> `'https://API_KEY_HERE@www.logainm.ie/api/v0.5/1384618'`

## Security

The API is served over a HTTPS protocol. Though HTTP requests to the service are automatically redirected to HTTPS, you should only ever interact with the API using HTTPS-prefixed URLs.

While HTTPS offers a signficant level of security, we would stress that the basic authentication methods described above do not amount to end-to-end encryption. **You should only ever pass your API Key to the service**—never include sensitive data, particularly passwords, as part of your requests.

### Illustrative examples

Below is a non-exhaustive list of valid API request URLs, provided for demonstration purposes:

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

## HTTP status codes

The status of all requests will be communicated, in the first instance, via standard HTTP status codes. We recommend that any applications interacting with the API handle the following status codes:

| Code  | Definition            | Further information |
| :---- | :-------------------- | :------------------ |
| 200   | OK                    | One or more JSON objects will be returned.  |
| 400   | BAD REQUEST           | The request syntax was invalid—a JSON object describing the error may be returned. |
| 401   | UNAUTHORISED          | A valid API key was not provided. |
| 404   | NOT FOUND             | The resource does not exist. |
| 500   | INTERNAL SERVER ERROR | Please contact us at [logainm@dcu.ie](mailto:logainm@dcu.ie) quoting the request path. |

**Note:** The current API does not handle create-, update-, or delete-type requests. Therefore, only HTTP GET methods are facilitated at this time.

## Data retention and data protection

We store the following data every time a request is made to the API:

1. Request path
2. Response status code
3. Result count
4. Query response time
5. Client ID (obtained with reference to the provided API key)

The client ID links your request to the data you have stored in the gaois.ie Developer Hub (the data you provided when you signed up for the service, for example). You can view all of the above data at any time in the Gaois.ie Developer Hub. These data are stored by Fiontar & Scoil na Gaeilge in a GDPR-compliant manner.

We reserve the right to report and/or publish aggregated or anonymised API query metrics. We will not report, publish or share any specific client data (i.e. your client ID or any associated client identification data) with any third party. We reserve the right to retain data items 1–4, listed above, indefinitely for the purposes of performance monitoring, research and service enhancement.

You are entitled to have your personal data removed from our systems at any time. This means deleting your username, password, name, organisational affiliation, and association with stored requests, completely and permanently. Please contact us at [logainm@dcu.ie](mailto:logainm@dcu.ie) if you wish to request that your personal data be removed.

By accessing the API you agree to abide by all policies and practices outlined in this document.
