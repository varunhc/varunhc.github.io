---
layout: about
title: About
permalink: /
subtitle: 

profile:
  align: left
  image: prof_pic.jpg
  image_circular: true # crops the image to make it circular
  address: 

selected_papers: ture # includes a list of papers marked as "selected={true}"
social: true  # includes social icons at the bottom of the page
news: false  # includes a list of news items
---
Hi, I'm currently pursuing a Master's degree in Computer Science at University of California, Irvine.

I have extensive working knowledge as a Software Engineer. In the past couple of years, I have worked on some very
interesting problems like memory leakages, sso redirect problems, container memory management, message broking,
asynchronous schedulers, network latency, caching strategies, and security vulnerabilities. Apart from these, my 
regular work day involves architecting microservices, API design and development, performance testing, and pipelining.

My research interests includes image and signal processing, neural network architectures amd their interpretability, and 
healthcare. I'm also interested in AI for social good, and privacy and fairness in AI. My previous research includes 
ML-powered Lab-on-Chip cytometry and other telemedicine devices. I have also worked on distributed ML, geospatial image 
processing, and a bit of smart contracts.

<br>
<br>
<br>
<br>
<br>
<br>

<h2> Experience </h2>
<div class="timeline">
  <div class="outer">
    <div class="title-cards">
      <div class="info">
        <h4 class="title">Software Engineer</h4>
        <h5 class="title"><img src="https://soroco.com/wp-content/uploads/2021/08/logo-icon.svg" width="56px" height="56px"><b>Soroco</b></h5>
        <h6 class="exper-card"><i>(November, 2020-Present)</i></h6>
        <ul>
          <li>Extensive working experience in developing web services that follow SOAP protocol and REST guidelines in
              Python and Go.
          </li>
          <li>Experience in working with observability tools such as Datadog and ElasticSearch for performance
              monitoring and debugging.
          </li>
          <li>Accustomed to using platforms such as Veracode and Snyk for detecting and fixing security vulnerabilities
              resulting in an 82% improvement in security metrics.
          </li>
          <li>Added single-sign-on (SSO) support and rule-based access control using Keycloak as the identity provider.
          </li>
          <li>Improved authorization response time by 60% by designing and implementing an efficient Redis cache for
              user authorization information which supported constant time O(1) lookup for 95% of the cases.
          </li>
          <li>Worked with Azure CI/CD pipelines to automate testing, packaging, and deployments.</li>
        </ul>
      </div>
    </div>
    <div class="title-cards">
      <div class="info">
        <h4 class="title">Data Scientist Intern</h4>
        <h5 class="title"><img src="https://www.wipro.com/content/dam/nexus/en/wipro-logo-new-og-502x263.jpg" width="60px" height="30px"><b>Wipro</b></h5>
        <h6 class="exper-card"><i>(January-May, 2020)</i></h6>
        <ul>
          <li>Worked with one of the largest telecom providers in the world to create a product to proactively monitor 
              SNMP event logs using event correlation, clustering, and predictive analysis.
          </li>
          <li>Created 172 situations from 3859 alarms with 87% accuracy based on the correlation of the alarms, and
              performed root cause analysis.
          </li>
          <li>Incorporated functionalities such as dynamic update of the element correlation and resolution suggestion.
          </li>
        </ul>
      </div>
    </div>
    <div class="title-cards">
      <div class="info">
        <h4 class="title">Machine Learning Engineer Intern</h4>
        <h5 class="title"><img src="https://upload.wikimedia.org/wikipedia/en/thumb/9/9a/ONGC_Logo.svg/1200px-ONGC_Logo.svg.png" width="56px" height="56px" style="margin-right:10px;"><b>Oil and Natural Gas Corporation</b></h5>
        <h6 class="exper-card"><i>(June-July, 2019)</i></h6>
        <ul>
          <li>Developed U-Net with skip connections for the generative model and generated seismic survey paths with an 
              accuracy of 72%.
          </li>
        </ul>
      </div>
    </div>
    <!-- <div class="card">
      <div class="info">
        <h3 class="title">Title 4</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. </p>
      </div>
    </div>
    <div class="card">
      <div class="info">
        <h3 class="title">Title 5</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. </p>
      </div>
    </div> -->
  </div>
</div>
<h2> Education </h2>
  <table class="table table-sm table-borderless">
              {%- assign news = site.news | reverse -%}
              {% if site.news_limit %}
              {% assign news_limit = site.news_limit %}
              {% else %}
              {% assign news_limit = news_size %}
              {% endif %}
              {% for item in news limit: news_limit %} 
                <tr>
                  <th scope="row">{{ item.date | date: "%b, %Y" }}</th>
                  <td>
                    {% if item.inline -%} 
                      {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
                    {%- else -%} 
                      <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
                    {%- endif %} 
                  </td>
                </tr>
              {%- endfor %} 
              </table>
<h2> Projects </h2>

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
