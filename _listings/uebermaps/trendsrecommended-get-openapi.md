---
swagger: "2.0"
x-collection-name: uebermaps
x-complete: 0
info:
  title: uebermaps List recommended maps
  description: List recommended maps.
  termsOfService: https://uebermaps.com/terms/
  contact:
    name: uebermaps API Team
  version: "2.0"
host: uebermaps.com
basePath: /api/v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /trends/recommended:
    get:
      summary: List recommended maps
      description: List recommended maps.
      operationId: trends.recommended.get
      x-api-path-slug: trendsrecommended-get
      responses:
        200:
          description: OK
      tags:
      - Mapping
      - Recommended
      - Maps
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