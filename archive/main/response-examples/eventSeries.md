# Event Series
Notes: using "event_series_full" view or similar
```json
// Example of event series data
{
  "id": 492,
  "schema": "eventSeries",
  "eventStatus": "Scheduled",
  "name": "John Smith Comedy Festival",
  "description": "Join us for a night of laughter with the hilarious John Smith.",
  "eventAttendanceMode": "Offline",
  "audience": "Adult",
  "startDate": "2023-12-15T19:00:00",
  "endDate": "2024-03-14T19:00:00"
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
  "offers": [  // List of event offers (represnetinosthat are part of the series
    {
      //What data is required here?
      "id": 140,
      "eventId": 492,
      "schema": "eventOffers",
      "eventStatus": "Scheduled",
      "name": "John Smith Comedy Show",
      "eventAttendanceMode": "Offline",
      "audience": "Adult",
      "startDate": "2024-02-15T19:00:00",
      "endDate": null, // Often null
      "isAccessibleForFree": false,
      "minPrice": 5.00,
      "price": 40.00,
      "availability": "http://schema.org/InStock",
      "availabilityStarts": "2023-11-15T19:00:00",
      "availabilityEnds": "2024-04-15T19:00:00",
      "advanceBookingRequirement": false,
      "location": {
        "id": 102,
        "schema": "places",
        "type": "Place", // Place | Organization
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
      "contributors": {
        // artists info
      },
    }
  ],
  "exhibitions": [  // List of exhibition part of the series
    {
      //What data is required here?
      "id": 3,
      "schema": "exhibitionEvents",
      "type": "Permanent",
      "eventStatus": "Scheduled",
      "name": "John Smith Comedy Expo",
      "eventAttendanceMode": "Offline",
      "audience": "Adult",
      "startDate": "2024-01-15T19:00:00",
      "endDate": null, // Often null
      "isAccessibleForFree": false,
      "minPrice": 5.00,
      "price": 40.00,
      "availability": "http://schema.org/InStock",
      "availabilityStarts": "2023-11-15T19:00:00",
      "availabilityEnds": "2024-04-15T19:00:00",
      "advanceBookingRequirement": false,
      "location": {
        "id": 102,
        "type": "Place", // Place | Organization
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
      "contributors": {
        // contributions info
      },
    }
  ],
  "lastModified": "2024-02-15T19:00:00"
}
```