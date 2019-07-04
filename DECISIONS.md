# API Design Decisions

This document outlines the rationale for most of the major design decisions involved in building the Logainm API in Q&A format.

## 1. How did you choose the API authentication method? Why not use OAuth or another JWT-based authentication protocol?

Our requirements for authentication are minimal and extend only to performance and usage monitoring. In terms of end-user experience, we wanted to keep the barrier to entry as low as possible. As such, the simple, key-based protocol we have chosen means that API consumers can get set up and start working quickly and without the need for any pre-existing tooling.

## 2. Did you consider structuring the data according to JSON-LD, RDF-JSON or another linked data standard?

It is precisely this multiplicity of standards that discouraged us from taking such an approach at this stage. We were reluctant to 
bet on a standard that may, or may not, be useful to our API consumers. We felt that, at this juncture, there was more benefit to be derived from making the data retrieval process as useful and as performant as possible, and producing high-quality and comprehensive documentation. We welcome feedback in this regard, however, and if there is reasonable demand for a particular linked data standard this is something we would consider implementing in v2.0 of the API.

## 3. 

Flat vs hierachical

## 4. What was the approach to data normali
partially denormalised
