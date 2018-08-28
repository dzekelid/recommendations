swagger: "2.0"
x-collection-name: Entertainment Express
x-complete: 1
info:
  title: Entertainment Express
  description: your-gateway-to-building-incredible-movie-tv-and-game-content-discovery-experiences-
  version: "2.0"
host: ee.iva-api.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /XroadMedia/recommendations:
    get:
      summary: Returns a list of recommendations from XRoadMedia for a movie or show.
      description: Get recommendations for movie or show.
      operationId: GetXRoadMediaRecommendations
      x-api-path-slug: xroadmediarecommendations-get
      parameters:
      - in: query
        name: MovieId
        description: Source MovieId for recommendations
      - in: query
        name: ShowId
        description: Source ShowId for recommendations
      - in: query
        name: Type
        description: Type of recommendation response
      responses:
        200:
          description: OK
      tags:
      - XroadMedia
      - Recommendations