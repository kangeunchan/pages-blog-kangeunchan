---
layout: post
title: Today I Learned
date : 2024-09-22
excerpt : Today I Learned Page!
---

# Today I Learned 📕
> 오늘 공부한 내용을 작성하는 페이지 입니다.

---
## Latest Documents
<ul style="list-style-type: none; padding-left: 0; margin-left: 0;">
  {% assign docs_pages = site.pages | where_exp:"page", "page.path contains 'docs/todayilearned'" %}
  {% for page in docs_pages limit:5 %}
    <li style="list-style-type: none; padding: 15px; margin-bottom: 15px; border-bottom: 1px solid #ddd;">
      <a href="{{ site.baseurl }}{{ page.url }}" style="text-decoration: none; color: #0073e6; font-weight: bold; font-size: 1.2em;">{{ page.title }}</a>
      {% if page.date %}
        <p style="font-size: 0.9em; color: #555;">작성일: {{ page.date | date: "%B %d, %Y" }}</p>
      {% else %}
        <p style="font-size: 0.9em; color: #555;">작성일 정보 없음</p>
      {% endif %}
      <p style="color: #333; font-size: 0.95em;">{{ page.excerpt | truncatewords: 20 }}</p>
    </li>
  {% endfor %}
</ul>
