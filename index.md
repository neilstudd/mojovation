---
layout: home
title: Welcome to Mojovation Consulting
---

# Because it's all about people.

![Anchorman - jumping](/assets/img/anchorman.gif)

Here at **Mojovation Consulting**, we want to help agile software development teams to grow by nurturing their most valuable assets: their employees. As both teams and individuals, our needs and desires are often sidelined in favour of meeting project goals, achieving OKRs or keeping metrics happy. We're here to show you that all of those things are achievable, whilst also allowing people to showcase their authentic selves.

We offer **agile coaching**, **career advice** and **project consultancy** services to both individuals and organisations. Whether you're starting the first steps of your career, or you're a veteran who's stuck in a rut - we'd love to talk to you about how we can recapture that mojo together. 🚀

> ### Let's start a conversation!  
> * [Learn more about our organisation.](/about)
> * [Learn more about the service packages we provide.](/services) 
> * [Contact us for a free consultation.](/contact)

## Latest blog posts

<div class="archive">
{% for post in site.posts limit:6 %}
  <article class="article">
    <a class="post-link" href="{{ post.url | relative_url }}"><img src="{{ post.image }}" class="thumb" /></a>
    <div><strong><a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></strong><br/>
    {{ post.excerpt }}<br/><br/>
    </div>
  </article>
  {%- endfor -%}
</div>
<div class="pagination">
    <p><strong><a href="/blog">View all blog posts</a></strong><br/>
    <strong><a href="feed.xml">Subscribe to our RSS feed</a></strong></p>
</div>