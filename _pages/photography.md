---
layout: single
title: "Photography"
permalink: /photography/
---

<style>
  .photo-gallery {
    display: flex;
    flex-wrap: wrap;
    gap: 15px; /* 图片之间的间距 */
    justify-content: center;
  }
  .photo-item {
    flex: 1 1 calc(33.333% - 15px); /* 桌面端每行显示3张图片 */
    box-sizing: border-box;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  }
  .photo-item img {
    width: 100%;
    height: auto;
    display: block;
    transition: transform 0.3s ease;
  }
  .photo-item:hover img {
    transform: scale(1.05);
  }
  /* 移动端适配：每行显示1张图片 */
  @media (max-width: 768px) {
    .photo-item {
      flex: 1 1 calc(100% - 15px);
    }
  }
</style>

<div class="photo-gallery">
  {% for photo in site.data.photography %}
    <div class="photo-item">
      <a href="{{ photo.image_path | relative_url }}" title="{{ photo.caption }}">
        <img src="{{ photo.image_path | relative_url }}" alt="{{ photo.caption }}">
      </a>
    </div>
  {% endfor %}
</div>
