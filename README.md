<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lista de Presentes — Itany & Camilo</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --ivory: #FAF7F2;
    --champagne: #E8DFD0;
    --gold: #C9A96E;
    --gold-light: #E8C98A;
    --deep: #2C2418;
    --text: #3D3023;
    --muted: #8A7A65;
    --card-bg: #FFFFFF;
    --border: #E0D5C5;
    --green-ok: #4A7C59;
    --green-bg: #EBF5EE;
    --blue: #4A6B8A;
    --blue-bg: #EBF2F9;
    --pink: #C06B8A;
    --pink-bg: #F9EBEF;
    --shadow: 0 4px 24px rgba(44,36,24,0.08);
    --radius: 16px;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Jost', sans-serif;
    background: var(--ivory);
    color: var(--text);
    min-height: 100vh;
  }

  /* HERO */
  .hero {
    background: linear-gradient(160deg, #2C2418 0%, #4A3820 50%, #6B4F35 100%);
    color: white;
    text-align: center;
    padding: 64px 24px 56px;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23C9A96E' fill-opacity='0.07'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    opacity: 1;
  }
  .hero-rings {
    font-size: 2rem;
    margin-bottom: 12px;
    opacity: 0.9;
  }
  .hero h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2.4rem, 6vw, 4rem);
    font-weight: 300;
    letter-spacing: 2px;
    line-height: 1.1;
  }
  .hero h1 em {
    font-style: italic;
    color: var(--gold-light);
  }
  .hero-date {
    font-family: 'Jost', sans-serif;
    font-size: 0.85rem;
    font-weight: 300;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--champagne);
    margin-top: 12px;
    opacity: 0.85;
  }
  .hero-divider {
    width: 60px;
    height: 1px;
    background: var(--gold);
    margin: 20px auto;
    opacity: 0.7;
  }
  .hero-subtitle {
    font-size: 0.9rem;
    color: var(--champagne);
    opacity: 0.8;
    max-width: 480px;
    margin: 0 auto;
    line-height: 1.7;
  }

  /* STATS BAR */
  .stats-bar {
    background: var(--deep);
    display: flex;
    justify-content: center;
    gap: 0;
    flex-wrap: wrap;
  }
  .stat-item {
    padding: 16px 32px;
    text-align: center;
    border-right: 1px solid rgba(201,169,110,0.2);
  }
  .stat-item:last-child { border-right: none; }
  .stat-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.8rem;
    color: var(--gold-light);
    display: block;
    font-weight: 400;
  }
  .stat-label {
    font-size: 0.68rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--champagne);
    opacity: 0.6;
  }

  /* CONTROLS */
  .controls {
    max-width: 1200px;
    margin: 0 auto;
    padding: 32px 24px 8px;
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    align-items: center;
  }
  .controls input {
    flex: 1;
    min-width: 200px;
    padding: 10px 16px;
    border: 1.5px solid var(--border);
    border-radius: 8px;
    font-family: 'Jost', sans-serif;
    font-size: 0.9rem;
    background: white;
    color: var(--text);
    outline: none;
    transition: border-color .2s;
  }
  .controls input:focus { border-color: var(--gold); }
  .filter-btn {
    padding: 10px 18px;
    border: 1.5px solid var(--border);
    border-radius: 8px;
    background: white;
    font-family: 'Jost', sans-serif;
    font-size: 0.82rem;
    font-weight: 500;
    color: var(--muted);
    cursor: pointer;
    transition: all .2s;
    white-space: nowrap;
  }
  .filter-btn:hover { border-color: var(--gold); color: var(--gold); }
  .filter-btn.active { background: var(--deep); color: var(--gold-light); border-color: var(--deep); }

  /* SECTION */
  .section {
    max-width: 1200px;
    margin: 0 auto;
    padding: 24px 24px 8px;
  }
  .section-header {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 20px;
    padding-bottom: 14px;
    border-bottom: 1px solid var(--border);
  }
  .section-icon {
    width: 40px; height: 40px;
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.2rem;
    flex-shrink: 0;
  }
  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.6rem;
    font-weight: 400;
    color: var(--deep);
  }
  .section-count {
    margin-left: auto;
    font-size: 0.75rem;
    color: var(--muted);
    background: var(--champagne);
    padding: 3px 10px;
    border-radius: 20px;
  }

  /* GRID */
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 20px;
    margin-bottom: 40px;
  }

  /* CARD */
  .card {
    background: var(--card-bg);
    border-radius: var(--radius);
    border: 1.5px solid var(--border);
    overflow: hidden;
    box-shadow: var(--shadow);
    transition: transform .2s, box-shadow .2s;
    display: flex;
    flex-direction: column;
    position: relative;
  }
  .card:hover { transform: translateY(-3px); box-shadow: 0 8px 32px rgba(44,36,24,0.13); }
  .card.purchased { opacity: 0.65; }
  .card.purchased::after {
    content: '✓ Comprado';
    position: absolute;
    top: 12px; right: 12px;
    background: var(--green-ok);
    color: white;
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.5px;
    padding: 4px 10px;
    border-radius: 20px;
    z-index: 2;
  }

  .card-img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    background: var(--champagne);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3rem;
    color: var(--muted);
    flex-shrink: 0;
    position: relative;
    overflow: hidden;
  }
  .card-img img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: opacity .3s;
  }
  .card-img .placeholder {
    position: absolute; inset: 0;
    display: flex; align-items: center; justify-content: center;
    font-size: 3rem;
    background: var(--champagne);
  }
  .photo-upload-btn {
    position: absolute;
    bottom: 8px; right: 8px;
    background: rgba(44,36,24,0.85);
    color: var(--gold-light);
    border: none;
    border-radius: 8px;
    padding: 6px 10px;
    font-size: 0.7rem;
    font-family: 'Jost', sans-serif;
    font-weight: 500;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 4px;
    z-index: 3;
    transition: background .2s;
  }
  .photo-upload-btn:hover { background: var(--deep); }

  .card-body {
    padding: 16px;
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  .card-name {
    font-family: 'Jost', sans-serif;
    font-size: 0.88rem;
    font-weight: 600;
    color: var(--deep);
    line-height: 1.35;
  }
  .card-price {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.4rem;
    color: var(--gold);
    font-weight: 600;
  }
  .card-price.no-price {
    font-size: 0.85rem;
    font-family: 'Jost', sans-serif;
    color: var(--muted);
    font-style: italic;
    font-weight: 300;
  }
  .card-options {
    font-size: 0.78rem;
    color: var(--muted);
    line-height: 1.4;
  }

  .card-footer {
    padding: 12px 16px;
    border-top: 1px solid var(--border);
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }
  .btn-link {
    flex: 1;
    text-align: center;
    padding: 8px 12px;
    background: var(--deep);
    color: var(--gold-light);
    text-decoration: none;
    border-radius: 8px;
    font-size: 0.78rem;
    font-weight: 500;
    letter-spacing: 0.3px;
    transition: background .2s;
    white-space: nowrap;
  }
  .btn-link:hover { background: #4A3820; }
  .btn-link.alt {
    background: transparent;
    border: 1.5px solid var(--border);
    color: var(--muted);
  }
  .btn-link.alt:hover { border-color: var(--gold); color: var(--gold); }

  .card-actions {
    padding: 0 16px 14px;
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }
  .badge {
    padding: 4px 10px;
    border-radius: 20px;
    font-size: 0.72rem;
    font-weight: 500;
    cursor: pointer;
    border: none;
    font-family: 'Jost', sans-serif;
    transition: all .15s;
  }
  .badge-split { background: var(--blue-bg); color: var(--blue); }
  .badge-split:hover { background: var(--blue); color: white; }
  .badge-bought { background: var(--green-bg); color: var(--green-ok); }
  .badge-bought:hover { background: var(--green-ok); color: white; }
  .badge-active-split { background: var(--pink-bg); color: var(--pink); }

  /* NAMES LIST for group purchases */
  .names-list {
    display: none;
    padding: 0 16px 12px;
    flex-direction: column;
    gap: 6px;
  }
  .names-list.open { display: flex; }
  .names-list label { font-size: 0.78rem; color: var(--muted); }
  .names-list input {
    padding: 6px 10px;
    border: 1px solid var(--border);
    border-radius: 6px;
    font-family: 'Jost', sans-serif;
    font-size: 0.82rem;
    color: var(--text);
    outline: none;
  }
  .names-list input:focus { border-color: var(--gold); }
  .names-output {
    font-size: 0.75rem;
    color: var(--pink);
    min-height: 0;
    line-height: 1.5;
    font-style: italic;
  }

  /* ADD NEW ITEM */
  .add-section {
    max-width: 1200px;
    margin: 0 auto 48px;
    padding: 0 24px;
  }
  .add-card {
    background: white;
    border: 1.5px dashed var(--gold);
    border-radius: var(--radius);
    padding: 28px;
  }
  .add-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.4rem;
    color: var(--deep);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .add-form {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }
  @media(max-width: 600px) { .add-form { grid-template-columns: 1fr; } }
  .add-form input, .add-form select, .add-form textarea {
    padding: 10px 14px;
    border: 1.5px solid var(--border);
    border-radius: 8px;
    font-family: 'Jost', sans-serif;
    font-size: 0.88rem;
    color: var(--text);
    outline: none;
    transition: border-color .2s;
    background: var(--ivory);
  }
  .add-form input:focus, .add-form select:focus { border-color: var(--gold); background: white; }
  .add-form .full { grid-column: 1 / -1; }
  .add-form textarea { resize: vertical; min-height: 60px; }
  .btn-add {
    grid-column: 1 / -1;
    padding: 12px;
    background: var(--deep);
    color: var(--gold-light);
    border: none;
    border-radius: 8px;
    font-family: 'Jost', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    cursor: pointer;
    letter-spacing: 0.5px;
    transition: background .2s;
  }
  .btn-add:hover { background: #4A3820; }

  /* FOOTER */
  footer {
    background: var(--deep);
    color: var(--champagne);
    text-align: center;
    padding: 32px 24px;
    margin-top: 32px;
  }
  footer p { font-size: 0.82rem; opacity: 0.6; line-height: 1.8; }
  footer strong { color: var(--gold-light); font-weight: 400; }

  /* INFO BANNER */
  .info-banner {
    background: linear-gradient(180deg, #f5efe6 0%, #faf7f2 100%);
    border-bottom: 1px solid var(--border);
    padding: 32px 24px;
  }
  .info-banner-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 24px;
  }
  .info-block {
    display: flex;
    gap: 16px;
    align-items: flex-start;
    background: white;
    border-radius: 14px;
    padding: 20px 22px;
    border: 1.5px solid var(--border);
    box-shadow: 0 2px 12px rgba(44,36,24,0.05);
  }
  .info-icon {
    font-size: 1.6rem;
    flex-shrink: 0;
    margin-top: 2px;
  }
  .info-text {
    flex: 1;
  }
  .info-text strong {
    display: block;
    font-size: 1rem;
    font-weight: 600;
    color: var(--deep);
    margin-bottom: 6px;
  }
  .info-text p {
    font-size: 0.86rem;
    color: var(--muted);
    line-height: 1.65;
  }
  .info-text em {
    color: var(--gold);
    font-style: normal;
    font-weight: 600;
  }
  .store-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin: 10px 0;
  }
  .store-badge {
    background: var(--champagne);
    color: var(--deep);
    font-size: 0.75rem;
    font-weight: 500;
    padding: 4px 12px;
    border-radius: 20px;
    border: 1px solid var(--border);
  }

  /* PIX CARDS */
  .pix-cards {
    display: flex;
    gap: 14px;
    margin-top: 14px;
    flex-wrap: wrap;
  }
  .pix-card {
    flex: 1;
    min-width: 200px;
    background: linear-gradient(135deg, #2C2418 0%, #4A3820 100%);
    border-radius: 14px;
    padding: 18px 20px;
    color: white;
    position: relative;
    overflow: hidden;
  }
  .pix-card::before {
    content: 'PIX';
    position: absolute;
    top: 12px; right: 16px;
    font-size: 0.65rem;
    letter-spacing: 3px;
    color: var(--gold-light);
    opacity: 0.7;
    font-weight: 700;
  }
  .pix-label {
    font-size: 0.72rem;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--gold-light);
    opacity: 0.8;
    margin-bottom: 6px;
  }
  .pix-key {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.3rem;
    font-weight: 400;
    color: white;
    margin-bottom: 4px;
    letter-spacing: 0.5px;
  }
  .pix-name {
    font-size: 0.8rem;
    color: var(--champagne);
    opacity: 0.85;
    margin-bottom: 2px;
  }
  .pix-type {
    font-size: 0.7rem;
    color: var(--champagne);
    opacity: 0.55;
    margin-bottom: 14px;
  }
  .pix-copy-btn {
    background: rgba(201,169,110,0.2);
    border: 1px solid rgba(201,169,110,0.4);
    color: var(--gold-light);
    border-radius: 8px;
    padding: 7px 14px;
    font-size: 0.78rem;
    font-family: 'Jost', sans-serif;
    font-weight: 500;
    cursor: pointer;
    transition: all .2s;
    width: 100%;
  }
  .pix-copy-btn:hover { background: rgba(201,169,110,0.35); }
  .pix-copy-btn.copied { background: var(--green-ok); border-color: var(--green-ok); color: white; }

  /* HIDDEN */
  .hidden { display: none !important; }
  input[type="file"] { display: none; }
</style>
</head>
<body>

<!-- HERO -->
<header class="hero">
  <div class="hero-rings">💍</div>
  <h1><em>Itany</em> & <em>Camilo</em></h1>
  <p class="hero-date">Lista de Presentes</p>
  <div class="hero-divider"></div>
  <p class="hero-subtitle">Cada presente aqui foi escolhido com carinho por nós. Você pode comprar sozinho ou se juntar a outros convidados para dar um presente maior. ♡</p>
</header>

<!-- INFO BANNER -->
<div class="info-banner">
  <div class="info-banner-inner">

    <div class="info-block info-tip">
      <div class="info-icon">💡</div>
      <div class="info-text">
        <strong>Os links são sugestões, não obrigação!</strong>
        <p>Os produtos listados aqui são referências do que gostaríamos de ganhar — o modelo, a cor e as especificações. Os links que colocamos são de onde encontramos por um bom preço, mas <em>fique à vontade para pesquisar em outras lojas!</em> Pode ser Magazine Luiza, Americanas, Mercado Livre, Amazon, Shopee ou qualquer outra. O que importa é o produto, não o site. 😊</p>
      </div>
    </div>

    <div class="info-block info-stores">
      <div class="info-icon">🛍️</div>
      <div class="info-text">
        <strong>Onde pesquisar o melhor preço?</strong>
        <div class="store-badges">
          <span class="store-badge">Mercado Livre</span>
          <span class="store-badge">Amazon</span>
          <span class="store-badge">Magazine Luiza</span>
          <span class="store-badge">Americanas</span>
          <span class="store-badge">Shopee</span>
          <span class="store-badge">Casas Bahia</span>
          <span class="store-badge">Fast Shop</span>
          <span class="store-badge">Lojas físicas</span>
        </div>
        <p>Use sites como <strong>Zoom</strong> ou <strong>Buscapé</strong> para comparar preços entre lojas em tempo real!</p>
      </div>
    </div>

    <div class="info-block info-pix">
      <div class="info-icon">💚</div>
      <div class="info-text">
        <strong>Prefere presentear via Pix?</strong>
        <p>Se preferir nos enviar o valor diretamente, fique à vontade! Assim compramos o item na hora e no melhor preço disponível. ♡</p>
        <div class="pix-cards">
          <div class="pix-card">
            <div class="pix-label">Pix do Camilo</div>
            <div class="pix-key">358.145.738-56</div>
            <div class="pix-name">Camilo Ribeiro Fagundes</div>
            <div class="pix-type">CPF</div>
            <button class="pix-copy-btn" onclick="copyPix('358.145.738-56', this)">📋 Copiar chave</button>
          </div>
          <div class="pix-card">
            <div class="pix-label">Pix da Itany</div>
            <div class="pix-key">(18) 99789-2050</div>
            <div class="pix-name">Itany Graziel Zanetti</div>
            <div class="pix-type">Celular</div>
            <button class="pix-copy-btn" onclick="copyPix('18997892050', this)">📋 Copiar chave</button>
          </div>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- STATS BAR -->
<div class="stats-bar">
  <div class="stat-item">
    <span class="stat-number" id="totalItems">0</span>
    <span class="stat-label">Total de Itens</span>
  </div>
  <div class="stat-item">
    <span class="stat-number" id="boughtItems">0</span>
    <span class="stat-label">Já Comprados</span>
  </div>
  <div class="stat-item">
    <span class="stat-number" id="availableItems">0</span>
    <span class="stat-label">Disponíveis</span>
  </div>
  <div class="stat-item">
    <span class="stat-number" id="splitItems">0</span>
    <span class="stat-label">Para Dividir</span>
  </div>
</div>

<!-- CONTROLS -->
<div class="controls">
  <input type="text" id="searchInput" placeholder="🔍 Buscar presente..." oninput="filterItems()">
  <button class="filter-btn active" onclick="filterCat('all', this)">Todos</button>
  <button class="filter-btn" onclick="filterCat('eletrodomesticos', this)">🏠 Eletrodomésticos</button>
  <button class="filter-btn" onclick="filterCat('eletronicos', this)">📱 Eletrônicos</button>
  <button class="filter-btn" onclick="filterCat('cozinha', this)">🍳 Cozinha</button>
  <button class="filter-btn" onclick="filterCat('moveis', this)">🛋️ Móveis & Decoração</button>
  <button class="filter-btn" onclick="filterCat('cama_banho', this)">🛏️ Cama & Banho</button>
  <button class="filter-btn" onclick="filterCat('organizacao', this)">🗄️ Organização</button>
  <button class="filter-btn" onclick="filterAvailable()">✨ Disponíveis</button>
</div>

<!-- ITEMS WILL BE RENDERED HERE -->
<div id="giftsContainer"></div>

<!-- ADD NEW ITEM -->
<div class="add-section">
  <div class="add-card">
    <h3 class="add-title">➕ Adicionar Novo Presente</h3>
    <div class="add-form">
      <input type="text" id="newName" placeholder="Nome do produto" />
      <input type="text" id="newPrice" placeholder="Preço (ex: 350,00)" />
      <input type="text" id="newLink" placeholder="Link para compra" />
      <input type="text" id="newImg" placeholder="URL da foto (opcional)" />
      <select id="newCat">
        <option value="eletrodomesticos">🏠 Eletrodomésticos</option>
        <option value="eletronicos">📱 Eletrônicos</option>
        <option value="cozinha">🍳 Cozinha</option>
        <option value="moveis">🛋️ Móveis & Decoração</option>
        <option value="cama_banho">🛏️ Cama & Banho</option>
        <option value="organizacao">🗄️ Organização</option>
      </select>
      <input type="text" id="newOptions" placeholder="Opções disponíveis (ex: 127V/220V)" />
      <textarea id="newNote" placeholder="Observações (opcional)" class="full"></textarea>
      <button class="btn-add" onclick="addNewItem()">✓ Adicionar à Lista</button>
    </div>
  </div>
</div>

<footer>
  <p>Feito com ♡ para o casamento de <strong>Itany & Camilo</strong><br>
  Para marcar um item como comprado, dividir o presente ou adicionar uma foto, use os botões em cada card.<br>
  <small>As informações são salvas automaticamente neste dispositivo.</small></p>
</footer>

<!-- Hidden file input used for manual photo upload -->
<input type="file" id="photoUploadInput" accept="image/*">

<script>
// ===================== PIX COPY =====================
function copyPix(key, btn) {
  navigator.clipboard.writeText(key).then(() => {
    btn.textContent = '✓ Copiado!';
    btn.classList.add('copied');
    setTimeout(() => {
      btn.textContent = '📋 Copiar chave';
      btn.classList.remove('copied');
    }, 2500);
  }).catch(() => {
    prompt('Copie a chave Pix:', key);
  });
}

// ===================== DATA =====================
let gifts = JSON.parse(localStorage.getItem('wedding_gifts_v2') || 'null') || [
  // ── COZINHA ──
  {
    id: 1, cat: 'cozinha', name: 'Manteigueira Francesa Brisa 250g — Ouro Cobalto (Ceraflame)',
    price: 'A consultar', note: 'Linha Ouro Cobalto · Ceraflame',
    img: '',
    links: [{ label: '🛒 Ceraflame', url: 'https://www.compreaqui.ceraflame.com.br/servir/manteigueira-francesa-brisa-250gr-01-ouro-cobalto' }],
    bought: false, splitOpen: false, names: []
  },
  // ── ELETRODOMÉSTICOS — LAVA-LOUÇAS ──
  {
    id: 2, cat: 'eletrodomesticos', name: 'Lava-Louças 10 Serviços (opção 1)',
    price: 'A consultar', note: 'Ver opções de voltagem no link',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2sPNyiu' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 3, cat: 'eletrodomesticos', name: 'Lava-Louças Brastemp BLF10B 10 Serviços Cor Inox',
    price: 'R$ 2.839,00', note: '127V',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2XxRUhR' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 4, cat: 'eletrodomesticos', name: 'Lava-Louças Electrolux 10 Serviços Inox — Lava & Seca 50min LS08E Display Digital',
    price: 'R$ 3.099,00', note: '220V',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1PasX3e' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 5, cat: 'eletrodomesticos', name: 'Lava-Louças Midea 14 Serviços Preta',
    price: 'R$ 2.882,00', note: 'Cor preta',
    img: '',
    links: [{ label: '🛒 Magazine Luiza', url: 'https://www.magazineluiza.com.br/lava-loucas-14-servicos-preta-midea/p/eh0aa5add5/ed/l14s/?seller_id=mideacarrier' }],
    bought: false, splitOpen: false, names: []
  },
  // ── ELETRÔNICOS — ROBÔ ASPIRADOR ──
  {
    id: 6, cat: 'eletronicos', name: 'Robô Aspirador Xiaomi S20',
    price: 'A consultar', note: 'Modelo Xiaomi S20',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1zNzqp9' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 7, cat: 'eletronicos', name: 'Robô Aspirador Xiaomi',
    price: 'A consultar', note: 'Disponível em 2 lojas — escolha a melhor opção',
    img: '',
    links: [
      { label: '🛒 Mercado Livre', url: 'https://meli.la/2bk8hJ3' },
      { label: '🛒 Amazon', url: 'https://amzn.to/3NrW5Oa' }
    ],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 8, cat: 'eletronicos', name: 'Robô Aspirador Xiaomi Robot Vacuum X20 Pro',
    price: 'A consultar', note: 'Modelo X20 Pro',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1Bm5QWd' }],
    bought: false, splitOpen: false, names: []
  },
  // ── SOFÁ ──
  {
    id: 9, cat: 'moveis', name: 'Sofá para Sala',
    price: 'A definir em loja', note: 'Iremos em lojas físicas para escolher o melhor modelo pessoalmente',
    img: '',
    links: [],
    bought: false, splitOpen: false, names: []
  },
  // ── PAINEL TV ──
  {
    id: 10, cat: 'moveis', name: 'Painel TV até 60" Ripado com Nichos — Bento Freijó Off White (DJ Móveis)',
    price: 'A consultar', note: 'DJ Móveis · Off White',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1rY6MGg' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 11, cat: 'moveis', name: 'Painel Suspenso TV 60" — Bento Freijó Off White (DJ Móveis)',
    price: 'A consultar', note: 'DJ Móveis · Suspenso',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2zoZDBM' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 12, cat: 'moveis', name: 'Painel TV até 60" Ripado com Nichos — Bento Freijó Cinza (DJ Móveis)',
    price: 'A consultar', note: 'DJ Móveis · Cinza',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1rDkJaZ' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 13, cat: 'moveis', name: 'Painel de TV Roma com Nicho Suspenso — Moderno',
    price: 'A consultar', note: 'Design moderno suspenso',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/21cUVnA' }],
    bought: false, splitOpen: false, names: []
  },
  // ── KIT FAQUEIRO / FACAS ──
  {
    id: 14, cat: 'cozinha', name: 'Jogo de Facas Plenus 9 Peças — Aço Inox e Cabos Polipropileno Preto (Tramontina)',
    price: 'A consultar', note: 'Tramontina · 9 peças',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1un9aFZ' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 15, cat: 'cozinha', name: 'Jogo de Facas Laguiole Inox com Cepo de Madeira 6 Peças Luxo Preto (La Tour)',
    price: 'A consultar', note: 'La Tour · Cepo de madeira · 6 peças',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1n22E2c' }],
    bought: false, splitOpen: false, names: []
  },
  // ── BATEDEIRA ──
  {
    id: 16, cat: 'eletrodomesticos', name: 'Batedeira Arno com Pedestal — Movimento Planetário Preta',
    price: 'A consultar', note: 'Movimento planetário · Cor preta',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2zcsndo' }],
    bought: false, splitOpen: false, names: []
  },
  // ── MIXER ──
  {
    id: 17, cat: 'eletrodomesticos', name: 'Mixer Turbo 3 em 1 — 1000W, 5 Velocidades, Preto',
    price: 'A consultar', note: '3 em 1 · 1000W · 5 velocidades',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/22aA9qB' }],
    bought: false, splitOpen: false, names: []
  },
  // ── LIQUIDIFICADOR ──
  {
    id: 18, cat: 'eletrodomesticos', name: 'Liquidificador Arno Power Max 1000 — 3.1L, 2200W, 15 Velocidades, Preto',
    price: 'A consultar', note: '3.1L · 2200W · 15 velocidades',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1CRVumf' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 19, cat: 'eletrodomesticos', name: 'Liquidificador WAP WB2000 — 2L, 1000W, Copo de Vidro, Velocidade Variável',
    price: 'A consultar', note: '2L · 220V · copo de vidro',
    img: '',
    links: [{ label: '🛒 Amazon', url: 'https://www.amazon.com.br/WAP-Liquidificador-WB2000-Velocidade-Vari%C3%A1vel/dp/B0DCP6WMQH/' }],
    bought: false, splitOpen: false, names: []
  },
  // ── VENTILADOR ──
  {
    id: 20, cat: 'eletrodomesticos', name: 'Ventilador de Chão',
    price: 'A consultar', note: 'Ver modelo no link',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1kXCCzL' }],
    bought: false, splitOpen: false, names: []
  },
  // ── FRIGIDEIRAS ──
  {
    id: 21, cat: 'cozinha', name: 'Frigideira Elétrica Philco Redstone Definitive 1.7L — Cinza/Vermelho',
    price: 'A consultar', note: 'PPH240AFR · 1.7L',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2uSvYEn' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 22, cat: 'cozinha', name: 'Kit Frigideiras RedSilver — Kit 1 (2 itens)',
    price: 'A consultar', note: 'Kit completo RedSilver',
    img: '',
    links: [{ label: '🛒 RedSilver', url: 'https://redsilverpanelas.com/ecommerce/kit/kit-1' }],
    bought: false, splitOpen: false, names: []
  },
  // ── CHALEIRA ──
  {
    id: 23, cat: 'eletrodomesticos', name: 'Chaleira Elétrica',
    price: 'A consultar', note: 'Ver modelo no link',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2D2r2Es' }],
    bought: false, splitOpen: false, names: []
  },
  // ── FAQUEIRO/TALHERES ──
  {
    id: 24, cat: 'cozinha', name: 'Faqueiro Brinox Lyon 36 Peças — Aço Inox',
    price: 'A consultar', note: '36 peças · Aço inox',
    img: '',
    links: [{ label: '🛒 Amazon', url: 'https://www.amazon.com.br/dp/B07YN1T44F' }],
    bought: false, splitOpen: false, names: []
  },
  // ── APARELHO DE JANTAR ──
  {
    id: 25, cat: 'cozinha', name: 'Aparelho de Jantar 10 Peças Porcelana — Flamingo Oxford Sofia Ouro',
    price: 'A consultar', note: 'Porcelana · 10 peças · Oxford',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2MYrK2j' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 26, cat: 'cozinha', name: 'Jogo de Jantar 10 Peças — Ryo Maresia',
    price: 'A consultar', note: '10 peças · Ryo Maresia',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1CkXZQX' }],
    bought: false, splitOpen: false, names: []
  },
  // ── JOGO DE SOBREMESA ──
  {
    id: 27, cat: 'cozinha', name: 'Jogo 6 Taças de Sobremesa Cameratta 257ml — Gamma',
    price: 'A consultar', note: '6 taças · 257ml',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/27n5gQ5' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 28, cat: 'cozinha', name: 'Conjunto de 6 Pratos Sobremesa 21,5cm — Ryo Maresia',
    price: 'A consultar', note: '6 pratos · 21,5cm',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2tWyu2J' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 29, cat: 'cozinha', name: 'Jogo de Sobremesa de Vidro 7 Peças — Doces, Sorvete, Toffee',
    price: 'A consultar', note: '7 peças em vidro',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/26p8r8b' }],
    bought: false, splitOpen: false, names: []
  },
  // ── KIT TOALHA ──
  {
    id: 30, cat: 'cama_banho', name: 'Jogo de Banhão 5 Peças Unika Branco — Karsten Cor U Lisa',
    price: 'A consultar', note: 'Karsten · 5 toalhas · Branco',
    img: '',
    links: [
      { label: '🛒 Mercado Livre 1', url: 'https://meli.la/1QDBfyc' },
      { label: '🛒 Mercado Livre 2', url: 'https://meli.la/1eXSBJN' }
    ],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 31, cat: 'cama_banho', name: 'Jogo 5 Toalhas Gigantes Banhão Lumina 100% Algodão — Karsten',
    price: 'A consultar', note: '100% algodão · 5 toalhas gigantes',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1y1GaXS' }],
    bought: false, splitOpen: false, names: []
  },
  // ── KIT JOGO DE CAMA ──
  {
    id: 32, cat: 'cama_banho', name: 'Jogo de Cama Casal 4 Peças 100% Algodão — Karsten Tom 200 Fios',
    price: 'A consultar', note: 'Karsten · 200 fios · 100% algodão',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/12M2Mky' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 33, cat: 'cama_banho', name: 'Colcha Casal Karsten Percal 160 Fios 100% Algodão — Cobre-leito',
    price: 'A consultar', note: 'Karsten · 160 fios',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2va3kdz' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 34, cat: 'cama_banho', name: 'Kit Colcha Casal Karsten 3 Peças Arturo Matelassado — Bege Giz',
    price: 'A consultar', note: 'Karsten · Matelassado · 3 peças',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/11asLKG' }],
    bought: false, splitOpen: false, names: []
  },
  // ── TÁBUA DE PASSAR ──
  {
    id: 35, cat: 'eletrodomesticos', name: 'Tábua de Passar Roupa com Cômoda e Prateleiras — Bela Store',
    price: 'A consultar', note: 'Com cômoda e prateleiras',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1ExFnZd' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 36, cat: 'eletrodomesticos', name: 'Kit Ferro a Vapor Black+Decker 127V + Tábua de Passar Roupa',
    price: 'A consultar', note: 'Black+Decker · 127V · kit completo',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1EA6Qrs' }],
    bought: false, splitOpen: false, names: []
  },
  // ── BOLEIRA ──
  {
    id: 37, cat: 'cozinha', name: 'Boleira de Vidro com Pé e Cúpula para Bolo/Torta Luxo — Alira',
    price: 'A consultar', note: 'Vidro com cúpula · Alira',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1VSo6kC' }],
    bought: false, splitOpen: false, names: []
  },
  // ── JOGO DE XÍCARA ──
  {
    id: 38, cat: 'cozinha', name: 'Jogo de 6 Xícaras Grandes 200ml com Pires — Unni Brisa Oxford',
    price: 'A consultar', note: '6 xícaras · 200ml · Oxford',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/14jxJhJ' }],
    bought: false, splitOpen: false, names: []
  },
  // ── JOGO DE TAÇA ──
  {
    id: 39, cat: 'cozinha', name: 'Jogo 6 Taças de Cristal Titanium Vinho Tinto 560ml — Xtra Bohemia',
    price: 'A consultar', note: '6 taças · 560ml · Bohemia',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/24ZzcPH' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 40, cat: 'cozinha', name: 'Jogo 6 Taças Grande Água Vidro Diamond Transparente Luxo',
    price: 'A consultar', note: '6 taças · vidro transparente',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1Wi8gdn' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 41, cat: 'cozinha', name: 'Kit Jarra de Vidro 1,2L Diamond + 6 Taças 330ml — Conjunto Luxo',
    price: 'A consultar', note: 'Jarra + 6 taças · 330ml',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/267P5ot' }],
    bought: false, splitOpen: false, names: []
  },
  // ── JOGO DE CADEIRA ──
  {
    id: 42, cat: 'moveis', name: 'Kit 2 Cadeiras Fibra Sintética com Braços Marrom — Área Externa/Varanda/Jardim',
    price: 'A consultar', note: 'Fibra sintética · Resistente · Marrom · Kit com 2',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/21Jx4MC' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 43, cat: 'moveis', name: 'Kit 4 Cadeiras Fibra Sintética com Braços Marrom — Área Externa/Varanda/Jardim',
    price: 'A consultar', note: 'Fibra sintética · Resistente · Marrom · Kit com 4',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/12PqT3z' }],
    bought: false, splitOpen: false, names: []
  },
  // ── MULTIUSO ──
  {
    id: 44, cat: 'organizacao', name: 'Armário para Lavanderia 60x160 Multiuso 2 Portas — Despensa',
    price: 'A consultar', note: '2 portas · Multiuso',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1e9HA3s' }],
    bought: false, splitOpen: false, names: []
  },
  // ── SAPATEIRA ──
  {
    id: 45, cat: 'organizacao', name: 'Sapateira Armário Organizador 2 Portas — Branco',
    price: 'A consultar', note: '2 portas · Branco',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2VYzv2R' }],
    bought: false, splitOpen: false, names: []
  },
  // ── FRUTEIRA ──
  {
    id: 46, cat: 'cozinha', name: 'Balcão Fruteira com Suporte para Filtro — Organizador Cozinha com Pés',
    price: 'A consultar', note: 'Com suporte para filtro de café',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/1HTQ9vn' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 47, cat: 'cozinha', name: 'Balcão Fruteira Isis 2 Portas 1 Gaveta',
    price: 'A consultar', note: '2 portas · 1 gaveta',
    img: '',
    links: [{ label: '🛒 Mercado Livre', url: 'https://meli.la/2dxorLk' }],
    bought: false, splitOpen: false, names: []
  }
];

// ===================== CATEGORIES =====================
const cats = {
  eletrodomesticos: { label: 'Eletrodomésticos', icon: '🏠', color: '#E8C98A' },
  eletronicos:      { label: 'Eletrônicos',       icon: '📱', color: '#B8D4E8' },
  cozinha:          { label: 'Cozinha',            icon: '🍳', color: '#E8D4B8' },
  moveis:           { label: 'Móveis & Decoração', icon: '🛋️', color: '#D4E8C8' },
  cama_banho:       { label: 'Cama & Banho',       icon: '🛏️', color: '#E8C8D4' },
  organizacao:      { label: 'Organização',        icon: '🗄️', color: '#D8D0E8' },
};

let activeCat = 'all';
let showOnlyAvailable = false;
let currentUploadId = null;

function save() {
  localStorage.setItem('wedding_gifts_v2', JSON.stringify(gifts));
}

function toggleBought(id) {
  const g = gifts.find(x => x.id === id);
  if (g) { g.bought = !g.bought; save(); render(); }
}

function toggleSplit(id) {
  const g = gifts.find(x => x.id === id);
  if (!g) return;
  g.splitOpen = !g.splitOpen;
  const el = document.getElementById('names-' + id);
  if (el) el.classList.toggle('open', g.splitOpen);
}

function addName(id) {
  const inp = document.getElementById('name-inp-' + id);
  if (!inp || !inp.value.trim()) return;
  const g = gifts.find(x => x.id === id);
  if (g) {
    g.names = g.names || [];
    g.names.push(inp.value.trim());
    inp.value = '';
    save();
    updateNamesOutput(id, g.names);
  }
}

function updateNamesOutput(id, names) {
  const out = document.getElementById('names-out-' + id);
  if (out) {
    out.textContent = names.length ? '👥 ' + names.join(' · ') : '';
  }
}

function filterCat(cat, btn) {
  activeCat = cat;
  showOnlyAvailable = false;
  document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  if (btn) btn.classList.add('active');
  render();
}

function filterAvailable() {
  showOnlyAvailable = !showOnlyAvailable;
  if (showOnlyAvailable) {
    activeCat = 'all';
    document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  }
  render();
}

function filterItems() {
  render();
}

// ===================== MANUAL PHOTO UPLOAD =====================
function triggerPhotoUpload(id) {
  currentUploadId = id;
  document.getElementById('photoUploadInput').click();
}

document.getElementById('photoUploadInput').addEventListener('change', function(e) {
  const file = e.target.files[0];
  if (!file || currentUploadId === null) return;

  if (file.size > 3 * 1024 * 1024) {
    alert('Por favor, escolha uma imagem menor que 3MB.');
    return;
  }

  const reader = new FileReader();
  reader.onload = function(evt) {
    const g = gifts.find(x => x.id === currentUploadId);
    if (g) {
      g.img = evt.target.result; // base64 data URL
      save();
      render();
    }
  };
  reader.readAsDataURL(file);
  e.target.value = ''; // reset input
});

function addNewItem() {
  const name = document.getElementById('newName').value.trim();
  if (!name) { alert('Por favor, insira o nome do presente.'); return; }
  const newItem = {
    id: Date.now(),
    cat: document.getElementById('newCat').value,
    name,
    price: document.getElementById('newPrice').value.trim() || 'A consultar',
    note: (document.getElementById('newOptions').value.trim() + ' ' + document.getElementById('newNote').value.trim()).trim(),
    img: document.getElementById('newImg').value.trim(),
    links: document.getElementById('newLink').value.trim()
      ? [{ label: '🛒 Ver produto', url: document.getElementById('newLink').value.trim() }]
      : [],
    bought: false, splitOpen: false, names: []
  };
  gifts.push(newItem);
  save();
  // Clear form
  ['newName','newPrice','newLink','newImg','newOptions','newNote'].forEach(id => document.getElementById(id).value = '');
  render();
  // scroll to bottom
  document.getElementById('giftsContainer').lastElementChild?.scrollIntoView({ behavior: 'smooth' });
}

function updateStats() {
  const total = gifts.length;
  const bought = gifts.filter(g => g.bought).length;
  const split = gifts.filter(g => g.names && g.names.length > 0).length;
  document.getElementById('totalItems').textContent = total;
  document.getElementById('boughtItems').textContent = bought;
  document.getElementById('availableItems').textContent = total - bought;
  document.getElementById('splitItems').textContent = split;
}

function render() {
  const search = document.getElementById('searchInput').value.toLowerCase();
  const container = document.getElementById('giftsContainer');
  container.innerHTML = '';

  const catGroups = activeCat === 'all' ? Object.keys(cats) : [activeCat];

  catGroups.forEach(cat => {
    let items = gifts.filter(g => {
      if (g.cat !== cat) return false;
      if (showOnlyAvailable && g.bought) return false;
      if (search && !g.name.toLowerCase().includes(search) && !g.note.toLowerCase().includes(search)) return false;
      return true;
    });
    if (items.length === 0) return;

    const sec = document.createElement('div');
    sec.className = 'section';

    const hdr = document.createElement('div');
    hdr.className = 'section-header';
    hdr.innerHTML = `
      <div class="section-icon" style="background:${cats[cat].color}20;color:${cats[cat].color}">${cats[cat].icon}</div>
      <h2 class="section-title">${cats[cat].label}</h2>
      <span class="section-count">${items.length} ${items.length === 1 ? 'item' : 'itens'}</span>
    `;
    sec.appendChild(hdr);

    const grid = document.createElement('div');
    grid.className = 'grid';

    items.forEach(g => {
      const card = document.createElement('div');
      card.className = 'card' + (g.bought ? ' purchased' : '');

      const imgHtml = g.img
        ? `<div class="card-img"><img src="${g.img}" alt="${g.name}" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="placeholder" style="display:none">${cats[g.cat].icon}</div><button class="photo-upload-btn" onclick="triggerPhotoUpload(${g.id})">📷 Trocar foto</button></div>`
        : `<div class="card-img"><div class="placeholder">${cats[g.cat].icon}</div><button class="photo-upload-btn" onclick="triggerPhotoUpload(${g.id})">📷 Adicionar foto</button></div>`;

      const linksHtml = g.links.map(l =>
        `<a class="btn-link" href="${l.url}" target="_blank" rel="noopener">${l.label}</a>`
      ).join('');

      const splitBtn = `<button class="badge badge-split" onclick="toggleSplit(${g.id})">👥 Dividir presente</button>`;
      const boughtBtn = `<button class="badge badge-bought" onclick="toggleBought(${g.id})">${g.bought ? '↩ Desmarcar' : '✓ Marcar como comprado'}</button>`;

      const namesHtml = `
        <div class="names-list ${g.splitOpen ? 'open' : ''}" id="names-${g.id}">
          <label>Adicione nomes dos convidados que vão dividir:</label>
          <div style="display:flex;gap:6px">
            <input type="text" placeholder="Nome do convidado" id="name-inp-${g.id}" onkeydown="if(event.key==='Enter')addName(${g.id})">
            <button class="btn-link" style="flex:0 0 auto;padding:6px 12px" onclick="addName(${g.id})">+</button>
          </div>
          <div class="names-output" id="names-out-${g.id}">${g.names && g.names.length ? '👥 ' + g.names.join(' · ') : ''}</div>
        </div>
      `;

      const isNoPrice = g.price === 'A consultar' || g.price === 'A definir em loja' || g.price === 'A definir';

      card.innerHTML = `
        ${imgHtml}
        <div class="card-body">
          <div class="card-name">${g.name}</div>
          <div class="card-price ${isNoPrice ? 'no-price' : ''}">${g.price}</div>
          ${g.note.trim() ? `<div class="card-options">${g.note.trim()}</div>` : ''}
        </div>
        ${linksHtml ? `<div class="card-footer">${linksHtml}</div>` : ''}
        <div class="card-actions">${splitBtn}${boughtBtn}</div>
        ${namesHtml}
      `;
      grid.appendChild(card);
    });

    sec.appendChild(grid);
    container.appendChild(sec);
  });

  updateStats();
}

render();
</script>
</body>
</html>
