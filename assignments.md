---
layout: page
title: Assignments
permalink: /assignments/
---

You can download the assignments here (in PDF format). Also check out assignment's pages for any additional info.


<ul id="archive">
{% for asg in site.assignments reversed %}
      <li class="archiveposturl" style="background: transparent">
        <span><a href="{{ asg.url | prepend: site.baseurl}}">{{ asg.title }}</a></span>        
<strong style="font-size:100%; font-family: 'Titillium Web', sans-serif; float:right">
<span style="font-size:75%;margin-right:.25em; display:inline-block;">Due: </span>
<span style="font-size:75%;color:red;font-weight:bold;margin-right:2.5em; display:inline-block;"> {{ asg.due | date_to_string }}</span>
{% if asg.pdf %}
<a title="Download problems (pdf)" href="
            {% if asg.pdf %}
            {% if asg.pdf contains '://' %}
              {{ asg.pdf }} 
            {% else %}
              {{ asg.pdf | prepend: site.baseurl }} 
            {% endif %}
            {% endif %}
            "><i class="fas fa-file-pdf"></i></a>
{% else %}
      <i class="fas fa-file-pdf"></i>
{% endif %}
{% if asg.attachment %}
&nbsp; <a title="Download attachments (zip)" href="
            {% if asg.attachment contains '://' %}
              {{ asg.attachment }} 
            {% else %}
              {{ asg.attachment | prepend: site.baseurl }} 
            {% endif %}"><i class="fas fa-file-archive"></i></a>
{% else %}
      <i class="fas fa-file-archive">
{% endif %}
</strong> 
      </li>
{% endfor %}
</ul>