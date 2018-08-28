swagger: "2.0"
x-collection-name: NPR
x-complete: 1
info:
  title: NPR One API Reference
  description: npr-one-is-a-smart-application-that-brings-the-best-of-npr-and-member-station-programming-newscasts-podcasts-and-stories-together-to-create-a-new-experience-for-listening--it-provides-an-editorcurated-and-localized-mobile-listening-experience-based-on-the-content-the-listener-chooses-likes-shares-and-enjoys--the-api-provides-all-of-the-content-and-customization-in-a-simple-structured-way-that-is-easy-for-applicationdevelopers-to-implement-
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
  /listening/v2/search/recommendations:
    get:
      summary: Get a list of recent audio and aggregation items associated with search
        terms
      description: In the schema shown below, SearchItemDocument is not an actual
        type of returned object; the object returned by a search will be either an
        AggregationAudioItemListDocument or an AudioItemDocument.
      operationId: getSearchRecommendations
      x-api-path-slug: listeningv2searchrecommendations-get
      parameters:
      - in: query
        name: No Name
      - in: query
        name: searchTerms
        description: Search terms to search on; can include URL-encoded punctuation
      responses:
        200:
          description: OK
      tags:
      - News
      - Listening
      - Search
      - Recommendations