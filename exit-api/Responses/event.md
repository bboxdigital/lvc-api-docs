# Event
Notes: using "events_full" view or similar
```json
// Example of event data
// Similar to old "get_activity"
{
  "id": 492,
  "type": "events",
  "eventStatus": "Scheduled",
  "name": "John Smith Comedy Show",
  "description": "Join us for a night of laughter with the hilarious John Smith.",
  "eventAttendanceMode": "Offline",
  "audience": "Adult",
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
  "eventOffers": [ // old "Showings"
    {
      //What data is required here?
      "id": 140,
      "eventId": 492,
      "type": "eventOffers",
      "eventStatus": "Scheduled",
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
      "offerArtist": {
        // Used when there is an artist attached to eventOffer.
      },
    }
  ],
  "lastModified": "2024-02-15T19:00:00"
}
```