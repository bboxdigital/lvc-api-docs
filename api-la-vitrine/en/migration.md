# Migration Guide
This major update brings a complete overhaul of the API, focusing on enhanced structure, security, and adherence to widely recognized standards.

## Major Changes

- **API Endpoint Redesign:**
  - Transition from using the "command" parameter to using URL endpoints for improved simplicity and clarity.

- **Data Restructuring and Alignment with Schema.org:**
  - Redesign of field names and data structures to closely align with Schema.org standards.
  - Easily inject JSON-LD into web pages for improved SEO and data interoperability.
  - Significant changes to reflect La Vitrine Culturelle's new data model.

- **Enhanced Data Exposure:**
  - By default, more information is now exposed, eliminating the need for separate commands to retrieve specific data.

- **OpenAPI Standards:**
  - API standardization following OpenAPI Standards to enhance interoperability and ease of use.

- **Authentication Improvements:**
  - Implementation of a new, more secure, and standardized authentication method.

### Data Model Changes

- **Removal of "Organisme":**
  - The `organisme` entity has been removed from the data model. (Consideration for future addition pending.)

- **Location Classification:**
  - `sectors` are now classified as `place` with specific types, falling under the location umbrella.

- **New Data Entities:**
  - Introducing `events` to replace the previous concept of   "showings."
  - Introducing `eventCollections` to replace the previous concept of "events".
  - Introducing `exhibitionEvents` type as a distinct data entity.
  - Introducing `eventSeries` type as a distinct data entity.
  - Introducing `contributor` to replace the previous concept of "artist".

## Migrating from `get_events`
Replaced by the `/searchEvents` endpoint. See [documentation](v1/searchEvents.md) for more details.

## Migrating from `get_activity` & `get_activitypublic`
Replaced by the `/events/{id}`, `/exhibitionEvents/{id}`, `/eventSeries/{id}`.

Event endpoints have been separated by type, due to the fact that in the new data structure the same ID can exist on different types of events. The responses are also return slightly different data, depending on the event type.

Users can now fetch individual event data using these endpoints, however they must know what type to use the correct endpoint.

Please refer to endpoint documentation for more information:
- [events](v1/events.md)
- [exhibitionEvents](v1/exhibitionEvents.md)
- [eventSeries](v1/eventSearch.md) 

## Migrating from `get_activies` & `get_activiespublic`
Replaced by `/searchEvents`
This endpoint will serve as a query for all event types and with the introduction of a vast range of query parameters, similar to the previous commands.

Please reference the [documentation](v1/searchEvents.md) for a detailed list of all supported query parameters.

## Migrating from `get_locations` & `get_locationspublic`
Replaced by `/places`, all "Places" and "Sectors" are under the same endpoint now.

Organisme parameter has been removed.

Please refer to endpoint [documentation](v1/places.md) for more information.

## Migrating from `get_artists`
Replaced by `/contributor`

Refer to [documentation](v1/contributors.md) for more information.

## Images and thumbnails

All items with an "image" property corresponding to the URL off the full size image will also have a "thumbnail" property corresponding to the image in 200x200 format.
