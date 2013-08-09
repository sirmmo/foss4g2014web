---
layout: page
title: FOSS4G 2014
---
{% include JB/setup %}
<div class="container">
    <div class="row">
        <div class="span12">
            <!-- slider -->
            <div class="flexslider" id="map">
                <ul class="slides">
                    {% for place in site.tags.place %}
                    <li data-lat="{{place.lat}}" data-lng="{{place.lng}}" data-zoom="{{place.zoom}}" {% if forloop.first %}class="flex-active-slide"{% endif %}>                                
                     <div class="year hidden">
                        {{ place.date |date:"%Y"}}
                    </div>
                      <div class="flex-caption hidden">
                            <h3>{{ place.title }}</h3>
                            {{ place.content }}
                            <!-- <div class="buttons">
                                <a href="{{ place.url }}" class="btn btn-1 pull-right">read more</a>
                            </div> -->
                        </div>
                    </li>
                    {% endfor %}
                </ul>
            </div>
            <span id="responsiveFlag">
            </span>
            <div class="block-slogan">
                <h2>
                    Sept. 8-13th, 2014
                </h2>
                <div>
                    <p>
                        FOSS4G 2014 will be held in Portland, Oregon
                    </p>
                </div>
            </div>
        </div>
    </div>
</div>
<!-- content -->
<div id="content" class="content-extra">
    <div class="ic">
    </div>
    <div class="row-1">
        <div class="container">
            <div class="row">
                <article class="span12">
                    <h4>From the blog</h4>
                </article>
            </div>
            <div class="row">
                    <ul class="thumbnails thumbnails-1">
                        {% assign counter = '' %}
                        {% for post in site.posts %}
                            {% unless post.tags contains 'place' %}
                            {% if counter.size < 4 %}
                            <li class="span3">
                                {% capture counter %}{{ counter }}*{% endcapture %}
                                <div class="thumbnail thumbnail-1">
                                    <img src="/assets/Flag_of_Cascadia.png" alt="">
                                    <section>
                                        <a href="{{ post.url }}"><h3>{{ post.title }}</h3></a>
                                        <div class="meta">
                                            <time datetime="{{ post.date }}" class="date-1">
                                                <i class="icon-calendar">
                                                </i>
                                                {{ post.date |date: "%m-%d-%Y"}}
                                            </time>
                                            <!-- <div class="name-author">
                                                            <i class="icon-user">
                                                            </i>
                                                            <a href="#">Admin</a>
                                                        </div> -->
                                            <!-- <a href="#" class="comments"><i class="icon-comment"></i> 7 comments</a> -->
                                        </div>
                                        <div class="clear">
                                        </div>
                                        <a href="{{ post.url }}" class="btn btn-1">read more</a>
                                    </section>
                                </div>
                            </li>
                            {% endif %}
                            {% endunless %}
                        {% endfor %}
                    </ul>
            </div>
        </div>
    </div>
</div>
