# Contributor API
## Get a 'contributor'
**TODO: Add response for 'Organization Type' contributors**\
**TODO: How to inject offer data?**
```yaml
openapi: 3.0.0
info:
  title: Contributor API
  version: 1.0.0
paths:
  /api/content/contributor/{id}:
    parameters:
      - name: id
        description: id of contributor
        in: path
        required: true
        schema:
          type: string
      - name: lang
        description: which language data to use
        in: query
        schema:
          type: string
          default: "fr"
          enum:
            - "fr"
            - "en"
    get:
      summary: Get Contributor Information
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              example:
                "@context": "https://schema.org"
                "@type": "Person"
                "id": 1
                "name": "John Doe"
                "description": "A talented musician and artist"
                "gender": "Male"
                "birthPlace":
                  "@type": "Place"
                  "name": "Cityville"
                  "address":
                    "@type": "PostalAddress"
                    "addressCountry": "United States"
                    "addressLocality": "Cityville"
                    "addressRegion": "CA"
                    "postalCode": "12345"
                    "streetAddress": "123 Main Street"
                "nationality":
                  "@type": "Country"
                  "name": "United States"
                "address":
                  "@type": "PostalAddress"
                  "addressCountry": "United States"
                  "addressLocality": "Cityville"
                  "addressRegion": "CA"
                  "postalCode": "12345"
                  "streetAddress": "123 Main Street"
                "image":
                  "@type": "ImageObject"
                  "name": "John Doe Portrait"
                  "description": "A professional portrait of John Doe"
                  "copyrightHolder":
                    "@type": "Person"
                    "name": "Jane Doe"
                  "copyrightNotice": "© 2023 Jane Doe"
                  "contentUrl": "https://example.com/john-doe-portrait.jpg"
                  "encodingFormat": "image/jpeg"
                "alternateName": "JD"
                "mainEntityOfPage": "https://example.com/john-doe-profile"
                "additionalType": "Musician"
                "sameAs": "https://twitter.com/johndoe"
        '404':
          description: Contributor not found
          content:
            application/json:
              example:
                error: "Contributor not found"
```
## Query contributors
```yaml
openapi: 3.0.0
info:
  title: Contributor API
  version: 1.0.0
paths:
  /api/content/contributor/:
    parameters:
      - name: lang
        description: which language data to use
        in: query
        schema:
          type: string
          default: "fr"
          enum:
            - "fr"
            - "en"
      - name: ids
        description: A comma-separated list of ids. If you define this option, all filtering parameters are ignored.
        in: query
        style: form
        explode: false
        schema: 
          type: array
          items:
            type: string
    get:
      summary: Get Contributor Information
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              example:
                "@context": "https://schema.org"
                "@type": "Person"
                "id": 1
                "name": "John Doe"
                "description": "A talented musician and artist"
                "gender": "Male"
                "birthPlace":
                  "@type": "Place"
                  "name": "Cityville"
                  "address":
                    "@type": "PostalAddress"
                    "addressCountry": "United States"
                    "addressLocality": "Cityville"
                    "addressRegion": "CA"
                    "postalCode": "12345"
                    "streetAddress": "123 Main Street"
                "nationality":
                  "@type": "Country"
                  "name": "United States"
                "address":
                  "@type": "PostalAddress"
                  "addressCountry": "United States"
                  "addressLocality": "Cityville"
                  "addressRegion": "CA"
                  "postalCode": "12345"
                  "streetAddress": "123 Main Street"
                "image":
                  "@type": "ImageObject"
                  "name": "John Doe Portrait"
                  "description": "A professional portrait of John Doe"
                  "copyrightHolder":
                    "@type": "Person"
                    "name": "Jane Doe"
                  "copyrightNotice": "© 2023 Jane Doe"
                  "contentUrl": "https://example.com/john-doe-portrait.jpg"
                  "encodingFormat": "image/jpeg"
                "alternateName": "JD"
                "mainEntityOfPage": "https://example.com/john-doe-profile"
                "additionalType": "Musician"
                "sameAs": "https://twitter.com/johndoe"
        '404':
          description: Contributor not found
          content:
            application/json:
              example:
                error: "Contributor not found"
```