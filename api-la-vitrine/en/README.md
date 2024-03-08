# WORK IN PROGRESS

This documentation is a work in progress and may change until the final version is approved.

# La Vitrine Culturelle (LVC) REST API Documentation
1. [Introduction](#introduction)
2. [Key Features](#key-features)
   - [1. Overview of Endpoints](#1-overview-of-endpoints)
   - [2. Data Structure](#2-data-structure)
   - [3. OpenAPI Swagger Definition](#3-openapi-swagger-definition)
3. [Getting Started](#getting-started)
   - [Step 1: Obtain an API Access Key](#step-1-obtaining-an-api-access-key)
   - [Step 2: Authentication](#step-2-authentication)
4. [Migration from the Old API](#migration-from-the-old-api)
5. [Important Notes](#important-notes)

## Introduction

Welcome to the official documentation of the La Vitrine Culturelle (LVC) REST API, a comprehensive interface designed to expose event data in Quebec to external partners. This API follows OpenAPI standards, providing a reliable and flexible solution for accessing event-related information.

## Background

La Vitrine has long been a curator of events in Quebec, serving as a go-to source for discovering and promoting various cultural happenings. In an effort to enhance the accessibility and functionality of their services, a new RESTful API has been developed. While maintaining the essence of their existing API, significant improvements have been implemented to accommodate the evolving data structure and to introduce additional features.

## Key Features

### 1. Overview of Endpoints

The API provides a set of core endpoints, allowing external partners to easily retrieve data from La Vitrine's database. The main endpoints include:

- **[eventCollections](v1/eventCollections.md):** Retrieve information about event collections.
- **[events](v1/events.md):** Retrieve information about individual events.
- **[eventSeries](v1/eventSeries.md):** Retrieve information about event series (festivals, tours, etc...)
- **[exhibitionEvents](v1/exhibitionEvents.md):** Retrieve information about exhibitions.
- **[contributors](v1/contributors.md):** Access details about contributors and artists associated with events.
- **[places](v1/places.md):** Retrieve data related to the locations or venues of events.
- **[disciplines](v1/disciplines.md):** Correspond to taxonomies for categorizing data, such as discipline (dance, music, etc...)
- **[searchEvents](v1/searchEvents.md):** A versatile endpoint allowing users to search across all types of events.

### 2. Data Structure

Efforts have been made to closely align the JSON structure with the standards of [Schema.org](https://www.schema.org/). This not only ensures consistency but also facilitates adaptation to the JSON-LD format, improving data interoperability.

### 3. OpenAPI Swagger Definition

You can visualize the API in the [Swagger API editor](https://editor.swagger.io/) by copying and pasting the contents of the file above:

- **[Swagger YAML](v1/swagger/swagger.yaml):** API definition in standard format.

[Click here](https://app.screencastify.com/v3/watch/TwH4f13leSEVbsdRJePn) for a short video demonstrating how to use the editor.

### Rate Limiting Policy

To ensure equitable access to our services and protect our infrastructure from abuse, we enforce a rate limiting policy on our API. This policy helps us maintain high service quality and availability for all partners.

#### Limits

Standard Rate Limit: 100 requests per minute per API key.
Extended Rate Limit: 1000 requests per minute per API key, available upon request.

#### Response Headers

Our API provides the following HTTP headers in every response to inform you of your current rate limit status:
- `X-RateLimit-Limit`: The maximum number of requests you’re permitted to make per minute.
- `X-RateLimit-Remaining`: The number of requests remaining in the current rate limit window.
- `X-RateLimit-Reset`: The time at which the current rate limit window resets in UTC epoch seconds.

#### Exceeding the Limit

If you exceed the rate limit, you will receive a `429 Too Many Requests` response status code, and you need to wait until the rate limit window resets before making additional requests.

## Getting Started

### Step 1: Obtaining an API Access Key

Before you begin using the API, you need to obtain a unique access key to authenticate your requests.

### Step 2: Authentication

To use this API, you must include your API key in the header of each request:
```
Authorization: Bearer YOUR_API_KEY
```
Replace `YOUR_API_KEY` with the API key we provided to you.

## Migration from the old API

Refer to the [migration documentation](migration.md) for more information on how to transition from the [old system](https://documentation.lavitrine.com/).

## Important Notes
- If data is to be used as JSON-LD on a website, the following fields must be removed before JSON-LD injection as they are not recognized by Schema.org or Google Rich Results:
  - `eventCollectionId`
  - `thumbnail`
  - `lastModified`
  - `exhibitionType`
  - `disciplines`
- For JSON-LD injection, utilization of the `@id` field is recommended to ensure unique identification of content across the web. Refer to [Schema.org](https://schema.org/docs/jsonld) for more information.
