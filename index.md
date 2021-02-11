---
layout: default
title: Home
---
# Home

{% assign post = site.posts.first %}
<div class="c-hero" style="background: url({{post.thumbnail_image.large | relative_url}})bottom center / cover no-repeat;">
   <h1 class="c-hero__title">{{ post.title }} · {% if post.comments %}<a href="https://hray.co.uk{{ post.url }}#disqus_thread" class="disqus-comment-count">Comments</a>{% endif %}</h1>
   {{ post.intro | markdownify  }}
   <a href="{{ post.url }}" class="btn--hero">Read the full Post</a>
</div>

<div class="constrain">
    <h1>More posts</h1> 
    <section class="card-list">
            {% for post in site.posts offset:1 %}
            <div class="card">
                    <img src="{{ post.thumbnail_image.small }}" />
                    <div class="card-details">
                    <h3>{{ post.date | date:"%d %b" }} - {{ post.title }} · {% if post.comments %}<a href="{{ post.url }}#disqus_thread" class="disqus-comment-count">Comments</a>{% endif %}</h3>
                <a href="{{ post.url }}" class="btn">Read More</a>
                    </div>
                </div>
            {% endfor %}
           
    </section>
 </div>