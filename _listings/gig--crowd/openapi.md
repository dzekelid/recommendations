swagger: "2.0"
x-collection-name: GIG & CROWD
x-complete: 1
info:
  title: GIG & Crowd
  version: 1.0.0
host: gigandcrowd.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /api/v1/gigme/event/recommended:
    get:
      summary: Get Gigme Event Recommended
      description: Get gigme event recommended.
      operationId: getApiV1GigmeEventRecommended
      x-api-path-slug: apiv1gigmeeventrecommended-get
      parameters:
      - in: query
        name: request.amount
      - in: query
        name: request.dateFilter
      - in: query
        name: request.type
        description: Type of Preview (event or place)
      responses:
        200:
          description: OK
      tags:
      - Gigme
      - Event
      - Recommended