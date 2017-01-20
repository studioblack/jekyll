---
layout: page
title: Presskit
permalink: /presskit/
---
<div class="uk-container uk-container-center">
  <div class="row">
    <div class="col-xs-12 col-md-3">
      <div class="navigation">
        <h1 class="nav-header">{{ site.data.data.title }}</h1>
        <a class="nav-header" href="{{ site.data.data.website }}">{{ site.data.data.website }}</a>
        <ul class="uk-nav uk-nav-side">
          <li>
            <a href="#factsheet">Factsheet</a>
          </li>
          <li>
            <a href="#description">Description</a>
          </li>
          <li>
            <a href="#history">History</a>
          </li>
          <li>
            <a href="#projects">Projects</a>
          </li>
          <li>
            <a href="#videos">Videos</a>
          </li>
          <li>
            <a href="#images">Images</a>
          </li>
          <li>
            <a href="#logo">Logo &amp; Icon</a>
          </li>
          <li>
            <a href="#awards">Awards &amp; Recognition</a>
          </li>
          <li>
            <a href="#articles">Selected Articles</a>
          </li>
          <li>
            <a href="#links">Additional Links</a>
          </li>
          <li>
            <a href="#team">Team</a>
          </li>
          <li>
            <a href="#contact">Contact</a>
          </li>
        </ul>
      </div>
    </div>

    <div class="col-xs-12 col-md-9">
      <img src="test.png" width="100%" />

      <div class="row">
        <div class="col-xs-4">
          <h2 id="factsheet">Factsheet</h2>

          <dl>
            <dt>Developer:</dt>
            <dd>
              {{ site.data.data.developer }} <br />
              Based in {{ site.data.data.basedIn }}
            </dd>

            {% if site.data.data.foundingData != null %}
              <dt>Founding date:</dt>
              <dd>{{ site.data.data.foundingData }}</dd>
            {% endif %}

            {% if site.data.data.website != null %}
              <dt>Website:</dt>
              <dd><a href="{{ site.data.data.website }}">{{ site.data.data.website }}</a></dd>
            {% endif %}

            {% if site.data.data.pressContact != null %}
              <dt>Press / Business Contact:</dt>
              <dd><a href="mailto:{{ site.data.data.pressContact }}">{{ site.data.data.pressContact }}</a></dd>
            {% endif %}

            {% if site.data.data.socials != null %}
              <dt>Social:</dt>
              {% for social in site.data.data.socials %}
                <dd><a href="{{ social.url }}">{{ social.name }}</a></dd>
              {% endfor %}
            {% endif %}

            {% if site.data.data.address != null %}
              <dt>Address:</dt>
              {% for line in site.data.data.address %}
                <dd><a href="{{ line.line }}">{{ line.line }}</a></dd>
              {% endfor %}
            {% endif %}

            {% if site.data.data.phone != null %}
              <dt>Phone:</dt>
              <dd><a href="tel:{{ site.data.data.phone }}">{{ site.data.data.phone }}</a></dd>
            {% endif %}
          </dl>
        </div>

        <div class="col-xs-8">
          <h2 id="description">Description</h2>

          <p>
            {{ site.data.data.description }}
          </p>

          <h2 id="history">History</h2>

          <h2 id="projects">Projects</h2>

        </div>
      </div>

      <hr />

      <h2 id="videos">Videos</h2>

      {% for video in site.data.data.videos %}
        {{ video.name }} <a href="http://www.youtube.com/watch?v={{ video.id }}">YouTube</a>

        <div class="uk-responsive-width iframe-container">
          <iframe src="http://www.youtube.com/embed/{{ video.id }}" frameborder="0" width="100%" allowfullscreen></iframe>
        </div>
      {% endfor %}

      <hr />

      <h2 id="images">Images</h2>

      Fill this up

      <hr />

      <h2 id="logo">Logo &amp; Icon</h2>

      Fill this up

      <hr />

      <h2 id="awards">Awards &amp; Recognition</h2>

      <ul>
        {% for award in site.data.data.awards %}
          <li>
            "{{ award.description }}" - {{ award.info }}
          </li>
        {% endfor %}
      </ul>

      <hr />

      <h2 id="articles">Selected Articles</h2>

      <ul>
        {% for quote in site.data.data.quotes %}
          <li>
            "{{ quote.description }}" <br />
            - {{ quote.name }},
            {% if quote.url != null %}
              <a href="{{ quote.url }}">
                {{ quote.website }}
              </a>
            {% else %}
              {{ quote.website }}
            {% endif %}
          </li>
        {% endfor %}
      </ul>


      <hr />

      <h2 id="links">Additional Links</h2>

      <dl>
        {% for link in site.data.data.links %}
          <dt>{{ link.title }}</dt>
          <dd>
            {{ link.description }} <a href="{{ link.url }}">{{ link.url }}</a>
          </dd>
        {% endfor %}
      </dl>


      <hr />

      <div class="row">
        <div class="col-xs-7">
          <h2 id="team">Team &amp; Repeating Collaborators</h2>

          <dl>
            {% for credit in site.data.data.credits %}
              <dt>{{ credit.name }}</dt>
              <dd>{{ credit.role }}</dd>
            {% endfor %}
          </dl>
        </div>

        <div class="col-xs-5">
          <h2 id="contact">Contact</h2>

          {% for contact in site.data.data.contacts %}
            <dt>{{ contact.name }}</dt>
            <dd><a href="{{ contact.url }}">{{ contact.url }}</a></dd>
          {% endfor %}
        </div>
      </div>

      <hr />
    </div>
  </div>
</div>
