[index.html.html](https://github.com/user-attachments/files/29384190/index.html.html)
# Lista-casamento<!DOCTYPE html>
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

  /* HIDDEN */
  .hidden { display: none !important; }
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
      </select>
      <input type="text" id="newOptions" placeholder="Opções disponíveis (ex: 127V/220V)" />
      <textarea id="newNote" placeholder="Observações (opcional)" class="full"></textarea>
      <button class="btn-add" onclick="addNewItem()">✓ Adicionar à Lista</button>
    </div>
  </div>
</div>

<footer>
  <p>Feito com ♡ para o casamento de <strong>Itany & Camilo</strong><br>
  Para marcar um item como comprado ou para dividir o presente, use os botões em cada card.<br>
  <small>As informações são salvas automaticamente neste dispositivo.</small></p>
</footer>

<script>
// ===================== DATA =====================
let gifts = JSON.parse(localStorage.getItem('wedding_gifts') || 'null') || [
  // ── ELETRODOMÉSTICOS ──
  {
    id: 1, cat: 'eletrodomesticos', name: 'Lava-Louças Midea SmartHome Black Inox 14 Serviços',
    price: 'R$ 2.559,00', note: '9 programas de lavagem · Função Open Dry',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_962069-MLU74948869813_032024-F.webp',
    links: [{ label: '🛒 Fast Shop', url: 'https://site.fastshop.com.br/lava-loucas-midea-smarthome-black-inox-com-14-servicos--09-programas-de-lavagem-e-funcao-open-dry---mdwef1433gbs-1qmdwef1433gb_prd/p' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 2, cat: 'eletrodomesticos', name: 'Lava-Louças Brastemp BLF10B 10 Serviços Inox',
    price: 'R$ 2.839,00', note: '127V · Aço Inoxidável',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_639071-MLU74885479773_032024-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/brastemp-blf10b-aco-inoxidavel-127v/p/MLB15927752' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 3, cat: 'eletrodomesticos', name: 'Lava-Louças Electrolux LS08E 8 Serviços Inox',
    price: 'A consultar', note: 'Lava & Seca 50 min · Display Digital · 127V',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_736271-MLU75091099451_032024-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/electrolux-lava-loucas-ls08e-prateado-127v/p/MLB49940241' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 4, cat: 'eletrodomesticos', name: 'Lava-Louças Midea 14 Serviços Preta',
    price: 'R$ 2.900,00', note: 'Cor preta · Design elegante',
    img: 'https://a-static.mlcdn.com.br/800x560/lava-loucas-14-servicos-preta-midea/magazineluiza/eh0aa5add5/81f67bcfd9e0f38e7d31e6f8d34d9a3d.jpg',
    links: [{ label: '🛒 Magazine Luiza', url: 'https://www.magazineluiza.com.br/lava-loucas-14-servicos-preta-midea/p/eh0aa5add5/ed/l14s/' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 5, cat: 'eletronicos', name: 'Robô Aspirador (várias opções disponíveis)',
    price: 'A consultar', note: 'Xiaomi S20 · Abir X9 · Liectroux G7 · Xiaomi Robot X20 Pro',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_985768-MLB54985574625_042023-F.webp',
    links: [
      { label: '🛒 Amazon', url: 'https://amzn.to/3NmPZP8' },
      { label: '🛒 Mercado Livre', url: 'https://meli.la/1ykiknV' }
    ],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 6, cat: 'moveis', name: 'Painel TV Ripado com Nichos – Bento Freijó Off White',
    price: 'A consultar', note: 'Para TV até 60 pol · DJ Móveis · Ripado com nichos',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_948461-MLU75042619820_032024-F.webp',
    links: [
      { label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/painel-para-tv-ate-60-polegadas-ripado-com-nichos-dj-moveis-bento-freijo-off-white/p/MLB23340089' }
    ],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 7, cat: 'moveis', name: 'Painel Suspenso TV 60 pol – Bento Freijó Off White DJ Móveis',
    price: 'A consultar', note: 'Painel suspenso · DJ Móveis',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_948461-MLU75042619820_032024-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/painel-suspenso-tv-60-pol-bento-freijo-off-white-dj-moveis/p/MLB53662388' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 8, cat: 'moveis', name: 'Painel TV Ripado com Nichos – Bento Freijó Cinza',
    price: 'A consultar', note: 'Para TV até 60 pol · DJ Móveis · Cinza',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_947611-MLB72416741820_102023-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/painel-para-tv-ate-60-polegadas-ripado-com-nichos-dj-moveis-bento-freijo-cinza/p/MLB23351810' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 9, cat: 'moveis', name: 'Painel de TV Roma com Nicho Suspenso – Moderno',
    price: 'A consultar', note: 'Suspenso · Design moderno para sala',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_831914-MLU74985099822_032024-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://produto.mercadolivre.com.br/MLB-3643574907-painel-de-tv-roma-com-nicho-suspenso-para-sala-moderno-_JM' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 10, cat: 'moveis', name: 'Sofá para Sala',
    price: 'A definir em loja', note: 'Iremos em lojas físicas para escolher o melhor modelo',
    img: '',
    links: [],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 11, cat: 'cozinha', name: 'Jogo de Facas Tramontina Plenus 9 Peças Aço Inox Preto',
    price: 'A consultar', note: 'Lâminas em aço inox · Cabos polipropileno preto',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_919201-MLB72474641869_102023-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/jogo-de-facas-plenus-9-pecas-com-lminas-em-aco-inox-e-cabos-de-polipropileno-cor-preto-tramontina/p/MLB27409895' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 12, cat: 'cozinha', name: 'Jogo de Facas Laguiole Inox com Cepo de Madeira 6 Peças Luxo',
    price: 'A consultar', note: 'Cepo de madeira · La Tour · Preto',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_753041-MLU73285264516_122023-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/jogo-de-facas-laguiole-inox-com-cepo-de-madeira-6-pecas-luxo-preto-la-tour/p/MLB47795671' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 13, cat: 'eletrodomesticos', name: 'Batedeira Arno com Pedestal Movimento Planetário Preta',
    price: 'A consultar', note: 'Cor preta · Movimento planetário',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_871074-MLU73406540673_122023-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/batedeira-arno-com-pedestal-movimento-planetario-preta-cor-preto/p/MLB58804100' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 14, cat: 'eletrodomesticos', name: 'Mixer Turbo 3 em 1 – 1000W 5 Velocidades Preto',
    price: 'A consultar', note: '3 em 1 · 1000W · 5 velocidades',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_900824-MLU74938296774_032024-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/mixer-turbo-3-em-1-1000w-5-velocidades-cor-preto/p/MLB66760336' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 15, cat: 'eletrodomesticos', name: 'Liquidificador Arno Power Max 1000 · 3.1L · 2200W · Preto',
    price: 'A consultar', note: '15 velocidades · 3.1L · 2200W',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_720951-MLU75278700742_042024-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/liquidificador-arno-power-max-1000-de-31-l-e-2200-w-com-15-velocidades-preto/p/MLB67008669' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 16, cat: 'eletrodomesticos', name: 'Liquidificador WAP WB2000 2L com Copo de Vidro · 1000W',
    price: 'A consultar', note: '2L · Copo de vidro · Velocidade variável · 220V',
    img: 'https://m.media-amazon.com/images/I/71m6XnKJkXL._AC_SX679_.jpg',
    links: [{ label: '🛒 Amazon', url: 'https://www.amazon.com.br/WAP-Liquidificador-WB2000-Velocidade-Vari%C3%A1vel/dp/B0DCP6WMQH/' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 17, cat: 'eletrodomesticos', name: 'Ventilador de Mesa 40cm Arno X-Treme 7 Pás 150W',
    price: 'A consultar', note: '40cm · 7 pás · 150W',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_942451-MLB74985099822_032024-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/ventilador-de-mesa-40cm-arno-x-treme-7-7-pas-150w-ve70/p/MLB28365895' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 18, cat: 'eletrodomesticos', name: 'Chaleira Elétrica Cadence CEL810 Pure Inox 1.7L',
    price: 'A consultar', note: 'Inox · 1.7 litros',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_847671-MLB54985099822_042023-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/chaleira-eletrica-cadence-cel810-pure-inox-17-litros/p/MLB24163174' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 19, cat: 'cozinha', name: 'Panelas de Cerâmica Ceraflame',
    price: 'A consultar', note: 'Manteigueira Francesa Brisa 250g · Ouro Cobalto',
    img: 'https://compreaqui.ceraflame.com.br/pub/media/catalog/product/cache/cba81df35bd94a5b83b79cc25be2eb85/S/E/SET-MANTEIGUEIRA-5011-AZUL-FOTO-1.jpg',
    links: [{ label: '🛒 Ceraflame', url: 'https://www.compreaqui.ceraflame.com.br/servir/manteigueira-francesa-brisa-250gr-01-ouro-cobalto' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 20, cat: 'cozinha', name: 'Frigideira Elétrica Philco Redstone Definitive 1.7L',
    price: 'A consultar', note: 'Cor Cinza/Vermelho · PPH240AFR',
    img: 'https://http2.mlstatic.com/D_NQ_NP_2X_817631-MLU73406540673_122023-F.webp',
    links: [{ label: '🛒 Mercado Livre', url: 'https://www.mercadolivre.com.br/frigideira-philco-17l-redstone-definitive-pph240afr-cor-cinzavermelho/p/MLB60090335' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 21, cat: 'cozinha', name: 'Kit Frigideiras RedSilver – Kit 1 (2 itens)',
    price: 'A consultar', note: 'Kit completo de frigideiras RedSilver',
    img: 'https://redsilverpanelas.com/ecommerce/media/catalog/product/cache/f87ef5a43f4b0f5d4d8d06e79ef95daf/k/i/kit1_redsilver.jpg',
    links: [{ label: '🛒 RedSilver', url: 'https://redsilverpanelas.com/ecommerce/kit/kit-1' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 22, cat: 'eletrodomesticos', name: 'Kit Ferro de Passar com Tábua',
    price: 'A consultar', note: 'Kit completo: ferro + tábua de passar roupa',
    img: '',
    links: [],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 23, cat: 'cozinha', name: 'Faqueiro Brinox Lyon 36 Peças Aço Inox',
    price: 'A consultar', note: '36 peças · Aço inox',
    img: 'https://m.media-amazon.com/images/I/71EWkH8mNUL._AC_SX679_.jpg',
    links: [{ label: '🛒 Amazon', url: 'https://www.amazon.com.br/dp/B07YN1T44F' }],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 24, cat: 'cama_banho', name: 'Kit Jogo de Cama Completo',
    price: 'A consultar', note: 'Lençol + fronha + cobre-leito completo',
    img: '',
    links: [],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 25, cat: 'cama_banho', name: 'Kit Toalha de Banho e Rosto',
    price: 'A consultar', note: 'Jogo completo de toalhas',
    img: '',
    links: [],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 26, cat: 'cozinha', name: 'Jogo de Sobremesa',
    price: 'A consultar', note: 'Conjunto completo para sobremesa',
    img: '',
    links: [],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 27, cat: 'cozinha', name: 'Aparelho de Jantar Completo',
    price: 'A consultar', note: 'Conjunto completo para jantar',
    img: '',
    links: [],
    bought: false, splitOpen: false, names: []
  },
  {
    id: 28, cat: 'cozinha', name: 'Jogo de Frigideiras Completo',
    price: 'A consultar', note: 'Conjunto de frigideiras variados tamanhos',
    img: '',
    links: [],
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
};

let activeCat = 'all';
let showOnlyAvailable = false;

function save() {
  localStorage.setItem('wedding_gifts', JSON.stringify(gifts));
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

function addNewItem() {
  const name = document.getElementById('newName').value.trim();
  if (!name) { alert('Por favor, insira o nome do presente.'); return; }
  const newItem = {
    id: Date.now(),
    cat: document.getElementById('newCat').value,
    name,
    price: document.getElementById('newPrice').value.trim() || 'A consultar',
    note: document.getElementById('newOptions').value.trim() + ' ' + document.getElementById('newNote').value.trim(),
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
        ? `<div class="card-img"><img src="${g.img}" alt="${g.name}" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="placeholder" style="display:none">${cats[g.cat].icon}</div></div>`
        : `<div class="card-img"><div class="placeholder">${cats[g.cat].icon}</div></div>`;

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
