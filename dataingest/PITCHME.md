# The Data Ingest API

### A simple Way of Pushing Data into GeoServer

---

## The Open Geoportal

- A collaboratively developed, open source, federated, social and technical **framework**.
- **Rapidly** document, **discover**, preview, and retrieve, **curated** geospatial **data** from multiple repositories.

<!-- - Lead by Tufts University along with Harvard . |
#- The Data Ingest API was designed as a component of the OGP | -->


<img src="assets/logos2.png" width="30%">

---?image=assets/screenshot_ogp.png&size=auto 90%

---?image=assets/ogp_architecture.png&size=auto 90%

<!--
OGP features a modular architecture, assembling loosely coupled services (web server, database, search engine). It also features a rich web client, which enables exploring the datasets through their metadata.
-->

---

## The Data Ingest API
- Loosely coupled service, which extends the OGP suite with data managing capabilities.
- Interacts with an instance of GeoServer, in order to query, upload and download geospatial datasets.
- The accompanying metadata is uploaded/downloaded to/from the SOLR server.

---

## A RESTfull Service
- Technology agnostic -> Microservices.

<img src="assets/why-microservices-578x470-op.png" width="40%">

---?image=assets/docker-compose-dataingest.png&size=auto 100%

<!--
The Java programming language provided support for annotations from Java 5.0 onward.
Prior to annotations, the behavior of the Spring Framework was largely controlled through XML configuration
-->

---
## Technology Stack
- Java 8
- Spring Boot

```java
@SpringBootApplication
@EnableCaching
@RestController
@EnableAutoConfiguration
```

---
## Geo Libraries
- https://github.com/geosolutions-it/geoserver-manager
- http://geotools.org/

```java
        store = new ShapefileDataStore(shapeURL);

        CoordinateReferenceSystem refSystem =
          store.getSchema().getGeometryDescriptor()
            .getCoordinateReferenceSystem();

        String wkt = refSystem.toWKT();

        EPSGClient client = new EPSGClient();
        String strCode = client.getEPSGfromWKT(wkt);
```

<!-- Geoserver Manager -- Java library that provides classes to programmatically configure GeoServer through its REST API. -->
<!-- Geotools   Java library that provides tools for geospatial data. -->

<!-- - check geometry type
- various checks in the uploaded shapefile (for instance, validity of CRS)
 -->

---
## What the Data Ingest API provides:
- A simple REST interface. <!-- (easy to use & technology agnostic) -->
- Scalability. <!-- (robust towards using a large number of datasets) -->
- Online documentation.

<img src="assets/scalability.png" width="50%">

---
## What the Data INGEST API does not provide:
- Other interactions with GeoServer. <!--, beyond uploading, downloading, unregistering and querying geospatial datasets (for instance, projecting files) ; ex: layer groups, styles, workspaces, data stores -->
- Ability to work with raster data.

<img src="assets/no.png" width="25%">

---
## OGP Harvester
<!-- good example to show the potential of Data Ingest.
-->
- Supports scheduling metadata harvesters. <!-- Solr, Geonetwork, CSW metadata nodes as well as direct metadata XML files within a web directory -->
- Supports different schemas.
- An organization can create a custom metadata catalog.
<!--  The OGP Harvester supports a variety of metadata formats. It also has an administrative section to manager and register new node services.-->

---
## OGP Harvester + Data Ingest API

- Browse layers.
- Upload zip archives containing data + related metadata, in a single step. <!--, to GeoServer and Solr.-->


---?image=assets/dataingest1.png&size=auto 90%

---?image=assets/dataingest2.png&size=auto 80%

---
## Some Implementation Details
- Asynchronous Requests.
- Pagination.
- Cache.
- Security. <!--(OAuth2) -->

---
## The REST Interface

The API calls are documented online, using Swagger:
- http://[YOURHOST]/swagger-ui.html |

---?image=assets/swagger.png&size=auto 90%

---
## JSON version

- http://[YOURHOST]/v2/api-docs

<img src="assets/lovejson.png" width="30%">

---
## Give it a Try!
- The data Ingest API was dockerized.
- The whole system can be launched from a docker composition.

<img src="assets/docker_toolbox_0.png" width="30%">

---

![Video](https://player.vimeo.com/video/278685324)

---
## The Team

<table class="GeneratedTable">
  <tbody>
    <tr>
      <td><img src="https://raw.githubusercontent.com/doublebyte1/keynotes/master/assets/me.jpg" height="125" /> </td>
      <td><img src="http://as.tufts.edu/images/newsMapquest.jpg" height="125" /></td>
      <td><img src="http://2017.foss4g.org/images/loc_barnett.png" height="125" /></td>
      <td><img src="https://www.geocat.net/wp-content/uploads/2010/09/256Jose.png" height="125" /></td>
      <td><img src="https://www.geocat.net/wp-content/uploads/2016/12/Antonio.jpg" height="125" /></td>
    </tr>
    <tr>
      <td>Joana Simoes</td>
      <td>Patrick Florance</td>
      <td>Christopher Barnett</td>
      <td>Jose Garcia</td>
      <td>Antonio Cerciello</td>
    </tr>
    <tr>
      <td>joana@doublebyte.net</td>
      <td>Patrick.Florance@tufts.edu</td>
      <td>Christopher.Barnett@tufts.edu</td>
      <td>jose.garcia@geocat.net</td>
      <td>antonio.cerciello@geocat.net</td>
    </tr>
    <tr>
      <td>@fa[twitter gp-contact](@doublebyte)</td>
      <td>@fa[twitter gp-contact](@pflomaps)</td>
      <td></td>
      <td></td>
      <td>@fa[twitter gp-contact](@PascalLike)</td>
    </tr>
  </tbody>
</table>

---?image=assets/left-red@2x.png&position=left&size=auto 30%

The source code for this project is available on Github, under a GPL v3 license:
- https://github.com/OpenGeoportal/Data-Ingest
---
# Thank you!
