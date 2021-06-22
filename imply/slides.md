---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/1920x1080/weekly?nature
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
download: true
---

# Apache Druid and Imply

Gaétan Collaud

22nd June 2021

<a href="https://github.com/gaetancollaud/presentations" target="_blank" alt="GitHub"
  class="abs-br m-6 text-xl icon-btn opacity-50 !border-none !hover:text-white">
  <carbon-logo-github />
</a>

---
layout: image-right
image: https://source.unsplash.com/1920x1080/weekly?nature
---

# Summary

- **Apache Druid** - Database for analytics
- **Imply** - Apache Druid as a service
- **Imply Pivot** - The visualisation tool of Imply
- **Apache Superset** - Alternative to Pivot
- **Demo** - Show me some data !
- **Questions** - I'm sure you have one

---
layout: image-left
image: https://s01.sgp1.cdn.digitaloceanspaces.com/article/124353-huqumrjvmo-1563950293.jpg
---

# Context

Sales analytics

Our customer has 1k+ shops with 300k+ products and do sales predictions every week.

They currently do analytics with excel...

Which is ... kinda slow ...

So they make aggregation (for instance they group all the milk related products)

---

# Apache druid

"Apache Druid is a high performance real-time analytics database."

Druid is composed of multiple services and each services has it's defined scope

SQL query language

Immutable data coming from different sources (makes copy)

Goal is to answer to any query (even multiple Terra Bytes) under one second

Joins possible, but limited and relatively slow. It's best to flatten the data

Index everything ! Each dimension has its own dictionary

Not that easy to setup...

---

# Apache Druid Architecture

<img border="rounded" src="https://druid.apache.org/docs/latest/assets/druid-architecture.png">

---
layout: image-right
image: https://source.unsplash.com/1920x1080/weekly?nature
---

# Under the hood

segmentation/partition => Same as kafka 

Time based but can also be split on a dimension.

"Perfect" segment is around 700mb

Rollout => "compact" the data

Time base eviction

Currently, join table are in memory (limitation)

---

# UI of apache Druid 

<img border="rounded" src="https://miro.medium.com/max/2400/1*9NxhsXfy9-xmPVshxOZW7Q.png">

---
layout: image-right
image: https://miro.medium.com/max/2400/1*4whEJtKe9-Ab6bvX6pFcng.png
---

# Add data


Ingress data from: 
* Kafka
* S3
* Simple http queries
* local upload
* Druid itself (reindex)
* ...

---

# Configure fields

<img border="rounded" src="https://www.datocms-assets.com/11147/1561671382-data-loader.png">

---
layout: image-right
image: https://source.unsplash.com/1920x1080/weekly?nature
---

# Imply

Confluent, know them ?

Imply is like confluent

but for Apache Druid and not kafka

Main contributor of Apache Druid

Products:
* Imply Pivot
* Imply Clarity
* Imply Manager
* Imply Cloud

---

# Imply pivot

<img border="rounded" src="https://www.datocms-assets.com/11147/1560871552-screenshot-dashboard.png">

---
layout: image-right
image: https://www.datocms-assets.com/11147/1560871552-screenshot-dashboard.png
---

# Imply pivot

Rapid data exploration

Every change trigger a query

Was open source:
 * https://github.com/implydata/pivot

Forks can be found:
 * https://github.com/allegro/turnilo

Demo later ;)

---

# Apache superset

<img border="rounded" src="https://superset.apache.org/images/dashboard3.png">

---
layout: image-right
image: https://superset.apache.org/images/dashboard3.png
---

# Apache superset

100% Opensource

Supports a lot of databases (including Apache Druid)

Supports a lot of different visualizations

Edit mode - View mode

Very customizable
* CSS customization
* plugin development

Demo later ;)

---
layout: center
---

# Questions so far ?
<img center border="rounded" src="https://media0.giphy.com/media/l378fZRQlBmeN0nm0/giphy.gif?cid=ecf05e47fnmossf0bh28k6zqvpuo90o84sqb7yjiwwbwdgon&rid=giphy.gif&ct=g">

---
layout: center
---

# Demo 


<img center border="rounded" src="https://media0.giphy.com/media/xT5LMH24b54rPyoEj6/giphy.gif?cid=ecf05e47cue969veyrctubh821bkt2pw6qhdjqlrmi094cks&rid=giphy.gif&ct=g">


---
layout: center
---

# Thanks

...for your attention

<img center border="rounded" src="https://media1.giphy.com/media/3oz8xIsloV7zOmt81G/giphy.gif?cid=ecf05e478vnxie51papr4y77ihtg5f2079gzfk2vyurn4bpj&rid=giphy.gif&ct=g">

