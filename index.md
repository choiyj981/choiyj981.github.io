---
layout: home
title: "Welcome to My Dev Blog"
description: "Notion에서 작성한 글을 자동으로 올려주는 개발 블로그입니다!"
---

<style>
.intro {
  text-align: center;
  margin: 2rem auto;
  max-width: 800px;
}
.intro h1 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}
.intro p {
  font-size: 1.2rem;
  color: #666;
}

.posts {
  max-width: 800px;
  margin: 3rem auto;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}
.post-card {
  border: 1px solid #ddd;
  padding: 1rem 1.5rem;
  border-radius: 8px;
  background: #fff;
  transition: box-shadow 0.2s ease;
}
.post-card:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
}
.post-title {
  font-size: 1.3rem;
  color: #0366d6;
  margin: 0;
}
.post-date {
  font-size: 0.9rem;
  color: #888;
}
</style>

<div class="intro">
  <h1>👋 Welcome to My Dev Blog</h1>
  <p>Notion에서 작성한 TIL, 공부 기록들이 자동으로 올라오는 블로그입니다.</p>
</div>

<div class="posts">
  {% for post in site.posts %}
  <div class="post-card">
    <a href="{{ post.url | relative_url }}" class="post-title">{{ post.title }}</a>
    <div class="post-date">{{ post.date | date: "%Y-%m-%d" }}</div>
    <p>{{ post.excerpt | strip_html | truncate: 120 }}</p>
  </div>
  {% endfor %}
</div>
