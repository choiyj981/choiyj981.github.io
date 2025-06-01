---
layout: default
title: "Welcome to My Dev Blog"
---

<!-- ───────────────────────────────────────────────────
     1. 인라인 CSS: 페이지 전체 스타일 정의
     ─────────────────────────────────────────────────── -->
<style>
  /* ───────────────────────────────────────────────────
     전체 컨테이너 여백/폰트 설정
     ─────────────────────────────────────────────────── */
  body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
                 Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
    line-height: 1.6;
    color: #333;
    padding: 0 1rem;
  }

  h1, h2, h3 {
    color: #222;
    margin-bottom: 0.5rem;
  }

  a {
    text-decoration: none;
    color: #0366d6;
  }
  a:hover {
    text-decoration: underline;
  }

  /* ───────────────────────────────────────────────────
     메인 헤더 / 설명 영역
     ─────────────────────────────────────────────────── */
  .intro {
    max-width: 800px;
    margin: 2rem auto;
    text-align: center;
  }
  .intro p {
    margin-top: 0.5rem;
    font-size: 1.1rem;
    color: #555;
  }

  /* ───────────────────────────────────────────────────
     포스트 목록을 담을 컨테이너
     ─────────────────────────────────────────────────── */
  .posts-container {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    max-width: 800px;
    margin: 2rem auto;
  }

  /* ───────────────────────────────────────────────────
     각 포스트 카드 스타일
     ─────────────────────────────────────────────────── */
  .post-card {
    border: 1px solid #e1e4e8;
    border-radius: 8px;
    padding: 1rem 1.5rem;
    transition: box-shadow 0.2s ease, border-color 0.2s ease;
    background-color: #fff;
  }
  .post-card:hover {
    border-color: #0366d6;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  }

  .post-header {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: 0.75rem;
  }
  .post-title {
    font-size: 1.4rem;
    margin: 0;
    color: #0366d6;
  }
  .post-title:hover {
    color: #024e9b;
  }
  .post-date {
    font-size: 0.9rem;
    color: #6a737d;
  }

  .post-excerpt {
    color: #444;
    margin-top: 0.5rem;
    font-size: 1rem;
    line-height: 1.5;
  }
</style>

<!-- ───────────────────────────────────────────────────
     2. 페이지 상단: 제목과 간단한 소개
     ─────────────────────────────────────────────────── -->
<div class="intro">
  <h1>👋 Welcome to My Dev Blog</h1>
  <p>
    이 공간은 Notion에서 작성한 글을 자동으로 변환해 보여주는  
    “개발 일지 & TIL” 블로그입니다. 최신 포스트를 아래에서 확인해보세요!
  </p>
</div>

<!-- ───────────────────────────────────────────────────
     3. 동적으로 포스트 목록 뿌려주기
     ─────────────────────────────────────────────────── -->
<div class="posts-container">
  {% for post in site.posts %}
    <div class="post-card">
      <div class="post-header">
        <!-- 포스트 제목 -->
        <h2 class="post-title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h2>
        <!-- 포스트 날짜 -->
        <span class="post-date">
          {{ post.date | date: "%Y-%m-%d" }}
        </span>
      </div>
      <!-- 포스트 요약: excerpt가 없을 경우 content 일부를 가져옴 -->
      <div class="post-excerpt">
        {{ post.excerpt | strip_html | truncate: 150 }}
      </div>
    </div>
  {% endfor %}
</div>
