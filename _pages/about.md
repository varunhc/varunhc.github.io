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
Hi, I currently work as a Software Engineer at Soroco.


My research interests includes image processing, computer vision, signal processing and healthcare. 
<br>
<br>
<br>
<br>
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
        <h3 class="title">Software Engineer</h3>
        <h4 class="title">Soroco</h4>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. </p>
      </div>
    </div>
    <div class="title-cards">
      <div class="info">
        <h3 class="title">Data Scientist Intern</h3>
        <h3 class="title">Wipro</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. </p>
      </div>
    </div>
    <div class="title-cards">
      <div class="info">
        <h3 class="title">Machine Learning Engineer Intern</h3>
        <h4 class="title">Oil and Natural Gas Corporation</h4>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. </p>
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
