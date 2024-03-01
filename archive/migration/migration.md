# Migration Guide
## Changelog
### Major Changes

- **API Endpoint Overhaul:**
  - Transitioned from using the "command" parameter to utilizing URL endpoints for improved simplicity and clarity.

- **Data Restructuring and Schema.org Alignment:**
  - Revamped field names and data structures to align closely with Schema.org standards.
  - Significant changes to reflect La Vitrine Culturelle's new data model.

- **Enhanced Data Exposure:**
  - By default, more information is now exposed, eliminating the need for separate commands to retrieve specific data.

- **Authentication Improvements:**
  - Implemented a new, more secure, and standardized authentication method for users.

- **OpenAPI Standards:**
  - Standardized the API following OpenAPI Standards to enhance interoperability and ease of use.

### Data Model Changes

- **Removal of "Organisme":**
  - The "Organisme" entity has been removed from the data model. (Consideration for future addition pending.)

- **Location Classification:**
  - "Sectors" are now classified as locations with specific types, falling under the location umbrella.

- **New Data Entities:**
  - Introducing "eventOffers" (representations) to replace the previous concept of "showings."
  - Introducing "exhibitions" as a distinct data entity.
  - Introducing "eventSeries" as a distinct data entity.
  - Introducing "contributor" to replace the previous concept of "artist".

- **JSON-LD Endpoints (Work in Progress):**
  - Introduced JSON-LD endpoints as a work in progress, enhancing Linked Data capabilities.

### Note: 
This major update brings a comprehensive overhaul to the API, focusing on improved structure, security, and adherence to widely recognized standards. Users are encouraged to review the updated documentation for a seamless transition to the enhanced functionality provided by this API.

## Migrating from ```get_events```
Replaced by the ```/api/content/allEvents/``` endpoint. See [documentation](../main/queryAllEvents.md) for more details.

## Migrating from ```get_activity``` & ```get_activitypublic```
Replaced by the ```/api/content/event```,```api/content/exhibition```,```/api/content/series```.

Event endpoints have been separated by type, due to the fact that in the new data structure the same ID can exist on different types of events. The responses are also return slightly different data, depending on the event type.

Users can now fetch individual event data using these endpoints, however they must know what type to use the correct endpoint.

Please refer to endpoint documentation for more information:
- [event](../main/event.md)
- [offer](../main/event.md#get-eventoffer-representation)
- [exhibition](../main/exhibition.md)
- [series](../main/series.md) 

## Migrating from ```get_activies``` & ```get_activiespublic```
Replaced by ```/api/content/allEvents```
This endpoint will serve as a query for all event types and with the introduction of a vast range of query parameters, similar to the previous commands.

Please reference the [documentation](../main/queryAllEvents.md) for a detailed list of all supported query parameters.

## Migrating from ```get_locations``` & ```get_locationspublic```
Replaced by ```/api/content/location```, all "Places" and "Sectors" are under the same endpoint now.

Organisme parameter has been removed.

withShowing parameter has be renamed to better suit it's function.

Please refer to endpoint [documentation](../main/location.md) for more information.

## Migrating from ```get_artists```
Replaced by ```/api/content/contributor```

Refer to [documentation](../main/contributor.md) for more information.

## Migrating from ```get_disciplines```
Replaced by ```/api/content/discipline```

This endpoint is still a work in progress.

Refer to [documentation](../main/discipline.md) for more information.

