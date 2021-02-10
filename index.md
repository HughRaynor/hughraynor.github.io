---
layout: default
title: Home
---
## Most Recent Post
{% assign post = site.posts.first %}
<div class="c-hero" style="background: url({{post.thumbnail_image.large | relative_url}})bottom center / cover no-repeat;">
   <h1 class="c-hero__title">{{ post.title }}</h1>
   {{ post.intro | markdownify  }}
   <a href="{{ post.url }}" class="btn--hero">Read the full Post</a>
</div>

<div class="c-feature">
    {% for page in site.pages %}
        {% if page.url == '/about.html' %} 
            <img src="{{ page.profile_image.small }}" alt="Profie Picture" class="c-feature__image" />
            <div class="c-feature__text">
                <h2><a href="{{ page.url }}">{{ page.title }}</a></h2>
                <p>{{ page.intro }}</p>
            </div>
           
        {% endif %}
    {% endfor %}
 </div>