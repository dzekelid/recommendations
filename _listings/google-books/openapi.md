swagger: "2.0"
x-collection-name: Google Books
x-complete: 1
info:
  title: Books
  description: searches-for-books-and-manages-your-google-books-library-
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