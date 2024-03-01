# Artist

Notes: using "artist_full" view or similar
```json
// Example of event data
// Similar to old "get_activity"
{
  "id": 492,
  "schema": "contributor",
  "type": "Person", // Person | Organization
  "name": "John Smith",
  "alternateName": "Johnny Funny Guy",
  "description": "Join us for a night of laughter with the hilarious John Smith.",
  "gender": "Male", // Male, Female, Non-binary,
  "birthPlace": "", // Text 
  "nationality": "Canada", // Text (country)
  "address": "", // Text or full PostalAddress obj
  "url": "https://example.com"
  "image": {
    "name": "john-smith.jpg",
    "contentUrl": "https://example.com/john-smith.jpg",
    "copyrightType": "Copyright-free", // Copyright-free | Copyright
    "encodingFormat": "image/jpeg",
    "copyrightNotice": "© Example 2024", // or creditText
  },
  "medias": [
    // Raw list of all medias
  ],
  "sameAs": [
      "https://www.linkedin.com/in/john-smith",
      "https://twitter.com/john-smith",
      "https://www.facebook.com/john-smith"
  ],
  "affiliation": "", // Affiliated organization
  "events", [] // List of events
  "eventSeries": [], // List of series
  "exhibitionEvents": [], // List of exhibitions
  "lastModified": "2024-02-15T19:00:00"
}
```