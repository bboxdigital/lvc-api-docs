## General notes and important information
- When possible response data structure follows Schema.org schemas when possible. Some deviation was required. This allows users to easily inject JSON-LD data into their frontends.
- Schema.org recommends using "identifier" instead of "id" to represent database id
- Response structures reworked to follow Schema.org standards when possible, this is a significant change from the existing API
- Multiple event types have been added, API routes added to support flexible and clear data fetching.
- Introduction of "offers" instead of "activities". An offer is similar to the previous "showing" and can be considered a representation when dealing with "event" type. For the Offer API, all event types have been standized to follow the offer schema. This can be useful when integrating such data into a search component as the data is predicable and normalized.
- "event" type events now have a field for "offers" that is a collection of Offer associated with the event. It is possible to have event without offer therefore, it was nessessary to create two separate API points. One to fetch event, one to fetch representation (offer).
- "exhibition" type events don't include offers as this data is found directly on the schema itself.
- "series" type events don't include offers as this data is found directly on the schema itself. Events of a series can be found in "subEvent" field.
- Custom Schema for LVCOffer, which is used in offer fields and in the "/events" API. This schema defines key information related to the event or representation in a standardized way. Allowing for simpler integrations and data management.


## Offers
Schema.org has a notion of Offers type but it doesn't fully represent how LVC uses offers. Schema.org Offers are essentially ticket information and price information.

For LVC an Offer has been extended to include items such as location and contributions (contributor). For certain schemas (ex: event) custom LVCOffer type are used in the "offers" field to more accurately reflect LVC's approach.

The /offers API does not use LVCOffer type, instead it returns Event type that closely follows Schema.org schema. 

