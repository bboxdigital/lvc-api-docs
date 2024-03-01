# Notes
## General
How to handle `lastModified`?  Any implications to add directly to the JSON?
Can we add LVC urls to "sameAs"?

Do we take LVC Additional Type and convert the main one to a different Schema.org type? ex: @type: MusicEvent or @type: ComedyEvent.

additionalType the way LVC uses is not recognized by Schema.org or Google Rich Results.  There is no way to add custom discipline types to Schema.org out of the box.

Following fields must be removed before JSON-LD injection:
- `eventCollectionId`
- `thumbnail`
- `lastModified`
- `exhibitionType`
- `disciplines`

## Events
How deep to resolve images (ex: Performer image, Location image). For main event image we can include as much as possible.

## ExhibitionEvents
- how to handle `type` field?
- how to handle `performers` field?
- how to deal with `temporary` vs `permanent` type?  startDate, endDate is conditional based on the type.  Will JSON-LD be invalid without startDate / endDate? How will google handle this information?

## Event Series
- EventSeries is not recognized by Google Rich Results?? Maybe / Maybe not  - will have to test.
- How much information do we need to pass in the sub events?
