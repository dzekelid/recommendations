---
swagger: "2.0"
x-collection-name: NPR
x-complete: 0
info:
  title: NPR Get a list of media for the logged-in user from NPR's recommendation
    engine
  description: |-
    This endpoint returns a list of audio recommendations. It is designed to be used for an initial list of recommendations, and then `GET /listening/v2/ratings?recommend=true` should be used for subsequent requests for recommendations.

    A fully-populated link to the ratings endpoint is returned with each individual recommendation and is located in the AudioItemDocument under the `links['recommendations']` object. The query parameters in this link should not be modified.
    Be sure to copy and send back the entire ratings object (RatingData), as new fields may be added to it in the future.
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
  /listening/v2/organizations/{orgId}/recommendations:
    get:
      summary: Get a variety of details about an organization including various lists
        of recent audio items
      description: This endpoint provides a variety of details about an organization
        including various lists of recent audio items.
      operationId: getOrganizationOverview
      x-api-path-slug: listeningv2organizationsorgidrecommendations-get
      parameters:
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
      - Recommendations
  /listening/v2/promo/recommendations:
    get:
      summary: Retrieve the most recent promo audio heard by the logged-in user
      description: Gets the most recently played promo for which the user has neither
        tapped through the promo or listened to the target story.
      operationId: getPromo
      x-api-path-slug: listeningv2promorecommendations-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - News
      - Listening
      - Promo
      - Recommendations
  /listening/v2/recommendations:
    get:
      summary: Get a list of media for the logged-in user from NPR's recommendation
        engine
      description: |-
        This endpoint returns a list of audio recommendations. It is designed to be used for an initial list of recommendations, and then `GET /listening/v2/ratings?recommend=true` should be used for subsequent requests for recommendations.

        A fully-populated link to the ratings endpoint is returned with each individual recommendation and is located in the AudioItemDocument under the `links['recommendations']` object. The query parameters in this link should not be modified.
        Be sure to copy and send back the entire ratings object (RatingData), as new fields may be added to it in the future.
      operationId: getRecommendations
      x-api-path-slug: listeningv2recommendations-get
      parameters:
      - in: query
        name: No Name
      - in: query
        name: notifiedMediaId
        description: The user received a push notification about this media; if provided,
          the service will add this recommendation to the top of the list
      - in: query
        name: sharedMediaId
        description: This media was shared directly with the user; if provided, the
          service will add this recommendation to the top of the list
      responses:
        200:
          description: OK
      tags:
      - News
      - Listening
      - Recommendations
x-streamrank:
  polling_total_time_average: "0"
  polling_size_download_average: "0"
  streaming_total_time_average: "0"
  streaming_size_download_average: "0"
  change_yes: "0"
  change_no: "0"
  time_percentage: "0"
  size_percentage: "0"
  change_percentage: "200"
  last_run: ~
  days_run: "0"
  minute_run: "0"
---