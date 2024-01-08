```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ItemList",
  "name": "Upcoming Events",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "item": {
        "@type": "Event",
        "name": "Example Event 1",
        "startDate": "2024-02-01T18:00:00-08:00",
        "endDate": "2024-02-01T20:00:00-08:00",
        "location": {
          "@type": "Place",
          "name": "Example Venue",
          "address": {
            "@type": "PostalAddress",
            "streetAddress": "123 Main St",
            "addressLocality": "Cityville",
            "addressRegion": "CA",
            "postalCode": "12345",
            "addressCountry": "US"
          }
        },
        "mainEntityOfPage": {
          "@type": "CollectionPage",
          "@id": "https://www.example.com/events"
        }
      }
    },
    // Add more events as additional "ListItem" elements
  ]
}
</script>

```