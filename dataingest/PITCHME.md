# The Data Ingest API

### A simple Way of Pushing Data into GeoServer

---

## The Open Geoportal

- Collaboratively developed, open source, federated web application.
- Rapidly discover, preview, and retrieve geospatial data from multiple organizations.
<!-- - Lead by Tufts University along with Harvard and MIT. |
#- The Data Ingest API was designed as a component of the OGP | -->


<img src="assets/logos.png" width="30%">

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
      <td> <img src="assets/me_foss4guk_square.jpg" height="125"> </td>
      <td>pic</td>
      <td>pic</td>
      <td>pic</td>
      <td>pic</td>
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
      <td>email</td>
      <td>antonio.cerciello@geocat.net</td>
    </tr>
  </tbody>
</table>


---
## Tips!

<br>

@fa[arrows gp-tip](Press F to go Fullscreen)

@fa[microphone gp-tip](Press S for Speaker Notes)

---

## Template Features

- Code Presenting |
- Repo Source, Static Blocks, GIST |
- Custom CSS Styling |
- Slideshow Background Image |
- Slide-specific Background Images |
- Custom Logo, TOC, and Footnotes |

---?code=sample/go/server.go&lang=golang&title=Golang File

@[1,3-6](Present code found within any repo source file.)
@[8-18](Without ever leaving your slideshow.)
@[19-28](Using GitPitch code-presenting with (optional) annotations.)

---

@title[JavaScript Block]

<p><span class="slide-title">JavaScript Block</span></p>

```javascript
// Include http module.
var http = require("http");

// Create the server. Function passed as parameter
// is called on every request made.
http.createServer(function (request, response) {
  // Attach listener on end event.  This event is
  // called when client sent, awaiting response.
  request.on("end", function () {
    // Write headers to the response.
    // HTTP 200 status, Content-Type text/plain.
    response.writeHead(200, {
      'Content-Type': 'text/plain'
    });
    // Send data and end response.
    response.end('Hello HTTP!');
  });

// Listen on the 8080 port.
}).listen(8080);
```

@[1,2](You can present code inlined within your slide markdown too.)
@[9-17](Displayed using code-syntax highlighting just like your IDE.)
@[19-20](Again, all of this without ever leaving your slideshow.)

---?gist=onetapbeyond/494e0fecaf0d6a2aa2acadfb8eb9d6e8&lang=scala&title=Scala GIST

@[23](You can even present code found within any GitHub GIST.)
@[41-53](GIST source code is beautifully rendered on any slide.)
@[57-62](And code-presenting works seamlessly for GIST too, both online and offline.)

---

## Template Help

- [Code Presenting](https://github.com/gitpitch/gitpitch/wiki/Code-Presenting)
  + [Repo Source](https://github.com/gitpitch/gitpitch/wiki/Code-Delimiter-Slides), [Static Blocks](https://github.com/gitpitch/gitpitch/wiki/Code-Slides), [GIST](https://github.com/gitpitch/gitpitch/wiki/GIST-Slides)
- [Custom CSS Styling](https://github.com/gitpitch/gitpitch/wiki/Slideshow-Custom-CSS)
- [Slideshow Background Image](https://github.com/gitpitch/gitpitch/wiki/Background-Setting)
- [Slide-specific Background Images](https://github.com/gitpitch/gitpitch/wiki/Image-Slides#background)
- [Custom Logo](https://github.com/gitpitch/gitpitch/wiki/Logo-Setting), [TOC](https://github.com/gitpitch/gitpitch/wiki/Table-of-Contents), and [Footnotes](https://github.com/gitpitch/gitpitch/wiki/Footnote-Setting)

---

## Go GitPitch Pro!

<br>
<div class="left">
    <i class="fa fa-user-secret fa-5x" aria-hidden="true"> </i><br>
    <a href="https://gitpitch.com/pro-features" class="pro-link">
    More details here.</a>
</div>
<div class="right">
    <ul>
        <li>Private Repos</li>
        <li>Private URLs</li>
        <li>Password-Protection</li>
        <li>Image Opacity</li>
        <li>SVG Image Support</li>
    </ul>
</div>

---

### Questions?

<br>

@fa[twitter gp-contact](@gitpitch)

@fa[github gp-contact](gitpitch)

@fa[medium gp-contact](@gitpitch)

---?image=assets/gitpitch-audience.jpg

@title[Download this Template!]

### <span class="white">Get your presentation started!</span>
### [Download this template @fa[external-link gp-download]](https://gitpitch.com/template/download/aqua)
