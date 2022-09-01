---
layout: home
title: Welcome to Mojovation Consulting
---

# Because it's all about people.

![Anchorman - jumping](/assets/img/anchorman.gif)

Here at **Mojovation Consulting**, we want to help agile software development teams to grow by nurturing their most valuable assets: their employees. As both teams and individuals, our needs and desires are often sidelined in favour of meeting project goals, achieving OKRs or keeping metrics happy. We're here to show you that all of those things are achievable, whilst also allowing people to showcase their authentic selves.

We offer **agile coaching**, **career advice** and **project consultancy** services to both individuals and organisations. Whether you're starting the first steps of your career, or you're a veteran who's stuck in a rut - we'd love to talk to you about how we can recapture that mojo together. 🚀

> **_Let's start a conversation!_** 👇  
> * [Learn more about our organisation.](/about)
> * [Learn more about the service packages we provide.](/services) 
> * [Contact us for a free consultation.](/contact)

### 👉 Read our latest [blog posts](/blog/):

<ul>
  {% for post in site.posts limit:5 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
  <li>Read all {{ site.posts | size}} posts in our <a href="/blog/">blog archive</a></li>
  <li>Check out our {{ site.tags.books | size}} <a href="/books/">book reviews</a></li>
  <li>Subscribe to our <a href="feed.xml">RSS feed</a></li>
</ul>