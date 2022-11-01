---
layout: page
title: About
permalink: /about/
---


{{ social.youtube_channel }}

 {%- if social.youtube -%}<li><a rel="me" href="https://www.youtube.com/{{ social.youtube | cgi_escape | escape }}" target="_blank" title="{{ social.youtube | escape }}"><svg class="svg-icon grey"><use xlink:href="{{ '/assets/minima-social-icons.svg#youtube' | relative_url }}"></use></svg></a></li>{%- endif -%}
  
