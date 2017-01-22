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
            <a href="#features">Features</a>
          </li>
          <li>
            <a href="#videos">Videos</a>
          </li>
          <li>
            <a href="#screenshots">Screenshots</a>
          </li>
          <li>
            <a href="#illustrations">Illustrations &amp; Concept Art</a>
          </li>
          <li>
            <a href="#logos">Logo &amp; Icon</a>
          </li>
          {% if site.data.data.music != null %}
            <li>
              <a href="#music">Music</a>
            </li>
          {% endif %}
          {% if site.data.data.awards != null %}
            <li>
              <a href="#awards">Awards &amp; Recognition</a>
            </li>
          {% endif %}
          {% if site.data.data.articles != null %}
            <li>
              <a href="#articles">Selected Articles</a>
            </li>
          {% endif %}
          {% if site.data.data.links != null %}
            <li>
              <a href="#links">Additional Links</a>
            </li>
          {% endif %}
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
      <img src="{{ site.data.data.featureImage }}" width="100%" />

      <p>
        Welcome to the Potionomics press kit! This kit contains the necessary information to grow more familiar with our
        project and team in order to write articles regarding the game. Additional information can be found on our
        website though you can contact <a href="mailto:media@voraciousgames.com">media@voraciousgames.com</a> for more info.
      </p>

      <div class="row">
        <div class="col-xs-4">
          <h2 id="factsheet">Factsheet</h2>

          <dl>
            <dt>Developer:</dt>
            <dd>
              {{ site.data.data.developer }} <br />
              Based in {{ site.data.data.basedIn }}
            </dd>

            {% if site.data.data.website != null %}
              <dt>Website:</dt>
              <dd><a href="{{ site.data.data.website }}">{{ site.data.data.website }}</a></dd>
            {% endif %}

            {% if site.data.data.pressContact != null %}
              <dt>Press / Business Contact:</dt>
              <dd><a href="mailto:{{ site.data.data.pressContact }}">{{ site.data.data.pressContact }}</a></dd>
            {% endif %}

            {% if site.data.data.releaseDate != null %}
              <dt>Release date:</dt>
              <dd>{{ site.data.data.releaseDate }}</dd>
            {% endif %}

            {% if site.data.data.platforms != null %}
              <dt>Platforms:</dt>
              {% for platform in site.data.data.platforms %}
                <dd>
                  {% if platform.url != null %}
                    <a href="{{ platform.url }}">{{ platform.name }}</a>
                  {% else %}
                    {{ platform.name }}
                  {% endif %}
                </dd>
              {% endfor %}
            {% endif %}

            {% if site.data.data.availability != null %}
              <dt>Availability:</dt>
              <dd>{{ site.data.data.availability }}</dd>
            {% endif %}

            {% if site.data.data.price != null %}
              <dt>Price:</dt>
              <dd>{{ site.data.data.price }}</dd>
            {% endif %}

            {% if site.data.data.rating != null %}
              <dt>ESRB:</dt>
              <dd>{{ site.data.data.rating }}</dd>
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
          {% if site.data.data.description != null %}
            <h2 id="description">Description</h2>

            {% for paragraph in site.data.data.description %}
              <p>
                {{ paragraph.paragraph }}
              </p>
            {% endfor %}

          {% endif %}

          {% if site.data.data.history != null %}
            <h2 id="history">History</h2>

            {% for paragraph in site.data.data.history %}
              <p>
                {{ paragraph.paragraph }}
              </p>
            {% endfor %}

          {% endif %}

          {% if site.data.data.features != null %}
            <h2 id="features">Features</h2>

            <ul>
              {% for feature in site.data.data.features %}
                <li>
                  {{ feature.description }}
                </li>
              {% endfor %}
            </ul>

          {% endif %}
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

      {% if site.data.data.screenshots != null %}
        <h2 id="screenshots">Screenshots</h2>

        {% for screenshot in site.data.data.screenshots %}
          {% assign mod = forloop.index | modulo:3 %}
          {% if forloop.index == 1 or mod == 1 %}
            <div class="row image-row">
          {% endif %}
              <div class="col-xs-4">
                <a href="{{ screenshot.url }}" target="_blank">
                  <img width="100%" src="{{ screenshot.url }}" />
                </a>
              </div>
          {% if mod == 0 or forloop.last  %}
            </div>
          {% endif %}
        {% endfor %}

        <hr />
      {% endif %}

      {% if site.data.data.illustrations != null %}
        <h2 id="illustrations">Illustrations &amp; Concept Art</h2>

        {% for illustration in site.data.data.illustrations %}
          {% assign mod = forloop.index | modulo:3 %}
          {% if forloop.index == 1 or mod == 1 %}
            <div class="row image-row">
          {% endif %}
              <div class="col-xs-4">
                <a href="{{ illustration.url }}" target="_blank">
                  <img width="100%" src="{{ illustration.url }}" />
                </a>
              </div>
          {% if mod == 0 or forloop.last  %}
            </div>
          {% endif %}
        {% endfor %}

        <hr />
      {% endif %}

      {% if site.data.data.logos != null %}
        <h2 id="logos">Logos &amp; Icons</h2>

        {% for logo in site.data.data.logos %}
          {% assign mod = forloop.index | modulo:3 %}
          {% if forloop.index == 1 or mod == 1 %}
            <div class="row image-row">
          {% endif %}
              <div class="col-xs-4">
                <a href="{{ logo.url }}" target="_blank">
                  <img width="100%" src="{{ logo.url }}" />
                </a>
              </div>
          {% if mod == 0 or forloop.last  %}
            </div>
          {% endif %}
        {% endfor %}

        <hr />
      {% endif %}

      {% if site.data.data.awards != null %}
        <h2 id="awards">Awards &amp; Recognition</h2>

        <ul>
          {% for award in site.data.data.awards %}
            <li>
              "{{ award.description }}" - {{ award.info }}
            </li>
          {% endfor %}
        </ul>

        <hr />
      {% endif %}

      {% if site.data.data.articles != null %}
        <h2 id="articles">Selected Articles</h2>

        <ul>
          {% for article in site.data.data.articles %}
            <li>
              "{{ article.description }}" <br />
              - {{ article.name }},
              {% if article.url != null %}
                <a href="{{ article.url }}">
                  {{ article.website }}
                </a>
              {% else %}
                {{ article.website }}
              {% endif %}
            </li>
          {% endfor %}
        </ul>

        <hr />
      {% endif %}

      {% if site.data.data.links != null %}
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
      {% endif %}

      {% if site.data.data.music != null %}
        <h2 id="music">Music</h2>

        <p>
          Potionomics features a live-orchestral score! Have a listen to a few samples:
        </p>

        <ul>
          {% for song in site.data.data.music %}
            <li>
              <a href="{{ song.url }}">
                {{ song.url }}
              </a>
            </li>
          {% endfor %}
        </ul>

        <hr />
      {% endif %}

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
