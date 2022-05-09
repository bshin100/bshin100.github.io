---
layout: page
title: School Project Highlights
permalink: /school-projects/
published: true
---

Hi! I'm currently an engineering student at Worcester Polytechnic Institute with a double major in mechanical and robotics engineering. While this site was primarily created to showcase and document my personal projects and skills, I felt that it would only be appropriate that I also highlight some of the work that I've accomplished in my project-based college curriculum.

**Contents:**
- [RBE 2001 - Unified Robotics I Final Project]({% link school/RBE2001.md %})
- [RBE 2002 - Unified Robotics II Final Project]({% link school/RBE2002.md %})
- [RBE 3001 - Unified Robotics III Final Project]({% link school/RBE3001.md %})
- [RBE 3002 - Unified Robotics IV Final Project]({% link school/RBE3002.md %})
- [CS 3733 - Software Engineering Final Project]({% link school/CS3733.md %})
- More to come!

----
<div markdown="0">
    <div class="school-projects">
      {% for post in site.tags.SCHOOL %}
        <article class="post">
          <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
          <div class="entry">
            {{ post.excerpt }}
          </div>
          <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
        </article>
      {% endfor %}
    </div>
</div>