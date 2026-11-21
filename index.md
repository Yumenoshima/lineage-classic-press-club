---
layout: default
title: ニュース
---

<div class="news-site">

  <!-- NEWS HEADER -->
  <div class="news-masthead">
    <div class="news-eyebrow">ONLINE GAME NEWS & MEDIA</div>
    <h1>LINEAGE CLASSIC<br>PRESS CLUB</h1>
    <p>リネージュクラシック ニュース・報道・情報メディア</p>
  </div>

  <!-- NAVIGATION -->
  <nav class="news-nav">
    <a href="/">HOME</a>
    <a href="/category/news/">NEWS</a>
    <a href="/category/incident/">INCIDENT</a>
    <a href="/category/operation/">運営情報</a>
    <a href="/category/community/">COMMUNITY</a>
    <a href="/about/">ABOUT</a>
  </nav>

  <!-- TOP STORY -->
  <section class="top-story">
    <div class="top-story-label">TOP STORY</div>
    <h2>リネージュクラシックの最新情報を発信</h2>
    <p>
      ゲーム内のニュース、運営情報、プレイヤーコミュニティ、
      不正行為に関する情報などを掲載します。
    </p>
    <a href="/news/" class="read-more">記事を読む →</a>
  </section>

  <!-- LATEST NEWS -->
  <section class="latest-news">
    <div class="section-heading">
      <h2>最新ニュース</h2>
      <span>LATEST ARTICLES</span>
    </div>

    <div class="news-list">

      {% assign sorted_posts = site.posts | sort: "date" | reverse %}

      {% for post in sorted_posts limit:10 %}
      <article class="news-card">

        <div class="news-meta">
          <span class="news-category">
            {{ post.categories | first | default: "NEWS" }}
          </span>
          <time>
            {{ post.date | date: "%Y.%m.%d" }}
          </time>
        </div>

        <h3>
          <a href="{{ post.url | relative_url }}">
            {{ post.title }}
          </a>
        </h3>

        <p>
          {{ post.excerpt | strip_html | truncate:120 }}
        </p>

        <a class="article-link" href="{{ post.url | relative_url }}">
          READ ARTICLE →
        </a>

      </article>
      {% endfor %}

      {% if site.posts.size == 0 %}
      <div class="empty-news">
        <p>現在、ニュース記事はありません。</p>
      </div>
      {% endif %}

    </div>
  </section>

  <!-- SIDEBAR -->
  <aside class="news-sidebar">
    <h2>ABOUT THIS MEDIA</h2>
    <p>
      Lineage Classic Press Clubは、
      リネージュクラシックに関する情報を発信するメディアです。
    </p>

    <h2>NEWS CATEGORIES</h2>
    <ul>
      <li><a href="/category/news/">ニュース</a></li>
      <li><a href="/category/incident/">事件・トラブル</a></li>
      <li><a href="/category/operation/">運営・公式情報</a></li>
      <li><a href="/category/community/">コミュニティ</a></li>
      <li><a href="/category/analysis/">分析・考察</a></li>
    </ul>
  </aside>

  <!-- FOOTER -->
  <div class="news-footer">
    <p>LINEAGE CLASSIC PRESS CLUB</p>
    <p>Independent Information & News</p>
  </div>

</div>
