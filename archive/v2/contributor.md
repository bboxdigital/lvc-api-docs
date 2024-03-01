# Contributor

## Content Endpoint

```content/contributor/{id}```
```json
{
  "id": 324,
  "type": "Person", // Person or Organization
  "name": "John Smith",
  "alternateName": "JS Funny Guy",
  "description": "John Smith is a Canadian comedian known for his hilarious stand-up comedy.",
  "gender": "Male",
  "birthPlace": "",
  "nationality": "Canada",
  "address": { // For Organization
    "streetAddress": "123 Laughter Lane",
    "addressLocality": "Humorville",
    "addressRegion": "Quebec",
    "postalCode": "G1T 4R1",
    "addressCountry": "CA"
  },
  "url": "https://example.com",
  "image": {
    "name": "john-smith.jpg",
    "contentUrl": "https://example.com/john-smith.jpg",
    "copyrightType": "Copyright-free",
    "encodingFormat": "image/jpeg",
    "copyrightNotice": "© Example 2024"
  },
  "sameAs": [
      "https://www.linkedin.com/in/john-smith",
      "https://twitter.com/john-smith",
      "https://www.facebook.com/john-smith"
  ],
  "affiliation": { // Affiliated with an Organization
    "id": 764,
    "type": "Organization",
    "name": "Comedy Organization",
    "url": "https://example.com",
    "image": "https://example.com/comedy-organization.jpg",
    "sameAs": [
      "https://www.linkedin.com/in/comedy-organization",
    ]
  },
  "events": [
    13,
    23,
    45,
    67
  ], // Event IDs that the contributor is associated with 
  "eventSeries": [4], // Event Series IDs that the contributor is associated with
  "exhibitionEvents": [56], // Exhibition Event IDs that the contributor is associated with
  "lastModified": "2024-02-15T19:00:00"
}
```

## JSON-LD

```/json-ld/contributor/{id}```
```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "@id": "https://la-vitrine.com/artist/john-smith/324", // Example of LVC webpage injection
  "identifier": 324,
  "name": "John Smith",
  "alternateName": "JS Funny Guy",
  "description": "John Smith is a Canadian comedian known for his hilarious stand-up comedy",
  "url": "https://example.com",
  "image": {
    "@type": "ImageObject",
    "contentUrl": "https://example.com/some-image.jpg",
    "description": "An example image",
    "encodingFormat": "image/jpeg",
    "creditText": "Jane Doe"
  },
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Laughter Lane",
    "addressLocality": "Humorville",
    "addressRegion": "Quebec",
    "postalCode": "G1T 4R1",
    "addressCountry": "CA"
  },
  "gender": "Male",
  "birthPlace": {
    "@type": "Place",
    "name": "Humorville",
    "address": {
      "@type": "PostalAddress",
      "streetAddress": "123 Laughter Lane",
      "addressLocality": "Humorville",
      "addressRegion": "Quebec",
      "postalCode": "G1T 4R1",
      "addressCountry": "CA"
    },
  },
  "nationality": {
    "@type": "Country",
    "name": "Canada"
  },
  "affiliation": {
    "@type": "Organization",
    "@id": "https://la-vitrine.com/organization/comedy-organization/764",
  },
  "performerIn": [
    {
      "@type": "Event",
      "@id": "https://la-vitrine.com/event/john-smith-comedy-show/23",
    },
    {
      "@type": "Event",
      "@id": "https://la-vitrine.com/event/john-smith-comedy-show/45",
    },
  ],
  "sameAs": [
    "https://www.linkedin.com/in/john-smith",
    "https://twitter.com/john-smith",
    "https://www.facebook.com/john-smith"
  ]
} 
```