---
title: Magic shop
icon: fas fa-store
order: 0
layout: redirect
redirect_url: https://t.me/hugogord_price
---

<style>
  .shop-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
  }
  .shop-title {
    font-size: 2.5em;
    color: #333;
    margin-bottom: 20px;
  }
  .category-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin-top: 20px;
  }
  .category-card {
    /* Убираем белый фон и рамку */
    background-color: transparent;
    border: none;
    padding: 0; /* Убираем внутренние отступы */
    transition: transform 0.2s ease;
  }
  .category-card:hover {
    transform: translateY(-5px);
  }
  .category-btn {
    display: block;
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    color: white;
    text-decoration: none;
    border-radius: 5px;
    font-size: 1.1em;
    text-align: center;
    transition: background-color 0.2s ease;
  }
  .category-btn:hover {
    background-color: #0056b3;
  }
  .prompt-tip {
    background-color: #f8f9fa;
    padding: 10px;
    border-radius: 5px;
    margin-bottom: 20px;
    font-style: italic;
    color: #555;
  }
  @media (max-width: 600px) {
    .shop-title {
      font-size: 1.8em;
    }
    .category-grid {
      grid-template-columns: 1fr;
    }
    .category-btn {
      font-size: 1em;
    }
  }
</style>

<div class="shop-container">
  <h1 class="shop-title">Магічна крамниця</h1>
  
  {{ "> Натисніть кнопку, щоб перейти до категорії послуг." | markdownify | replace: '<blockquote>', '<blockquote class="prompt-tip">' }}
  <!-- {{ "> Знижки до 50% на всі послуги в честь свята Valborgsmässoafton" | markdownify | replace: '<blockquote>', '<blockquote class="prompt-warning">' }} -->
  
  <div class="category-grid">
    {% for service in site.services | sort_natural: 'order' %}
    <div class="category-card">
      <a href="{{ service.url }}" class="category-btn">{{ service.title }}</a>
    </div>
    {% endfor %}
  </div>
</div>