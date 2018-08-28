swagger: "2.0"
x-collection-name: uebermaps
x-complete: 1
info:
  title: uebermaps
  description: enable-people-to-store-spots-on-public-and-private-maps
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