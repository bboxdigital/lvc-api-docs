# Contributors (Artists, Organizations)
type:  Person | Organization

Google doesn't accept "Person" type yet.
They have "LocalBusiness", "Profile Page",
```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "@id": "https://la-vitrine.com/artist/john-smith/10",
  "identifier": 10,
  "name": "John Smith",
  "alternateName": "John Smith Funny Guy",
  "gender": "Male",
  "birthDate": "1980-01-15",
  "birthPlace": "CA",
  "description": "John Smith is a comedian from Montreal.",
  "image": {
    "@type": "ImageObject",
    "contentUrl": "https://www.johnsmithcomedy.com/images/john-smith.jpg",
    "description": "An example image",
    "encodingFormat": "image/jpeg",
    "creditText": "Jane Doe"
  },
  "url": "https://john-smith.com",
  "sameAs": [
    "https://www.linkedin.com/in/john-smith",
    "https://twitter.com/john-smith",
    "https://www.facebook.com/john-smith"
  ],
  "performerIn": {
    "@type": "Event",
    "@id": "https://la-vitrine.com/fr/evenement/john-smith-comedy-show/123/14",
    "identifier": 14,
    "name": "John Smith Comedy Show",
    "startDate": "2024-02-15T19:00:00",
    "endDate": "2024-02-15T21:00:00",
    "image": "https://example.com/john-smith.jpg",
    "location": {
      "@type": "Place",
      "@id": "https://la-vitrine.com/fr/lieu/comedy-club-a/23",
      "identifier": 23,
      "name": "Comedy Club A"
    }
  },
  "affiliation": {
    "@type": "Organization",
    "@id": "https://la-vitrine.com/fr/organization/comedy-organization/55",
    "identifier": 23,
    "name": "Comedy Organization"
  }
}
```
```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "@id": "https://la-vitrine.com/fr/organization/comedy-organization/55",
  "identifier": 55,
  "name": "Comedy Organization",
  "description": "Comedy Organization is a comedy club in Montreal.",
  "image": "https://example.com/photo.jpg",
  "url": "https://comedy-organization.com",
  "sameAs": [
    "https://www.linkedin.com/in/comedy-organization",
    "https://twitter.com/comedy-organization",
    "https://www.facebook.com/comedy-organization"
  ]
}
```