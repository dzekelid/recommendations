---
swagger: "2.0"
x-collection-name: NPR
x-complete: 0
info:
  title: NPR Get a list of recommendations from a category of content from an organization
  description: This endpoint provides a list of recommendations from a category of
    content from  an organization.
  termsOfService: http://dev.npr.org/develop/terms-of-use
  contact:
    name: NPR One Enterprise Team
    url: http://dev.npr.org
    email: NPROneEnterprise@npr.org
  version: 1.0.0
host: api.npr.org
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /listening/v2/aggregation/{aggId}/recommendations:
    get:
      summary: Get a set of recommendations for an aggregation
      description: This endpoint provides a list of recent audio items associated
        with the aggregation along with metadata about the aggregation.
      operationId: getAggRecommendations
      x-api-path-slug: listeningv2aggregationaggidrecommendations-get
      parameters:
      - in: path
        name: aggId
        description: ID of an aggregation such as a program or podcast
      - in: query
        name: No Name
      - in: query
        name: startNum
        description: The result to start with
      responses:
        200:
          description: OK
      tags:
      - News
      - Listening
      - Aggregation
      - Agg
      - Recommendations
  /listening/v2/organizations/{orgId}/categories/{category}/recommendations:
    get:
      summary: Get a list of recommendations from a category of content from an organization
      description: This endpoint provides a list of recommendations from a category
        of content from  an organization.
      operationId: getOrganizationCategory
      x-api-path-slug: listeningv2organizationsorgidcategoriescategoryrecommendations-get
      parameters:
      - in: path
        name: category
        description: One of the three categories of content - newscast, story, or
          podcast
      - in: query
        name: No Name
      - in: path
        name: orgId
        description: ID of an organization, such as an NPR One station
      responses:
        200:
          description: OK
      tags:
      - News
      - Listening
      - Organizations
      - Org
      - Categories
      - Category
      - Recommendations
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