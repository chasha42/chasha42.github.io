<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>Чаша | Меню</title>
<style>
  :root {
    --bg: #f5f0eb;
    --bg2: #ffffff;
    --bg3: #ede8e2;
    --purple: #6b4f8a;
    --purple-light: #8b6aaa;
    --purple-dim: #e8e0f0;
    --gold: #a07830;
    --gold-light: #c49a40;
    --text: #1a1520;
    --text-muted: #6b5f7a;
    --text-dim: #9a8fa8;
    --border: rgba(107,79,138,0.15);
    --border-gold: rgba(160,120,48,0.2);
  }
  * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: Georgia, 'Times New Roman', serif;
    font-size: 15px;
    line-height: 1.6;
    max-width: 600px;
    margin: 0 auto;
  }

  /* HEADER */
  .header {
    background: var(--text);
    padding: 2.5rem 1.5rem 0;
    text-align: center;
  }
  .header-logo {
    font-size: 3rem;
    font-weight: 400;
    letter-spacing: 0.25em;
    color: #f5f0eb;
    line-height: 1;
    margin-bottom: 0.4rem;
  }
  .header-logo span { color: var(--gold-light); font-style: italic; }
  .header-sub {
    font-family: Arial, sans-serif;
    font-size: 0.6rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--text-dim);
    margin-bottom: 2rem;
  }
  .combo-hero {
    border-top: 1px solid rgba(160,120,48,0.3);
    padding: 1.5rem 1rem 1.8rem;
  }
  .combo-hero-tag {
    font-family: Arial, sans-serif;
    font-size: 0.55rem;
    letter-spacing: 0.28em;
    text-transform: uppercase;
    color: var(--gold-light);
    margin-bottom: 0.5rem;
    opacity: 0.8;
  }
  .combo-hero-title {
    font-size: 1.8rem;
    font-weight: 400;
    color: #f5f0eb;
    margin-bottom: 0.3rem;
    letter-spacing: 0.04em;
  }
  .combo-hero-items {
    font-family: Arial, sans-serif;
    font-size: 0.68rem;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: rgba(245,240,235,0.4);
    margin-bottom: 0.8rem;
  }
  .combo-hero-price {
    font-size: 2.5rem;
    color: var(--gold-light);
    line-height: 1;
  }

  /* NAV */
  nav {
    background: var(--text);
    border-top: 1px solid rgba(255,255,255,0.08);
    padding: 0 0.5rem;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    scrollbar-width: none;
    white-space: nowrap;
  }
  nav::-webkit-scrollbar { display: none; }
  nav a {
    display: inline-block;
    font-family: Arial, sans-serif;
    font-size: 0.58rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(245,240,235,0.5);
    text-decoration: none;
    padding: 0.75rem 0.7rem;
  }
  nav a:hover { color: var(--gold-light); }

  /* SECTIONS */
  .section {
    padding: 2rem 1.5rem 0.5rem;
    scroll-margin-top: 10px;
  }
  .section-title {
    font-size: 1.7rem;
    font-weight: 400;
    letter-spacing: 0.04em;
    color: var(--text);
    margin-bottom: 0.2rem;
  }
  .section-title span { color: var(--purple); font-style: italic; }
  .section-rule {
    width: 40px; height: 2px;
    background: var(--gold);
    margin-bottom: 1.2rem;
    opacity: 0.7;
  }

  /* SUB HEADING */
  .sub-heading {
    font-family: Arial, sans-serif;
    font-size: 0.58rem;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--purple-light);
    margin: 1.5rem 0 0.6rem;
    padding-bottom: 0.4rem;
    border-bottom: 1px solid var(--border);
  }

  /* DIVIDER */
  .divider {
    text-align: center;
    padding: 2rem 1.5rem 0;
  }
  .divider-inner {
    display: inline-flex;
    align-items: center;
    gap: 0.8rem;
    font-family: Arial, sans-serif;
    font-size: 0.55rem;
    letter-spacing: 0.22em;
    color: var(--text-dim);
  }
  .divider-inner::before, .divider-inner::after {
    content: '';
    width: 40px; height: 1px;
    background: var(--border);
    display: block;
  }

  /* MENU ROW */
  .menu-row {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    gap: 0.8rem;
    padding: 0.8rem 0;
    border-bottom: 1px solid rgba(107,79,138,0.08);
  }
  .menu-row:last-child { border-bottom: none; }
  .row-left { flex: 1; min-width: 0; }
  .row-name { font-size: 0.92rem; color: var(--text); }
  .row-note {
    font-family: Arial, sans-serif;
    font-size: 0.67rem;
    color: var(--text-muted);
    margin-top: 0.1rem;
  }
  .row-vol {
    font-family: Arial, sans-serif;
    font-size: 0.65rem;
    color: var(--text-dim);
    white-space: nowrap;
    margin-right: 0.5rem;
  }
  .row-price {
    font-size: 0.95rem;
    color: var(--gold);
    white-space: nowrap;
    min-width: 60px;
    text-align: right;
  }

  /* HOOKAH ROW */
  .hookah-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    padding: 1rem 0;
    border-bottom: 1px solid var(--border-gold);
  }
  .hookah-row:last-child { border-bottom: none; }
  .hookah-name { font-size: 1rem; color: var(--text); }
  .hookah-note {
    font-family: Arial, sans-serif;
    font-size: 0.67rem;
    color: var(--text-muted);
    margin-top: 0.15rem;
  }
  .hookah-price {
    font-size: 1.1rem;
    color: var(--gold);
    white-space: nowrap;
    min-width: 70px;
    text-align: right;
  }
  .badge {
    display: inline-block;
    font-family: Arial, sans-serif;
    font-size: 0.52rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    background: var(--purple-dim);
    color: var(--purple);
    padding: 2px 6px;
    border-radius: 2px;
    margin-left: 6px;
    vertical-align: middle;
  }

  /* COMBO */
  .combo-wrap {
    border: 1px solid var(--border-gold);
    border-radius: 3px;
    padding: 2rem 1.5rem;
    text-align: center;
    background: var(--bg2);
    margin: 1rem 0;
    position: relative;
  }
  .combo-wrap::before {
    content: '';
    position: absolute;
    top: -1px; left: 20%; right: 20%;
    height: 2px;
    background: var(--gold);
    opacity: 0.5;
  }
  .combo-tag {
    font-family: Arial, sans-serif;
    font-size: 0.55rem;
    letter-spacing: 0.28em;
    text-transform: uppercase;
    color: var(--gold);
    display: block;
    margin-bottom: 0.6rem;
  }
  .combo-title { font-size: 1.8rem; font-weight: 400; color: var(--text); margin-bottom: 0.4rem; }
  .combo-items {
    font-family: Arial, sans-serif;
    font-size: 0.7rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--text-muted);
    margin-bottom: 1.2rem;
  }
  .combo-items span { color: var(--text-dim); margin: 0 0.3rem; }
  .combo-price { font-size: 2.8rem; font-weight: 400; color: var(--gold); line-height: 1; }
  .combo-price sup { font-size: 1rem; vertical-align: super; opacity: 0.6; }

  /* FOOTER */
  footer {
    background: var(--text);
    text-align: center;
    padding: 2.5rem 1.5rem;
    margin-top: 3rem;
  }
  .footer-logo { font-size: 1.5rem; letter-spacing: 0.22em; color: rgba(245,240,235,0.5); margin-bottom: 0.3rem; }
  .footer-logo span { color: var(--gold-light); }
  .footer-handle {
    font-family: Arial, sans-serif;
    font-size: 0.6rem;
    letter-spacing: 0.18em;
    color: rgba(245,240,235,0.3);
    text-transform: uppercase;
  }
</style>
</head>
<body>

<div class="header">
  <div class="header-logo">ЧАША</div>
  <div class="header-sub">Кальянная &nbsp;·&nbsp; Бар</div>
  <div class="combo-hero">
    <div class="combo-hero-tag">Специальное предложение</div>
    <div class="combo-hero-title">Комбо обед</div>
    <div class="combo-hero-items">Кальян · Сэндвич · Напиток</div>
    <div class="combo-hero-price">1 600 ₽</div>
  </div>
</div>

<nav>
  <a href="#kalyan">Кальян</a>
  <a href="#bar">Бар</a>
  <a href="#kuhnya">Кухня</a>
  <a href="#chai">Чаи</a>
  <a href="#napitki">Напитки</a>
  <a href="#kofe">Кофе</a>
  <a href="#deserty">Десерты</a>
</nav>

<!-- КАЛЬЯН -->
<div class="divider"><div class="divider-inner">КАЛЬЯН</div></div>
<section class="section" id="kalyan">
  <h2 class="section-title">Кальян</h2>
  <div class="section-rule"></div>
  <div class="hookah-row">
    <div>
      <div class="hookah-name">Express <span class="badge">ПН–ПТ до 18:00</span></div>
      <div class="hookah-note">Чёрный/зелёный чай и орешки · 40–60 мин</div>
    </div>
    <div class="hookah-price">1 000 ₽</div>
  </div>
  <div class="hookah-row">
    <div>
      <div class="hookah-name">На фруктовой чаше</div>
      <div class="hookah-note">Грейпфрут, апельсин, гранат</div>
    </div>
    <div class="hookah-price">1 800 ₽</div>
  </div>
  <div class="hookah-row">
    <div><div class="hookah-name">Классический</div></div>
    <div class="hookah-price">1 400 ₽</div>
  </div>
  <div class="hookah-row">
    <div><div class="hookah-name">На сигарном листе</div></div>
    <div class="hookah-price">1 700 ₽</div>
  </div>
</section>

<!-- БАР -->
<div class="divider"><div class="divider-inner">МЕНЮ БАРА</div></div>
<section class="section" id="bar">
  <h2 class="section-title">Бар</h2>
  <div class="section-rule"></div>

  <div class="sub-heading">КОКТЕЙЛИ</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Пина Колада</div><div class="row-note">Ром, ананасовый сок, сливки, кокосовый сироп</div></div>
    <div class="row-vol">310 мл</div><div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Виски Кола</div><div class="row-note">Виски, кола, лимон</div></div>
    <div class="row-vol">200 мл</div><div class="row-price">400 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Чаша</div><div class="row-note">Джин, сок ананас, лимонный сок, сироп кокос, ликёр блю кюрасао, спрайт</div></div>
    <div class="row-vol">310 мл</div><div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Ром Кола</div><div class="row-note">Ром, кола, лимон</div></div>
    <div class="row-vol">200 мл</div><div class="row-price">400 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Белый Русский</div><div class="row-note">Водка, сливки, ликёр кофе</div></div>
    <div class="row-vol">100 мл</div><div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Джин Тоник</div><div class="row-note">Джин, тоник, лимон</div></div>
    <div class="row-vol">200 мл</div><div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Малиновая Лада</div><div class="row-note">Джин, сироп малина, сироп гренадин, трипел сек, сок лимона, спрайт</div></div>
    <div class="row-vol">200 мл</div><div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Лонг Айленд</div><div class="row-note">Кола, водка, ром, джин, текила, трипел сек, сок лимона, сахарный сироп</div></div>
    <div class="row-vol">200 мл</div><div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Апероль Шприц</div><div class="row-note">Аперитив, игристое хаус, газ вода</div></div>
    <div class="row-vol">270 мл</div><div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Негрони</div><div class="row-note">Кампари, джин, фиеро</div></div>
    <div class="row-vol">90 мл</div><div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Фиеро Тоник</div><div class="row-note">Фиеро, тоник</div></div>
    <div class="row-vol">220 мл</div><div class="row-price">550 ₽</div>
  </div>

  <div class="sub-heading">АВТОРСКИЕ КОКТЕЙЛИ · 650 ₽</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Birkin</div><div class="row-note">Ром, сироп груша, сироп лаванда, спрайт</div></div>
    <div class="row-vol">250 мл</div><div class="row-price">650 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Банановый Трайфл</div><div class="row-note">Белый ром, ликёр кофе, сливки, сироп банан</div></div>
    <div class="row-vol">200 мл</div><div class="row-price">650 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Гламур</div><div class="row-note">Водка, сироп клубника, сливки</div></div>
    <div class="row-vol">200 мл</div><div class="row-price">650 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Райская Бестия</div><div class="row-note">Водка, текила, белый ром, энергетик, сироп дыня</div></div>
    <div class="row-vol">300 мл</div><div class="row-price">650 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Asphalt 8</div><div class="row-note">Кола, виски, вишня</div></div>
    <div class="row-vol">300 мл</div><div class="row-price">650 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">The Best</div><div class="row-note">Текила, сок апельсин, белок, сироп грейпфрут</div></div>
    <div class="row-vol">200 мл</div><div class="row-price">650 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Биллини</div><div class="row-note">Просекко, пюре манго, белок</div></div>
    <div class="row-vol">200 мл</div><div class="row-price">650 ₽</div>
  </div>

  <div class="sub-heading">ШОТЫ ФРУКТОВЫЕ · x1 = 150 ₽</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Дыня / Вишня / Ананас / Апельсин</div></div>
    <div class="row-vol">6 шт / 12 шт</div>
    <div class="row-price">700 / 1200 ₽</div>
  </div>

  <div class="sub-heading">ШОТЫ КРЕПКИЕ</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Водка</div></div>
    <div class="row-vol">70 / 500 мл</div><div class="row-price">250 / 3500 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Текила</div></div>
    <div class="row-vol">70 / 500 мл</div><div class="row-price">250 / 2500 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Виски</div></div>
    <div class="row-vol">70 / 500 мл</div><div class="row-price">250 / 3500 ₽</div>
  </div>

  <div class="sub-heading">НАСТОЙКИ</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Лимончелло / Банановая / Малиновая</div></div>
    <div class="row-vol">50 / 500 мл</div><div class="row-price">150 / 1500 ₽</div>
  </div>

  <div class="sub-heading">ПИВО · 500 МЛ</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">В ассортименте</div></div>
    <div class="row-price">300 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Корона</div></div>
    <div class="row-price">400 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Гиннесс</div></div>
    <div class="row-price">600 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Сидр</div></div>
    <div class="row-price">400 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Соджу</div></div>
    <div class="row-price">400 ₽</div>
  </div>

  <div class="sub-heading">ВИНО · 200 МЛ</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Белое / Красное</div><div class="row-note">Сухое / Полусладкое</div></div>
    <div class="row-price">350 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Игристое белое / красное</div><div class="row-note">Сухое / Полусладкое</div></div>
    <div class="row-price">350 ₽</div>
  </div>
</section>

<!-- КУХНЯ -->
<div class="divider"><div class="divider-inner">КУХНЯ</div></div>
<section class="section" id="kuhnya">
  <h2 class="section-title">Еда</h2>
  <div class="section-rule"></div>

  <div class="sub-heading">ПАСТА</div>
  <div class="menu-row">
    <div class="row-left">
      <div class="row-name">Фетучини с креветками</div>
      <div class="row-note">Фетучини, сливочный соус, твёрдый сыр, креветки</div>
    </div>
    <div class="row-vol">300 гр</div>
    <div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left">
      <div class="row-name">Карбонара</div>
      <div class="row-note">Фетучини, сливочный соус, твёрдый сыр, бекон</div>
    </div>
    <div class="row-vol">320 гр</div>
    <div class="row-price">550 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left">
      <div class="row-name">Паста с куриной грудкой</div>
      <div class="row-note">Фетучини, сливочный соус, твёрдый сыр, куриная грудка</div>
    </div>
    <div class="row-vol">310 гр</div>
    <div class="row-price">550 ₽</div>
  </div>

  <div class="sub-heading">САЛАТЫ</div>
  <div class="menu-row">
    <div class="row-left">
      <div class="row-name">Греческий</div>
      <div class="row-note">Оливки, маслины, соус песто, салат айсберг, огурцы, помидоры черри</div>
    </div>
    <div class="row-vol">250 гр</div>
    <div class="row-price">450 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left">
      <div class="row-name">Буррата с овощами</div>
      <div class="row-note">Сыр буррата, соус песто, запечёный перец на гриле, томаты</div>
    </div>
    <div class="row-vol">270 гр</div>
    <div class="row-price">600 ₽</div>
  </div>

  <div class="menu-row">
    <div class="row-left">
      <div class="row-name">Цезарь с курицей / креветкой</div>
      <div class="row-note">Салат айсберг, помидоры черри, соус цезарь, гренки, курица/креветки</div>
    </div>
    <div class="row-vol">225 гр</div>
    <div class="row-price">450 ₽</div>
  </div>

  <div class="sub-heading">СЭНДВИЧИ</div>
  <div class="menu-row">
    <div class="row-left">
      <div class="row-name">С ветчиной + фри</div>
      <div class="row-note">Хлеб для тостов, соус 1000 островов, огурец, помидор, сыр, ветчина</div>
    </div>
    <div class="row-price">500 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left">
      <div class="row-name">С курицей + фри</div>
      <div class="row-note">Хлеб для тостов, соус 1000 островов, огурец, помидор, сыр, куриное филе</div>
    </div>
    <div class="row-price">500 ₽</div>
  </div>
</section>

<!-- ЧАИ -->
<div class="divider"><div class="divider-inner">ЧАЙНАЯ КАРТА</div></div>
<section class="section" id="chai">
  <h2 class="section-title">Авторские Чаи</h2>
  <div class="section-rule"></div>

  <div class="sub-heading">АВТОРСКИЕ ЧАИ · 1000 МЛ · 700 ₽</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Пуэр на вишнёвом соке</div></div>
    <div class="row-price">700 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Пуэр на вишнёво-гранатовом соке</div></div>
    <div class="row-price">700 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Облепиховый</div></div>
    <div class="row-price">700 ₽</div>
  </div>

  <div class="sub-heading">КЛАССИЧЕСКИЕ ЧАИ · 1000 МЛ · 500 ₽</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Зелёный</div></div>
    <div class="row-price">500 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Чёрный</div></div>
    <div class="row-price">500 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Турецкое утро</div></div>
    <div class="row-price">500 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Имбирное утро</div></div>
    <div class="row-price">500 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Мулен Руж</div></div>
    <div class="row-price">500 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">1001 ночь</div></div>
    <div class="row-price">500 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Молочный улун</div></div>
    <div class="row-price">500 ₽</div>
  </div>
  <div style="display:flex;justify-content:space-between;align-items:center;padding:0.8rem 0;border-top:1px solid var(--border);margin-top:0.3rem;">
    <span style="font-family:Arial,sans-serif;font-size:0.7rem;color:var(--text-muted);text-transform:uppercase;letter-spacing:0.08em;">Добавки: мята / лимон / мёд / сироп</span>
    <span style="font-size:0.95rem;color:var(--gold);">+ 50 ₽</span>
  </div>
</section>

<!-- НАПИТКИ -->
<div class="divider"><div class="divider-inner">БЕЗАЛКОГОЛЬНЫЕ НАПИТКИ</div></div>
<section class="section" id="napitki">
  <h2 class="section-title">Напитки</h2>
  <div class="section-rule"></div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Авторский лимонад</div><div class="row-note">Освежающий напиток на основе пюре из натуральных фруктов</div></div>
    <div class="row-vol">500мл / 1500 мл</div>
    <div class="row-price">400 ₽ / 900 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Классический лимонад</div><div class="row-note">Освежающий напиток на основе фруктового / ягодного сиропа</div></div>
    <div class="row-vol">500мл / 1500 мл</div>
    <div class="row-price">270 ₽ / 700 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Спрайт / Фанта / Кола</div></div>
    <div class="row-vol">300 мл / 500 мл</div>
    <div class="row-price">200 ₽ / 250 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Сок в ассортименте</div></div>
    <div class="row-vol">300 мл</div>
    <div class="row-price">200 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Энергетик</div></div>
    <div class="row-vol">300 мл / 500 мл</div>
    <div class="row-price">200 ₽ / 350 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Лимонад Натахтари</div></div>
    <div class="row-vol">500 мл</div>
    <div class="row-price">250 ₽</div>
  </div>

  <div class="sub-heading">ВОДА</div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Газированная</div></div>
    <div class="row-vol">300 мл</div>
    <div class="row-price">100 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Негазированная</div></div>
    <div class="row-vol">500 мл</div>
    <div class="row-price">200 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Borjomi</div></div>
    <div class="row-vol">500 мл</div>
    <div class="row-price">300 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Jermuk</div></div>
    <div class="row-vol">500 мл</div>
    <div class="row-price">300 ₽</div>
  </div>
</section>

<!-- КОФЕ -->
<div class="divider"><div class="divider-inner">ГОРЯЧИЕ НАПИТКИ</div></div>
<section class="section" id="kofe">
  <h2 class="section-title">Кофе</h2>
  <div class="section-rule"></div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">На турке</div><div class="row-note">100 мл</div></div>
    <div class="row-price">200 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Латте</div><div class="row-note">350 мл</div></div>
    <div class="row-price">300 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Раф</div><div class="row-note">350 мл</div></div>
    <div class="row-price">350 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Капучино</div><div class="row-note">350 мл</div></div>
    <div class="row-price">300 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Бамбл-кофе</div><div class="row-note">400 мл</div><div class="row-note">На апельсиновом / вишневом соке</div></div>
    <div class="row-price">370 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Айс-Латте</div><div class="row-note">350 мл</div></div>
    <div class="row-price">350 ₽</div>
  </div>

</section>

<!-- ДЕСЕРТЫ -->
<div class="divider"><div class="divider-inner">ДЕСЕРТЫ И ЗАКУСКИ</div></div>
<section class="section" id="deserty">
  <h2 class="section-title">Десерты</h2>
  <div class="section-rule"></div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Чизкейк</div><div class="row-note">Классический / шоколадный</div></div>
    <div class="row-vol">1 шт</div>
    <div class="row-price">350 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Батончики</div><div class="row-note">Snickers · Bounty · Mars</div></div>
    <div class="row-vol">1 шт</div>
    <div class="row-price">150 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Шоколад</div></div>
    <div class="row-vol">1 шт</div>
    <div class="row-price">250 ₽</div>
  </div>
  <div class="menu-row">
    <div class="row-left"><div class="row-name">Микс фруктов и орехов</div></div>
    <div class="row-vol">200 гр</div>
    <div class="row-price">350 ₽</div>
  </div>

  <h2 class="section-title" style="margin-top:2rem;">Закуски</h2>
  <div class="section-rule"></div>
  <div class="hookah-row">
    <div>
      <div class="hookah-name">Картофель-фри / по деревенски</div>
      <div class="row-vol">250 гр</div>
    </div>
    <div class="hookah-price">300 ₽</div>
  </div>
  <div class="hookah-row">
    <div>
      <div class="hookah-name">Наггетсы</div>
      <div class="row-vol">8 шт</div>
    </div>
    <div class="hookah-price">400 ₽</div>
  </div>
  <div class="hookah-row">
    <div>
      <div class="hookah-name">Стрипсы</div>
      <div class="row-vol">4 шт</div>
    </div>
    <div class="hookah-price">350 ₽</div>
  </div>
    <div class="hookah-row">
    <div>
      <div class="hookah-name">Арахис</div>
      <div class="row-vol">150 гр</div>
    </div>
    <div class="hookah-price">250 ₽</div>
  </div>
  <div class="hookah-row">
    <div>
      <div class="hookah-name">Фисташки</div>
      <div class="row-vol">300 гр</div>
    </div>
    <div class="hookah-price">500 ₽</div>
  </div>

  <div class="hookah-row">
    <div>
      <div class="hookah-name">Пивная тарелка</div>
      <div class="hookah-note">Арахис, фисташки, колбаски, соус, креветки/наггетсы</div>
    </div>
    <div class="hookah-price">900 ₽</div>
  </div>
  <div class="hookah-row">
    <div>
      <div class="hookah-name">Пивная горячая тарелка</div>
      <div class="hookah-note">Картофель фри/по-деревенски, наггетсы, стрипсы, луковые кольца/кольца кальмара, соус</div>
    </div>
    <div class="hookah-price">1 400 ₽</div>
  </div>
  <div class="hookah-row">
    <div>
      <div class="hookah-name">Соус</div>
      <div class="hookah-note">Кисло-сладкий · Сырный · Кетчуп · 1000 островов</div>
    </div>
    <div class="hookah-price">50 ₽</div>
  </div>
</section>

<footer>
  <div class="footer-logo">ЧАША</div>
  <p class="footer-handle">@chasha_kem</p>
</footer>

</body>
</html>
