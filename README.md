<Online školenie>
<html lang="sk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Revízny technik| Projektant| Bleskozvody</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: #111;
      color: #fff;
    }

    /* Horné menu (Header) */
    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background-color: #0d0d0d;
      padding: 15px 40px;
      border-bottom: 1px solid #222;
    }

    .logo-group {
      display: flex;
      flex-direction: column;
    }

    .logo-main {
      font-size: 20px;
      font-weight: bold;
      color: #ff5500;
      letter-spacing: 1px;
    }

    .logo-sub {
      font-size: 11px;
      color: #aaa;
      margin-top: 2px;
    }

    nav {
      display: flex;
      gap: 25px;
    }

    nav a {
      color: #ccc;
      text-decoration: none;
      font-size: 15px;
      transition: color 0.2s;
      cursor: pointer;
    }

    nav a:hover, nav a.active {
      color: #ff5500;
    }

    .header-actions {
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .btn-login {
      background-color: #e6e6e6;
      color: #111;
      border: none;
      padding: 10px 22px;
      border-radius: 6px;
      font-weight: bold;
      cursor: pointer;
      text-decoration: none;
      font-size: 14px;
      transition: background 0.2s;
    }

    .btn-login:hover {
      background-color: #ffffff;
    }

    /* Hlavný obsah (Sekcie) */
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 60px 20px;
    }

    .page-section {
      display: none;
    }

    .page-section.active {
      display: block;
    }

    /* Domovská sekcia (Hero) */
    .hero {
      display: flex;
      align-items: center;
      gap: 50px;
      justify-content: space-between;
    }

    .hero-cards {
      flex: 1;
      display: flex;
      gap: 20px;
    }

    .test-card-preview {
      flex: 1;
      background-color: #1e1e1e;
      border: 1px solid #333;
      border-radius: 12px;
      padding: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    }

    .test-card-preview h4 {
      color: #ff5500;
      margin-bottom: 12px;
      font-size: 16px;
      border-bottom: 1px solid #333;
      padding-bottom: 8px;
    }

    .test-item {
      background-color: #2a2a2a;
      padding: 10px 12px;
      margin-bottom: 8px;
      border-radius: 6px;
      font-size: 13px;
      display: flex;
      justify-content: space-between;
      color: #ddd;
    }

    .hero-text {
      flex: 1;
    }

    .hero-text h1 {
      font-size: 42px;
      line-height: 1.2;
      margin-bottom: 20px;
      font-weight: 800;
    }

    .hero-text p {
      color: #aaa;
      font-size: 16px;
      line-height: 1.6;
      margin-bottom: 35px;
    }

    .btn-orange {
      background-color: #e64a00;
      color: #fff;
      border: none;
      padding: 14px 28px;
      border-radius: 6px;
      font-weight: bold;
      font-size: 15px;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
      transition: background 0.2s;
    }

    .btn-orange:hover {
      background-color: #ff5500;
    }

    /* Stránka Cenník / Testy */
    .pricing-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 25px;
      margin-top: 30px;
    }

    .pricing-card {
      background-color: #1a1a1a;
      border: 1px solid #333;
      border-radius: 10px;
      padding: 30px;
      text-align: center;
    }

    .pricing-card h3 {
      font-size: 22px;
      margin-bottom: 15px;
      color: #ff5500;
    }

    .pricing-card .price {
      font-size: 36px;
      font-weight: bold;
      margin-bottom: 20px;
    }

    /* Stránka Kontakt & Skúšobná verzia */
    .info-box {
      background-color: #1a1a1a;
      border: 1px solid #333;
      border-radius: 10px;
      padding: 40px;
      max-width: 600px;
      margin: 0 auto;
    }

    .info-box h2 {
      color: #ff5500;
      margin-bottom: 20px;
    }

    .info-detail {
      font-size: 18px;
      margin-bottom: 12px;
      color: #ddd;
    }

    @media (max-width: 900px) {
      .hero {
        flex-direction: column-reverse;
      }
      header {
        flex-direction: column;
        gap: 15px;
      }
    }
  </style>
</head>
<body>

  <!-- HORNÉ MENU -->
  <header>
    <div class="logo-group">
      <div class="logo-main">Revízny technik| Projektant| Bleskozvody</div>
      <div class="logo-sub">Elektro revízny technik</div>
    </div>

    <nav>
      <a onclick="showSection('home')" class="nav-link active" id="link-home">Hlavná stránka</a>
      <a onclick="showSection('cenik')" class="nav-link" id="link-cenik">Cenník</a>
      <a onclick="showSection('skusobna')" class="nav-link" id="link-skusobna">Skúšobná verzia</a>
      <a onclick="showSection('kontakt')" class="nav-link" id="link-kontakt">Kontakt</a>
    </nav>

    <div class="header-actions">
      <button class="btn-login" onclick="alert('Prihlasovací formulár sa pripravuje.')">Prihlásiť sa</button>
    </div>
  </header>

  <div class="container">

    <!-- 1. HLAVNÁ STRÁNKA (HERO) -->
    <section id="home" class="page-section active">
      <div class="hero">
        <!-- Nahradenie fotiek dvoma ukážkovými testami -->
        <div class="hero-cards">
          <div class="test-card-preview">
            <h4>Ukážka: Test RT 1</h4>
            <div class="test-item"><span>Otázka 1: Ochrana pred zásahom</span><span>▶</span></div>
            <div class="test-item"><span>Otázka 2: Meranie odporu</span><span>▶</span></div>
            <div class="test-item"><span>Otázka 3: Bleskozvody STN</span><span>▶</span></div>
          </div>
          <div class="test-card-preview">
            <h4>Ukážka: Test RT 2</h4>
            <div class="test-item"><span>Otázka 1: Predpisy BOZP</span><span>▶</span></div>
            <div class="test-item"><span>Otázka 2: Požiarna ochrana</span><span>▶</span></div>
            <div class="test-item"><span>Otázka 3: Bezpečnostný technik</span><span>▶</span></div>
          </div>
        </div>

        <!-- Hlavný text -->
        <div class="hero-text">
          <h1>Správa školení</h1>
          <p>Ať už pořádáte školení interně, zadáváte je externistům nebo agentuře, mějte kontrolu nad jejich konáním, výstupy a prezenčními listinami potřebnými k naplnění compliance povinností.</p>
          <button class="btn-orange" onclick="showSection('cenik')">Vybrať testy</button>
        </div>
      </div>
    </section>

    <!-- 2. CENNÍK (S ODKAZMI NA PODUJATIA / BALÍKY) -->
    <section id="cenik" class="page-section">
      <h2 style="text-align: center; margin-bottom: 10px;">Vybrať testy a podujatia</h2>
      <p style="text-align: center; color: #aaa; margin-bottom: 40px;">Zvoľte si rozsah prístupu k testom pre BOZP, TPO a elektrotechnikov.</p>
      
      <div class="pricing-grid">
        <div class="pricing-card">
          <h3>1x Test</h3>
          <div class="price">10 €</div>
          <p style="color: #aaa; margin-bottom: 20px;">Jednorazový prístup k vybranému podujatiu alebo testu.</p>
          <button class="btn-orange" onclick="alert('Odkaz na podujatie 1x test')">Kúpiť 1x test</button>
        </div>

        <div class="pricing-card" style="border-color: #ff5500;">
          <h3>2x Test</h3>
          <div class="price">15 €</div>
          <p style="color: #aaa; margin-bottom: 20px;">Zvýhodnený prístup ku 2 podujatiam alebo testom.</p>
          <button class="btn-orange" onclick="alert('Odkaz na podujatie 2x test')">Kúpiť 2x test</button>
        </div>

        <div class="pricing-card">
          <h3>5x Test</h3>
          <div class="price">20 €</div>
          <p style="color: #aaa; margin-bottom: 20px;">Kompletný prístup k 5 podujatiam a testom.</p>
          <button class="btn-orange" onclick="alert('Odkaz na podujatie 5x test')">Kúpiť 5x test</button>
        </div>
      </div>
    </section>

    <!-- 3. SKÚŠOBNÁ VERZIA -->
    <section id="skusobna" class="page-section">
      <div class="info-box">
        <h2>Skúšobná verzia</h2>
        <p style="color: #ccc; line-height: 1.6; margin-bottom: 20px;">
          Vyskúšajte si aplikáciu a vzorové testy na 7 dní zadarmo bez akýchkoľvek záväzkov.
        </p>
        <button class="btn-orange" onclick="alert('Spúšťa sa skúšobná verzia...')">Spustiť zadarmo</button>
      </div>
    </section>

    <!-- 4. KONTAKT -->
    <section id="kontakt" class="page-section">
      <div class="info-box">
        <h2>KONTATNÉ ÚDAJE</h2>
        <div class="info-detail"><strong>Meno:</strong> Tomáš Trenčan</div>
        <div class="info-detail"><strong>Telefón:</strong> 0911 757 674</div>
        <div class="info-detail"><strong>E-mail:</strong> ttrencan1980@gmail.com</div>
      </div>
    </section>

  </div>

  <!-- JAVASCRIPT PRE PREPÍNANIE STRÁNOK -->
  <script>
    function showSection(sectionId) {
      // Skryť všetky sekcie
      document.querySelectorAll('.page-section').forEach(section => {
        section.classList.remove('active');
      });

      // Odobrať aktívnu triedu zo všetkých odkazov v menu
      document.querySelectorAll('.nav-link').forEach(link => {
        link.classList.remove('active');
      });

      // Zobraziť vybranú sekciu
      document.getElementById(sectionId).classList.add('active');

      // Zvýrazniť aktívny odkaz v menu
      const activeLink = document.getElementById('link-' + sectionId);
      if (activeLink) {
        activeLink.classList.add('active');
      }
    }
  </script>

</body>
</html>
