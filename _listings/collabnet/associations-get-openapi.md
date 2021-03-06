---
swagger: "2.0"
x-collection-name: CollabNet
x-complete: 0
info:
  title: CollabNet TeamForge API Documentation Gets the association information for
    the given object/activity ids
  version: 1.0.0
  description: Gets the association information for the given object/activity ids.
basePath: /ctfrest/foundation/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /objects/{objectid}/delivery:
    get:
      summary: Gets delivery information for the given object
      description: Gets delivery information for the given object.
      operationId: getObjectDeliveryInfo
      x-api-path-slug: objectsobjectiddelivery-get
      parameters:
      - in: path
        name: objectid
        description: Object id(commit or artifact)
      responses:
        200:
          description: OK
      tags:
      - Delivery
      - Informationthe
      - Given
      - Object
  /objects/{objectid}/comments:
    post:
      summary: Posts a comment on the given object id
      description: Posts a comment on the given object id.
      operationId: postComment
      x-api-path-slug: objectsobjectidcomments-post
      parameters:
      - in: body
        name: body
        description: Comment
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Comment
      - "On"
      - Given
      - Object
    get:
      summary: Gets the comments on the given object id
      description: Gets the comments on the given object id.
      operationId: getObjectComments
      x-api-path-slug: objectsobjectidcomments-get
      parameters:
      - in: query
        name: count
        description: Max
      - in: path
        name: objectid
        description: Object id
      - in: query
        name: offset
        description: Offset
      - in: query
        name: sortby
        description: Sort by column name
      responses:
        200:
          description: OK
      tags:
      - Comments
      - "On"
      - Given
      - Object
  /objects/{objectid}/auditlog:
    get:
      summary: Gets a collection of audit transactions performed on the specified
        TeamForge object
      description: Gets a collection of audit transactions performed on the specified
        teamforge object.
      operationId: getAuditLog
      x-api-path-slug: objectsobjectidauditlog-get
      parameters:
      - in: query
        name: count
        description: Max
      - in: path
        name: objectid
        description: Object identifier
      - in: query
        name: offset
        description: Offset
      responses:
        200:
          description: OK
      tags:
      - Collection
      - Of
      - Audit
      - Transactions
      - Performed
      - "On"
      - Specified
      - TeamForge
      - Object
  /objects/{objectid}/associations:
    get:
      summary: Gets the association information for the given object id
      description: Gets the association information for the given object id.
      operationId: getObjectAssociations
      x-api-path-slug: objectsobjectidassociations-get
      parameters:
      - in: query
        name: depth
        description: Number of levels
      - in: query
        name: includeDependencies
        description: Include dependency associations (parent and child)
      - in: query
        name: includeEvents
        description: Include events
      - in: query
        name: includePhantoms
        description: Include phantom events
      - in: query
        name: limit
        description: Maximum number of generic associations for an object
      - in: path
        name: objectid
        description: Object/Activity id
      responses:
        200:
          description: OK
      tags:
      - Association
      - Informationthe
      - Given
      - Object
  /myself/recent/objects:
    get:
      summary: Gets recent object list for the current user
      description: Gets recent object list for the current user.
      operationId: getMyRecentObjects
      x-api-path-slug: myselfrecentobjects-get
      parameters:
      - in: query
        name: count
        description: Max
      responses:
        200:
          description: OK
      tags:
      - Recent
      - Object
      - Listthe
      - Current
      - User
  /monitoring/users/{userid}/objects/{objectid}:
    get:
      summary: Monitoring the current object or not for the given user id (true /
        false)
      description: Monitoring the current object or not for the given user id (true
        / false).
      operationId: isObjectMonitoredByUserid
      x-api-path-slug: monitoringusersuseridobjectsobjectid-get
      parameters:
      - in: path
        name: objectid
        description: Object id
      - in: path
        name: userid
        description: User id
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Current
      - Object
      - Notthe
      - Given
      - User
      - (true
      - ""
      - ""
      - False)
  /monitoring/users/myself/objects/{objectid}:
    get:
      summary: The logged in user is monitoring the current object or not (true /
        false)
      description: The logged in user is monitoring the current object or not (true
        / false).
      operationId: isObjectMonitored
      x-api-path-slug: monitoringusersmyselfobjectsobjectid-get
      parameters:
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - The
      - Logged
      - In
      - User
      - Is
      - Monitoring
      - Current
      - Object
      - Not
      - (true
      - ""
      - ""
      - False)
  /monitoring/users/by-username/{username}/objects/{objectid}:
    get:
      summary: Monitoring the current object or not for the given username (true /
        false)
      description: Monitoring the current object or not for the given username (true
        / false).
      operationId: isObjectMonitoredByUsername
      x-api-path-slug: monitoringusersbyusernameusernameobjectsobjectid-get
      parameters:
      - in: path
        name: objectid
        description: Object id
      - in: path
        name: username
        description: Username
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Current
      - Object
      - Notthe
      - Given
      - Username
      - (true
      - ""
      - ""
      - False)
  /integrationdata/by-objectid/{objectid}/{namespaceid}:
    delete:
      summary: Removes integration data for an object by namespace id
      description: Removes integration data for an object by namespace id.
      operationId: removeIntegrationData
      x-api-path-slug: integrationdatabyobjectidobjectidnamespaceid-delete
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespaceid
        description: Namespace id
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Removes
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
    put:
      summary: Sets integration data for an object by namespace id
      description: Sets integration data for an object by namespace id.
      operationId: setIntegrationData
      x-api-path-slug: integrationdatabyobjectidobjectidnamespaceid-put
      parameters:
      - in: body
        name: body
        description: Integration data
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: namespaceid
        description: Namespace id
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Sets
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
    get:
      summary: Gets integration data for an object by namespace id
      description: Gets integration data for an object by namespace id.
      operationId: getIntegrationData
      x-api-path-slug: integrationdatabyobjectidobjectidnamespaceid-get
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespaceid
        description: Namespace id
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
  /integrationdata/by-objectid/{objectid}/by-name/{namespace}:
    delete:
      summary: Removes integration data for an object by namespace name
      description: Removes integration data for an object by namespace name.
      operationId: removeIntegrationDataByName
      x-api-path-slug: integrationdatabyobjectidobjectidbynamenamespace-delete
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespace
        description: Namespace name
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Removes
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
      - Name
    put:
      summary: Sets integration data for an object by namespace name
      description: Sets integration data for an object by namespace name.
      operationId: setIntegrationDataByName
      x-api-path-slug: integrationdatabyobjectidobjectidbynamenamespace-put
      parameters:
      - in: body
        name: body
        description: Integration data
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: createNamespace
        description: Create namespace if missing?
      - in: path
        name: namespace
        description: Namespace name
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Sets
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
      - Name
    get:
      summary: Gets integration data for an object by namespace name
      description: Gets integration data for an object by namespace name.
      operationId: getIntegrationDataByName
      x-api-path-slug: integrationdatabyobjectidobjectidbynamenamespace-get
      parameters:
      - in: query
        name: dataname
        description: Data name
      - in: path
        name: namespace
        description: Namespace name
      - in: path
        name: objectid
        description: Object id
      responses:
        200:
          description: OK
      tags:
      - Integration
      - Dataan
      - Object
      - By
      - Namespace
      - Name
  /associations:
    get:
      summary: Gets the association information for the given object/activity ids
      description: Gets the association information for the given object/activity
        ids.
      operationId: getAssociations
      x-api-path-slug: associations-get
      parameters:
      - in: query
        name: depth
        description: Number of levels
      - in: query
        name: ids
        description: Comma separated object ids
      - in: query
        name: includeDependencies
        description: Include dependency associations (parent and child)
      - in: query
        name: includeEvents
        description: Include events
      - in: query
        name: includePhantoms
        description: Include phantom events
      - in: query
        name: limit
        description: Maximum number of generic associations for an object
      responses:
        200:
          description: OK
      tags:
      - Association
      - Informationthe
      - Given
      - Object
      - Activitys
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