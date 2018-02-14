# Spatial Data Infrastructures
### In the era of Docker and Microservices
+++

# How can we ease the provision of SDIs?

+++?image=assets/journey.jpg&size=auto 90%

---
## Introduction
<!-- Who am I?-->
<div id="container">
  <div id="content">
    <img src="https://raw.githubusercontent.com/doublebyte1/keynotes/master/assets/pasta_fresca.jpg">
  </div>
  <div id="navbar">
    <ul>
       <li style="font-size:30px">Board member of GSDI.</li>
       <li style="font-size:30px">Deputy president of OSGeo-pt.</li>
       <li style="font-size:30px">OSGeo advocate.</li>
       <li style="font-size:30px">Honorary research associate at CASA-UCL.</li>
       <li style="font-size:30px">Ocasional contributor of FOSS projects.</li>
    </ul>
  </div>
</div>

+++
## GeoCat
<!-- I work for geocat-->
+ Micro-company, based in the NL
+ Spatial Data Infrastructures (SDI)
+ FOSS

![team](assets/team.jpg)

+++
<!-- Why I picked this topic?-->
## GeoCat Live

+ Cloud SDI As a Service

![team](assets/LiveGraph.png)

---
## Spatial Data Infrastructure

*Collection of technologies, policies and institutional arrangements that facilitate the availability of and access to spatial data.*
<p style="text-align:right;">GSDI, 2012</p>

<!--
GSDI cookbook

+ Data infrastructure implementing a framework of geographic data, metadata, users and tools that are interactively connected in order to use spatial data in an efficient and flexible way.

Data as a Service
-->
+++
## Timeline

<!--
Quite young when compared to the history of GIS
-->

<div id="container">
  <div id="content">
    <img src="https://raw.githubusercontent.com/doublebyte1/keynotes/master/assets/800px-Snow-cholera-map-1.jpg">
  </div>
  <div id="navbar">
    <ul>
       <li style="font-size:30px">John Snow's cholera maps (1854).</li>
       <li style="font-size:30px">US NSDI (1994).</li>
       <li style="font-size:30px">INSPIRE (2007).</li>
    </ul>
  </div>
</div>


<!-- +++
## Software Components

+ Catalogue service
+ Spatial Data service
+ Spatial Data repository
+ Processing Service
+ Client
-->

<!-- Standards: how we glue these components together; how we do vertical integration
OGC ISO 19115 -->

+++?image=assets/sdi-components.png
<!-- .slide: data-background-transition="none" -->
+++?image=assets/sdi-components2.png
<!-- .slide: data-background-transition="none" -->
+++?image=assets/sdi-components3.png
<!-- .slide: data-background-transition="none" -->

+++

## Inspired by INSPIRE

<div id="container">
  <div id="content">
    <img src="https://raw.githubusercontent.com/doublebyte1/keynotes/master/assets/babel.jpg" width="80%">
  </div>
  <div id="navbar">
    <ul>
       <li style="font-size:30px">Sharing environmental spatial information among public sector organisations.</li>
       <li style="font-size:30px">Public access to spatial information across Europe.</li>
      <li style="font-size:30px">Assist in policy-making across boundaries.</li>
    </ul>
  </div>
</div>

+++?image=assets/wally.jpg

+++?image=assets/virtualization_before.jpg

---?image=assets/artisan.jpg
<!-- .slide: data-background-transition="none" -->
---?image=assets/artisan2.jpg
<!-- .slide: data-background-transition="none" -->

<!--
# Can do better?
+ Ease of Deployment
+ Speed of Deployment
+ Reproduceabiliy
-->
---
## Can we do better?

- Automation  |
- Portability |
- Scalability |

+++?image=assets/over.jpg

---
## Virtualization

*The thin piece of software that decouples the OS from the physical bare-metal, and allows us to hedge physical hardware.*
<p style="text-align:right;">IBM, 1967</p>

<!--
- Run an OS on top of another OS.
- Shared hardware resources.
- More efficient use of resources.
-->

+++
<!--
scalability, cloud, automation, Reproduceabiliy
-->
- Take an image of an entire virtual host and launch a new virtual instance from it.

![team](assets/word-image133.png)

---
## Hypervisor Based Virtualization
<!--
- Hardware virtualization
- OS agnostic
- Hypervisor sits between the OS and the physical hardware.
-  performance hit:  memory and cpu managers for a guest operating system and hypervisor
good for virtulizing servers, but do we really want to use it to virtualize software?
-->

![team](assets/hypervisor.png)

+++
## Vmware & VirtualBox
<!-- vmware 1999, vbox 2007 -->

![team](assets/hypervisor_examples.png)

---
## Container Based Virtualization
<!--
- Software virtualization, done at OS level
- Each container(well call it guest operating system) shares the same kernel of the base system.
- provides isolation, but not as much as hypervisor Based
- it needs to run in linux
- is much more lightweight
- The Linux kernel's support for namespaces mostly[10] isolates an application's view of the operating environment, including process trees, network, user IDs and mounted file systems, while the kernel's cgroups provide resource limiting, including the CPU, memory, block I/O, and network.
-->
![team](assets/container.png)

+++
## Docker
<!-- docker debut 2013 -->

![team](assets/docker_container.jpg)

+++

<!-- scaling: hundreds of containers in the same machine
It is feasible to have one container per application
-->
## Providing Software
<!-- +++?image=assets/docker_icon.png&size=auto 80% -->
<img src="assets/docker_icon.png" width="70%">

+++
## Orchestrating Software
<img src="assets/compose.png" width="50%">

+++?image=assets/sdi.png
<!-- .slide: data-background-transition="fade" -->
+++?image=assets/docker-compose.png
<!-- .slide: data-background-transition="none" -->

+++
## Providing Servers
![team](assets/docker-machine.png)

---
## Can we do better?

- What about if we want to provide SDIs at scale?

+++
## Meta-System
![team](assets/meta-system.png)

+++?image=assets/virtualization_before.jpg

---
## Microservices Architecture

<pr style="font-size:30px">Decomposes an application into a collection of loosely coupled services.
![team](assets/monolithic.png)

<!--
breaks large software projects into loosely coupled modules, which communicate with each other through REST APIs.
Applications built as a set of modular components are easier to understand, easier to test, and most importantly easier to maintain
-->

+++
## Advantages

- Isolation |
- Simplicity |
- Scalability |

<!-- -developer independence
Lifecycle automation: Individual components are easier to fit into continuous delivery pipelines and complex deployment scenarios not possible with monoliths.
-->

+++?image=assets/docker-ms.png&size=auto 80%

+++?image=assets/docker-compose.png

+++?image=assets/matrioska.jpg

+++?image=assets/ahead.jpg
- <font color="#76448a" style="font-weight: bold;">Microservices are not a silver bullet</font> |
- <font color="#76448a">Docker is a young and fast evolving technology</font> |

<!--
trust
model presumes that the local
government agencies of counties and municipalities
will share their geographic information freely with
government agencies of regions, states and federal
agencies.

In a phenomenon known widely as vertical
integration (Burgess 1999), the detailed information
collected by local agencies should be available to
agencies operating at other levels of government,
ensuring the most complete geographic information
possible

Through the European Commission INSPIRE Directive (European Commission 2007), transposed into national legislation of member states in 2009 (cf. Scottish Government 2009), all European Union countries are required to share environmentally related datasets so that they can be easily accessed by other public organisations within their own and neighbouring countries for the purposes of Community environmental policies and policies or activities that may have an impact on the environment. There is thus an increasing expectation that publicly held data should be available, without undue restriction, to inform decision making about the environment. If the data are not discoverable and accessible they cannot be easily considered alongside other relevant datasets and help positively influence decision-making processes until far too late.

Key to delivering INSPIRE is the establishment of Spatial Data Infrastructures (SDIs). An SDI provides the framework for coordinating the policies, infrastructure and standards needed to acquire, process, distribute, use, maintain and preserve spatial data to deliver GI enabled business applications and services for social, economic and environmental benefits. Although INSPIRE mandates a national approach, SDIs may also be established regionally or thematically. E

-->


---

# Thank You!
## I would love to hear your thoughts

* @fa[twitter] @doublebyte
* @fa[github] @doublebyte1
* @fa[wordpress] doublebyte.net
