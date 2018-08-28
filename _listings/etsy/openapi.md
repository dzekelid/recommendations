swagger: "2.0"
x-collection-name: Etsy
x-complete: 1
info:
  title: Etsy
  description: bring-etsys-handmade-marketplace-and-community-into-your-apps-
  version: 1.0.0
host: openapi.etsy.com
basePath: /v2/private/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /users/{user_id}/recommended_listings:
    get:
      summary: Get Users User Recommended Listings
      description: Get recommended listings for an authenticated member. The number
        of listings returned may not match the specified limit if there is no activity
        from recommended shops.
      operationId: getUsersUserRecommendedListings
      x-api-path-slug: usersuser-idrecommended-listings-get
      parameters:
      - in: query
        name: excluded_listing_ids
        description: Bring Etsys handmade marketplace and community into your apps
      - in: query
        name: limit
        description: Bring Etsys handmade marketplace and community into your apps
      - in: path
        name: user_id
      responses:
        200:
          description: OK
      tags:
      - Users
      - Recommended
      - Listings
  /users/{user_id}/recommended_listings/rejects/{listing_ids}:
    post:
      summary: Post Users User Recommended Listings Rejects Listing S
      description: Registers rejections of recommended listings. Affects future recommended
        listings.
      operationId: postUsersUserRecommendedListingsRejectsListingS
      x-api-path-slug: usersuser-idrecommended-listingsrejectslisting-ids-post
      parameters:
      - in: path
        name: listing_ids
      - in: path
        name: user_id
      responses:
        200:
          description: OK
      tags:
      - Users
      - Recommended
      - Listings
      - Rejects
      - Listings
  /users/{user_id}/recommended_listings/views/{listing_ids}:
    post:
      summary: Post Users User Recommended Listings Views Listing S
      description: Register viewings of recommended listings. Affects future recommended
        listings.
      operationId: postUsersUserRecommendedListingsViewsListingS
      x-api-path-slug: usersuser-idrecommended-listingsviewslisting-ids-post
      parameters:
      - in: path
        name: listing_ids
      - in: path
        name: user_id
      responses:
        200:
          description: OK
      tags:
      - Users
      - Recommended
      - Listings
      - Views
      - Listings