---
permalink: /
title: "Heng Xu"
description: "Heng Xu's personal homepage — research on AI infrastructure, networking systems, data center networks, edge computing, and embedded systems."
author_profile: false
redirect_from:
  - /about/
  - /about.html
---

{% include base_path %}

<section class="home-intro-flow">
  <aside class="home-intro-float">
    <div class="home-intro-float__main">
      <div class="home-intro-float__left">
        <h1>Heng Xu</h1>
        <p class="home-intro-float__links home-intro-float__links--top">
          <a href="https://orcid.org/0009-0001-1599-8200" target="_blank" rel="noopener noreferrer">𝐎𝐑𝐂𝐈𝐃</a>
        </p>
        <p class="home-intro-float__links home-intro-float__links--middle">
          <a href="https://github.com/jhlxp" target="_blank" rel="noopener noreferrer">𝐆𝐢𝐭𝐇𝐮𝐛</a>
        </p>
        <p class="home-intro-float__links home-intro-float__links--bottom">
          <a href="https://scholar.google.com/citations?user=zav19AkAAAAJ&hl=zh-CN&oi=sra" target="_blank" rel="noopener noreferrer">𝐆𝐨𝐨𝐠𝐥𝐞 𝐒𝐜𝐡𝐨𝐥𝐚𝐫</a>
        </p>
      </div>
      <img src="/photo/xuheng.png" alt="Heng Xu" class="home-intro-float__avatar" />
    </div>
  </aside>

  <!--
    Add your self-introduction paragraphs below.
    The text will automatically wrap around the profile box on the top-right.
  -->
  <div class="home-intro-text">
    <p>
      I received my B.E. and M.E. degrees from Beijing Jiaotong University, where my research focused on networking systems. My current research interests span AI infrastructure, scalable systems, and data center networks, with a focus on topology, routing, load balancing, congestion control, scheduling, and placement. I also work on edge computing and embedded systems, including edge intelligence and efficient edge transport. My current collaborator and mentor is <a href="https://franklee94.github.io/" target="_blank" rel="noopener noreferrer" class="home-intro-text__mentor-link">Prof. Jialong Li</a>.
    </p>
  </div>

  <section class="home-selected-pubs">
    <h2>Selected Publications</h2>
    {% assign selected_publications = site.publications | where_exp: "item", "item.selected == true" %}
    {% assign dc_cloud_publications = selected_publications | where: "selected_area", "data-center-cloud" | sort: "selected_order" %}
    {% assign edge_terminal_publications = selected_publications | where: "selected_area", "edge-terminal" | sort: "selected_order" %}

    <div class="home-selected-pubs__group">
      <h3 class="home-selected-pubs__group-title">Scope 1: Datacenter and Cloud</h3>
      <div class="publication-cards">
        {% for post in dc_cloud_publications %}
          <article class="publication-card">
            <h3 class="publication-card__title">
              {% if post.status == "submission" %}
                <span class="publication-card__status-badge">[Under Review]</span>
              {% endif %}
              {% if post.paperurl %}
                <a href="{{ post.paperurl }}" target="_blank" rel="noopener noreferrer">{{ post.title }}</a>
              {% else %}
                <a href="{{ base_path }}{{ post.url }}" rel="permalink">{{ post.title }}</a>
              {% endif %}
            </h3>
            {% if post.excerpt %}
              <p class="publication-card__authors">{{ post.excerpt }}</p>
            {% endif %}
            <p class="publication-card__venue"><i>{{ post.venue }}</i>, {{ post.date | default: "1900-01-01" | date: "%Y" }}</p>
          </article>
        {% endfor %}
      </div>
    </div>

    <div class="home-selected-pubs__group">
      <h3 class="home-selected-pubs__group-title">Scope 2: Edge and Terminal Systems</h3>
      <div class="publication-cards">
        {% for post in edge_terminal_publications %}
          <article class="publication-card">
            <h3 class="publication-card__title">
              {% if post.status == "submission" %}
                <span class="publication-card__status-badge">[Under Review]</span>
              {% endif %}
              {% if post.status == "submission" %}
                {{ post.title }}
              {% else %}
                {% if post.paperurl %}
                  <a href="{{ post.paperurl }}" target="_blank" rel="noopener noreferrer">{{ post.title }}</a>
                {% else %}
                  <a href="{{ base_path }}{{ post.url }}" rel="permalink">{{ post.title }}</a>
                {% endif %}
              {% endif %}
            </h3>
            {% if post.excerpt %}
              <p class="publication-card__authors">{{ post.excerpt }}</p>
            {% endif %}
            <p class="publication-card__venue"><i>{{ post.venue }}</i>, {{ post.date | default: "1900-01-01" | date: "%Y" }}</p>
          </article>
        {% endfor %}
      </div>
    </div>
  </section>

  <section class="home-experience">
    <h2>Experience</h2>
    <ul class="home-experience__list">
      <li class="home-experience__item">
        <div class="home-experience__line"><span class="home-experience__period-inline">2025 - Present</span>, Research Assistant, SUAT</div>
      </li>
      <li class="home-experience__item">
        <div class="home-experience__line"><span class="home-experience__period-inline">2024</span>, UAV Architecture Systems Intern, Meituan Ltd.</div>
      </li>
    </ul>
  </section>

  <section class="home-education">
    <h2>Education</h2>
    <ul class="home-education__list">
      <li class="home-education__item">
        <div class="home-education__line"><span class="home-education__period-inline">2022 - 2025</span>, M.S., Beijing Jiaotong University</div>
      </li>
      <li class="home-education__item">
        <div class="home-education__line"><span class="home-education__period-inline">2018 - 2022</span>, B.E., Beijing Jiaotong University</div>
      </li>
    </ul>
  </section>

  <!--
  <div class="home-intro-float__photo">
    <div class="home-intro-float__photo-placeholder">Photo</div>
  </div>
  -->
</section>