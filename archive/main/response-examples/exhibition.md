# Exhibition
Notes: using "exhibition_events_full" view or similar
```json
// Example of exhitibtion data
{
  "id": 492,
  "schema": "exhibitionEvents",
  "type": "Permanent", // Permanent | Temporary
  "eventStatus": "Scheduled",
  "name": "John Smith Comedy Show",
  "description": "Join us for a night of laughter with the hilarious John Smith.",
  "eventAttendanceMode": "Offline",
  "audience": "Adult",
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
  "contributions": [ // What data is required here? Perhaps we could consolidate
    {
      "id": 402,
      "type":"Artiste sur scene",
      "contributors": {
        "name": "John Smith",
        "contributorType": "Person",
        "image": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
        "url": "https://john-smith.com",
        ...
      },
      ...
    },
    {
      "id": 401,
      ...
    }
  ],
  // Or artists instead, if full contribution data is not required
  "artists": [
    {
      "id": 853,
      "type": "Person",
      "name": "John Smith",
      "image": "https://example.com/john-smith.jpg", // Need full media object?
      "sameAs": [
        "https://www.linkedin.com/in/john-smith",
        "https://twitter.com/john-smith",
        "https://www.facebook.com/john-smith"
      ]
    },
  ],
  "location": {
    "id": 102,
    "schema": "places",
    "type": "Place", // Place | Sector
    "name": "Example Place A",
    "address": { // Could combined to String instead, but more difficult for users to parse into JSON-LD
      "streetAddress": "789 Laughter Lane",
      "addressLocality": "Humorville",
      "addressRegion": "Quebec",
      "postalCode": "G1T 4R1",
      "addressCountry": "CA"
    },
    "latitude": 37.23332,
    "longitude": -133.43330,
    "maximumAttendeeCapacity": 240,
    "url": "https://example-place-a.com"  // Offical Website
  },
  "lastModified": "2024-02-15T19:00:00"
}
```