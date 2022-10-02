---
layout: base.html
title: STEAM influencers
metaDescription:
  Celebrating people who are sharing and working into STEAM— and inspires the
  And inspiring the next generation of STEAM people with inclusion and equity.
templateEngineOverride: njk
eleventyComputed:
  memberCount: "{{ profiles | length + 1 }}"
---

<section class="hero">
  <div class="hero__content">
    <h1 class="hero__contentHeadline">Celebrating people who are sharing and working into STEAM</h1>
    <p  class="hero__contentByline">And inspiring the next generation of STEAM people with inclusion and equity.</p>
    <div class="hero__buttons">
      <a href="https://github.com/#readme" target="_blank" class="hero__button">Add your profile</a>
      <!-- <a href="https://jamstack.org/discord" target="_blank" class="hero__button hero__button--alt">Join the discord</a> -->
    </div>
  </div>
</section>

<section>
  <ul class="profiles">
  {% for key, profile in profiles %}
      <li class="profiles__item">
        <span class="profiles__itemImgWrapper">
         {% image "./src/_data/images/" + key + ".jpeg", profile.name, "lazy" %}
        </span>
        <span class="profiles__itemTextWrapper">
          <h2 class="profiles__itemName">{{ profile.name }}</h2>
          <p class="profiles__itemBio">{{ profile.bio }}</p>
          <p class="profiles__itemJob">{{ profile.jobTitle }} {% if profile.company.length > 0 %} @ {{ profile.company }}{% endif %}</p>
          <span class="profiles__itemSocials">
            {% if profile.twitterUsername.length > 0 %}
              <a href="https://twitter.com/{{ profile.twitterUsername }}" 
                target="_blank" title="{{ profile.name }} on Twitter">
                {% include "profile_svg/twitter.svg" %}
              </a>
            {% endif %}
            {% if profile.instagramUsername.length > 0 %}
              <a href="https://instagram.com/{{ profile.instagramUsername }}" 
                target="_blank" title="{{ profile.name }} on instagram">
                  {% include "profile_svg/instagram.svg" %}
              </a>
            {% endif %}
            {% if profile.tiktokUsername.length > 0 %}
              <a href="https://tiktok.com/{{ profile.tiktokUsername }}" 
                target="_blank" title="{{ profile.name }} on Tiktok">
                  {% include "profile_svg/tiktok.svg" %}
              </a>
            {% endif %}
            {% if profile.githubUsername.length > 0 %}
              <a href="https://github.com/{{ profile.githubUsername }}" 
              target="_blank" title="{{ profile.name }} on Github">
                {% include "profile_svg/github.svg" %}
              </a>
            {% endif %}
            {% if profile.twitchUsername.length > 0 %}
              <a href="https://twitch.tv/{{ profile.twitchUsername }}" 
                target="_blank" title="{{ profile.name }} on Twitch">
                  {% include "profile_svg/twitch.svg" %}
              </a>
            {% endif %}
            {% if profile.website.length > 0 %}
              <a href="{{ profile.website }}" 
                target="_blank" title="{{ profile.name }}'s Website">
                {% include "profile_svg/globe.svg" %}
              </a>
            {% endif %}
          </span>
        </span>
      </li>
    {% endfor %}
      <li class="profiles__item">
        <span class="profiles__itemImgWrapper profiles__itemImgWrapper--blank">
         {% include "profile_svg/user.svg" %}
        </span>
        <span class="profiles__itemTextWrapper">
          <h2 class="profiles__itemName">Your Name Here</h2>
          <p class="profiles__itemBio">Do you work into STEAM and share content? You should feature on STEAM influencers!</p>
          <p class="profiles__itemJob">Submit a PR on GitHub 👇</p>
           <span class="profiles__itemSocials">
            <a class="profiles__ctaButton" href="" target="_blank">Add your profile</a>
          </span>
        </span>
      </li>
  </ul>
</section>
