---
layout: first
# title: The Tao of Me
tagline: "Once apon a time I fancied myself a writer, a journalist, and even a starving artist. During those days I created an archive of fictional stories. This is mostly a collection of those, with maybe a post added from time to time. Many of my stories are unfinished, so if you'd like to give them a good ending, please do. I look forward to seeing them improved."
---

<section class="jumbotron">
    <article class="container">
        <h1 class="post-title-main" itemprop="name headline">{{ site.title }}</h1>
        <p class="post-list post-box">{{ page.tagline }}</p>
    </article>
</section>

<section id="page-content">
    <article class="container">
        <div class="post-list">
            {%  for post in site.posts %}
            <div class="post-box">
                <div class="post-title">
                    <a class="post-title" href="{{post.url | prepend:site.baseurl }}" > {{ post.title }}</a>
                </div>
                <div class="post-excerpt">
                    {{ post.content | strip_html | truncatewords:20}}
                </div>
                <div class="posted">
                    posted on
                    <span class="posted-on">
                        {{ post.date | date: "%A, %B %-d, %Y" }}
                    </span>
                    <span class="in">
                        in
                    </span>
                    <span class="categories-on">
                        {% for category in post.categories %}
                        {{ category }} &nbsp;{% if forloop.last %}{% else %},{% endif %}
                        {% endfor %}
                    </span>
                </div>
            </div>
            {% endfor %}
        </div>
    </article>
</section>