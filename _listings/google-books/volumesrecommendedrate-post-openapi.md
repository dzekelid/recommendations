---
swagger: "2.0"
x-collection-name: Google Books
x-complete: 0
info:
  title: Google Books API Rate Recommend
  description: Rate a recommended book for the current user.
  contact:
    name: Google
    url: https://google.com
  version: v1
host: www.googleapis.com
basePath: /books/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /volumes/recommended:
    get:
      summary: Get Recommend
      description: Return a list of recommended books for the current user.
      operationId: books.volumes.recommended.list
      x-api-path-slug: volumesrecommended-get
      parameters:
      - in: query
        name: locale
        description: ISO-639-1 language and ISO-3166-1 country code
      - in: query
        name: maxAllowedMaturityRating
        description: The maximum allowed maturity rating of returned recommendations
      - in: query
        name: source
        description: String to identify the originator of this request
      responses:
        200:
          description: OK
      tags:
      - Recommended
  /volumes/recommended/rate:
    post:
      summary: Rate Recommend
      description: Rate a recommended book for the current user.
      operationId: books.volumes.recommended.rate
      x-api-path-slug: volumesrecommendedrate-post
      parameters:
      - in: query
        name: locale
        description: ISO-639-1 language and ISO-3166-1 country code
      - in: query
        name: rating
        description: Rating to be given to the volume
      - in: query
        name: source
        description: String to identify the originator of this request
      - in: query
        name: volumeId
        description: ID of the source volume
      responses:
        200:
          description: OK
      tags:
      - Recommended
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---