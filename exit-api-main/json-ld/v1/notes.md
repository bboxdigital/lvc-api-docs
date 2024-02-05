## Examples (JSON-LD on frontend)
- [Schema.org Validator](https://validator.schema.org/)
- [Ticketmaster](https://www.ticketmaster.ca/tim-mcgraw-tickets/artist/762799?site=10085&pageType=178229&nativePromo=3389&slot=1&campaign=732282&flight=425372307&nativeId=435303311&ac_link=NTM_TimMcGraw2024_spotlight_3#about)
- [Eventbrite Events Page](https://www.eventbrite.ca/d/canada/events/)
- [Eventbrite Event Page](https://www.eventbrite.ca/cc/sugar-sammy-gatineau-youre-gonna-rire-2-1428859?aff=odclrlmctfte)

## Define the use case for JSON-LD
- Structured content, following a well documented source
- Provide LVC data to partners in a structured manner to make injection of JSON-LD onto their website effortless
- LVC website frontend / partner's website frontend

## Notes on JSON-LD
- A lot of fields on Schema.org or used to support the "Linked data" system. Often, there are URI values (external links) and generally the JSON-LD data is injected via scripts on Frontend / Websites, where search engine crawlers can travel these URIs (links) to build a detailed representation of the page. JSON-LD is used on frontends to provide these search engines with a detailed representation of the web page.

- Going for a full JSON-LD approach (with Links etc) assumes that the consumer will use the data in a way that is similar to how search engines use the data. This is not always the case.

- If you serve data in direct JSON-LD format users looking to fill their databases with content will soon become frustrated with "Linked Data", databases can't traverse or travel links like search engine crawlers.

- When creating an API for users to use to populate their own Databases or to compile data for their own frontends, JSON-LD starts to lose it's value unless you know how the users of your API will use the data, and how this data will be represented on their frontends.

- Our proposed approach is to use [Schema.org](https://schema.org) as building block for creating the JSON structure of content.

- Yes, it's possible to create an API that serves JSON-LD, but partners and consumers would have to create a system to handle mapping and storing the data in their own databases. This is not ideal. Not to mention, the API would have to replace any "Linked Data" with traditional data to provide a more traditional JSON structure. The consumer would then have to create their own JSON-LD structures and mapping to inject onto their website.

- We must ensure that we provide the right data for the customers so they can accurately consume data. This means moving away from true JSON-LD structures.

- For partners who want the full JSON-LD structures, we will offer different endpoints that the consumers can use to catalog the "JSON-LD" in a field on their own database so that they can easily inject the JSON into their page.

- LVC Data uses a combination of Event, Exhibition, Series and CreativeWork. We will need to define how these are represented in JSON-LD. Especially Events, where it's often to see fields that come from both Event and CreativeWork schemas.

## Questions
- How will consumers use the data? Databases / Frontends vs JSON-LD injections

## Items to review
- @id vs identifier vs sameAs vs mainEntity vs url
- Review additionalType (as per Schema.org)
- Person vs Organization, will they be under the same endpoint?
- Performer, actor, composer, contributor, organizer, producer, director, etc.
  - A variety of different fields in JSON-LD, representing "contributions"
  - Schema.org contributor is defined as "the secondary contributor"
  - Event schema does not have producer, director, etc. these are fields in CreativeWork
  - Adding CreativeWorks type into Event schema? Is this required?
- How to manage pricing
- Additional types
- How to integrate LVC event

