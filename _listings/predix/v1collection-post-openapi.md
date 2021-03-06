---
swagger: "2.0"
x-collection-name: Predix
x-complete: 0
info:
  title: Predix Assets Create one or more user-defined domain objects
  description: |-
    This is a user-defined domain object collection.

    You can create your own custom domain objects, add properties to them, define relationships, and so on.

    The following characters are not allowed in any attribute names: $ < > : | ( ) , = ! ? &
  version: 1.0.0
host: predix-apphub-arcs-prod.run.aws-usw02-pr.ice.predix.io
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v1/{collection}:
    get:
      summary: Gets all user-defined domain objects.
      description: |-
        This is a user-defined domain object collection.

        You can create your own custom domain objects, add properties to them, define relationships, and so on.
      operationId: getV1Collection
      x-api-path-slug: v1collection-get
      parameters:
      - in: path
        name: collection
        description: Name of the user-defined domain object collection
      - in: query
        name: fields
        description: Fields to be returned from each entity (comma separated)
      - in: query
        name: filter
        description: GEL query filter
      - in: query
        name: pageSize
        description: Limits the number of entities returned
      responses:
        200:
          description: Successful response
      tags:
      - S
      - ""
      - User-defined
      - Domain
      - Objects
    post:
      summary: Create one or more user-defined domain objects
      description: |-
        This is a user-defined domain object collection.

        You can create your own custom domain objects, add properties to them, define relationships, and so on.

        The following characters are not allowed in any attribute names: $ < > : | ( ) , = ! ? &
      operationId: postV1Collection
      x-api-path-slug: v1collection-post
      parameters:
      - in: body
        name: body
        description: Array of entities to create
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: collection
        description: Name of the user-defined domain object collection
      responses:
        200:
          description: Successful response
      tags:
      - More
      - User-defined
      - Domain
      - Objects
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