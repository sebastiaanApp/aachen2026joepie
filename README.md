
<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { font-family: 'DM Sans', sans-serif; background: #faf7f2; color: #2c2820; line-height: 1.7; }

  /* HERO */
  .hero {
    background: linear-gradient(160deg, #1a3a2a 0%, #2d5a3d 40%, #3d7a52 70%, #8b6914 100%);
    color: white;
    padding: 80px 40px 60px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 300px; height: 300px;
    border-radius: 50%;
    background: rgba(255,255,255,0.04);
  }
  .hero::after {
    content: '';
    position: absolute;
    bottom: -80px; left: -40px;
    width: 250px; height: 250px;
    border-radius: 50%;
    background: rgba(255,255,255,0.03);
  }
  .hero-badge {
    display: inline-block;
    background: rgba(255,255,255,0.15);
    border: 1px solid rgba(255,255,255,0.3);
    border-radius: 40px;
    padding: 6px 18px;
    font-size: 12px;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 24px;
    font-weight: 500;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: 64px;
    font-weight: 700;
    line-height: 1.1;
    margin-bottom: 12px;
  }
  .hero h1 em { font-style: italic; color: #f0c060; }
  .hero-subtitle {
    font-size: 18px;
    opacity: 0.85;
    margin-bottom: 8px;
    font-weight: 300;
  }
  .hero-dates {
    font-family: 'Playfair Display', serif;
    font-size: 15px;
    opacity: 0.7;
    letter-spacing: 1px;
    margin-bottom: 40px;
  }
  .hero-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
  }
  .tag {
    background: rgba(255,255,255,0.12);
    border: 1px solid rgba(255,255,255,0.2);
    border-radius: 30px;
    padding: 5px 14px;
    font-size: 12px;
    font-weight: 500;
  }

  /* MAIN CONTENT */
  .content { max-width: 900px; margin: 0 auto; padding: 0 24px; }

  /* INTRO STRIP */
  .intro-strip {
    background: #2d5a3d;
    color: white;
    padding: 32px 40px;
    display: flex;
    align-items: center;
    gap: 32px;
  }
  .intro-strip p { font-size: 15px; line-height: 1.8; opacity: 0.9; }
  .intro-icon { font-size: 48px; flex-shrink: 0; }

  /* SECTION HEADERS */
  .section {
    padding: 56px 0 0;
  }
  .section-label {
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: #8b6914;
    font-weight: 500;
    margin-bottom: 8px;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: 36px;
    font-weight: 700;
    color: #1a3a2a;
    margin-bottom: 32px;
    line-height: 1.2;
  }
  .section-title em { font-style: italic; color: #2d5a3d; }

  /* CARDS GRID */
  .cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 20px;
    margin-bottom: 12px;
  }
  .card {
    background: white;
    border-radius: 16px;
    padding: 24px;
    border: 1px solid #e8e2d8;
    transition: transform 0.2s, box-shadow 0.2s;
    position: relative;
    overflow: hidden;
  }
  .card:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,0,0,0.08); }
  .card-accent {
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 4px;
    border-radius: 16px 16px 0 0;
  }
  .accent-green { background: #2d5a3d; }
  .accent-amber { background: #8b6914; }
  .accent-teal { background: #1a6b5a; }
  .accent-rose { background: #8b3a4a; }
  .accent-blue { background: #1a3a6b; }
  .accent-purple { background: #5a3a8b; }
  .card-emoji { font-size: 28px; margin-bottom: 12px; display: block; }
  .card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    font-weight: 700;
    color: #1a3a2a;
    margin-bottom: 8px;
  }
  .card p { font-size: 13.5px; color: #5a5248; line-height: 1.65; margin-bottom: 12px; }
  .card-link {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    font-size: 12px;
    color: #2d5a3d;
    font-weight: 500;
    text-decoration: none;
    border-bottom: 1px solid #2d5a3d;
    padding-bottom: 1px;
  }
  .card-tip {
    background: #f5f0e8;
    border-radius: 8px;
    padding: 8px 12px;
    font-size: 12px;
    color: #6b5a40;
    margin-top: 8px;
    line-height: 1.5;
  }
  .card-tip strong { color: #8b6914; }
  .maps-link {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    font-size: 11px;
    color: #8b6914;
    text-decoration: none;
    margin-top: 6px;
  }

  /* HIGHLIGHT BOX */
  .highlight-box {
    background: #1a3a2a;
    color: white;
    border-radius: 20px;
    padding: 40px;
    margin: 40px 0;
    position: relative;
    overflow: hidden;
  }
  .highlight-box::after {
    content: '📚';
    position: absolute;
    right: 30px;
    top: 50%;
    transform: translateY(-50%);
    font-size: 80px;
    opacity: 0.12;
  }
  .highlight-box h3 {
    font-family: 'Playfair Display', serif;
    font-size: 26px;
    margin-bottom: 16px;
    color: #f0c060;
  }
  .highlight-box p { opacity: 0.9; font-size: 14px; line-height: 1.8; }
  .highlight-list { list-style: none; margin-top: 16px; }
  .highlight-list li {
    padding: 8px 0;
    border-bottom: 1px solid rgba(255,255,255,0.1);
    font-size: 14px;
    display: flex;
    align-items: flex-start;
    gap: 10px;
  }
  .highlight-list li:last-child { border-bottom: none; }
  .highlight-list a { color: #f0c060; text-decoration: none; border-bottom: 1px solid rgba(240,192,96,0.4); }

  /* DIVIDER */
  .divider {
    height: 1px;
    background: linear-gradient(to right, transparent, #c8b890, transparent);
    margin: 48px 0 0;
  }

  /* TIPS GRID */
  .tips-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }
  .tip-box {
    background: white;
    border: 1px solid #e8e2d8;
    border-radius: 12px;
    padding: 20px;
  }
  .tip-box h4 {
    font-size: 14px;
    font-weight: 500;
    color: #1a3a2a;
    margin-bottom: 8px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .tip-box ul { list-style: none; }
  .tip-box ul li { font-size: 13px; color: #5a5248; padding: 3px 0; }
  .tip-box ul li::before { content: '→ '; color: #8b6914; font-weight: 500; }

  /* PROEVEN */
  .food-strip {
    background: #f5ede0;
    border-radius: 16px;
    padding: 32px;
    margin: 40px 0;
    border: 1px solid #e8d8c0;
  }
  .food-items {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 16px;
  }
  .food-item {
    background: white;
    border-radius: 40px;
    padding: 8px 18px;
    font-size: 13px;
    font-weight: 500;
    color: #5a3a20;
    border: 1px solid #e8d0b0;
  }
  .food-item span { margin-right: 6px; }

  /* FOTO SECTION */
  .foto-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-top: 4px;
  }
  .foto-item {
    background: white;
    border: 1px solid #e8e2d8;
    border-radius: 12px;
    padding: 16px 18px;
    font-size: 13px;
    color: #3a3028;
  }
  .foto-item strong { display: block; font-size: 13px; font-weight: 500; color: #1a3a2a; margin-bottom: 2px; }
  .foto-item span { color: #7a6a58; font-size: 12px; }

  /* SLOGAN FOOTER */
  .footer {
    background: linear-gradient(135deg, #1a3a2a, #2d5a3d);
    color: white;
    text-align: center;
    padding: 64px 40px;
    margin-top: 64px;
  }
  .slogan {
    font-family: 'Playfair Display', serif;
    font-size: 32px;
    font-style: italic;
    color: #f0c060;
    margin-bottom: 20px;
    line-height: 1.3;
  }
  .footer p { font-size: 15px; opacity: 0.85; max-width: 500px; margin: 0 auto; line-height: 1.8; }
  .footer-hearts { font-size: 24px; margin-top: 24px; letter-spacing: 8px; }

  /* REGENWEER */
  .rain-section {
    background: #eef2f8;
    border-radius: 16px;
    padding: 32px;
    border: 1px solid #d0d8e8;
    margin: 12px 0;
  }
  .rain-section h4 {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    color: #1a3a6b;
    margin-bottom: 16px;
  }

  .full-divider { height: 1px; background: #e8e0d0; margin: 0; }

  @media (max-width: 600px) {
    .hero h1 { font-size: 42px; }
    .tips-grid, .foto-list { grid-template-columns: 1fr; }
    .intro-strip { flex-direction: column; gap: 16px; text-align: center; }
    .hero { padding: 60px 24px 40px; }
    .highlight-box::after { display: none; }
  }
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="hero-badge">✦ Weekendtrip voor 2 ✦</div>
  <h1>Hey babe, we gaan naar<br><em>Aachen</em></h1>
  <div class="hero-subtitle">Een weekend vol charme, cultuur & kleine avonturen</div>
  <div class="hero-dates">Justine <3 Seb &nbsp;·&nbsp; 15 – 17 mei 2025 &nbsp;·&nbsp; 2 nachten &nbsp;·&nbsp; Oneindig veel keuze</div>
  <div class="hero-tags">
    <span class="tag">🥾 Wandelen</span>
    <span class="tag">📚 Boekenwinkels</span>
    <span class="tag">🐘 Dierenpark</span>
    <span class="tag">🎲 Games & Bordspellen</span>
    <span class="tag">🌿 Natuur</span>
    <span class="tag">☕ Terrasjes</span>
    <span class="tag">🛍️ Shoppen</span>
    <span class="tag">🏛️ Musea</span>
  </div>
</div>

<!-- INTRO STRIP -->
<div class="intro-strip">
  <div class="intro-icon">🗺️</div>
  <p>Aachen is een van de meest onderschatte steden van Europa — op een steenworp van de Belgische grens. Hier botsen geschiedenis en hipheid op de lekkerste manier. Van middeleeuwse kathedralen tot cozy boekencafés, van verborgen wandelpaden tot retrogamewinkels die je nooit meer wil verlaten. Deze brochure is geen dagplanning, maar een menukaart van alles wat Aachen te bieden heeft. Kies wat jullie anstaat.</p>
</div>

<div class="content">

  <!-- NATUUR & WANDELEN -->
  <div class="section">
    <div class="section-label">Natuur & Beweging</div>
    <div class="section-title">🥾 Wandelen & <em>de natuur in</em></div>

    <div class="cards-grid">
      <div class="card">
        <div class="card-accent accent-green"></div>
        <span class="card-emoji">🌲</span>
        <h3>Aachener Wald</h3>
        <p>Het groene hart van Aachen. Een uitgestrekt bosgebied direct aan de rand van de stad met talloze wandelpaden voor elk niveau. Perfect voor een ochtendwandeling met koffie erna.</p>
        <div class="card-tip"><strong>Tip:</strong> Neem de route langs de Wildbach-beek voor extra sfeer.</div>
        <br><a href="https://maps.google.com/?q=Aachener+Wald" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-green"></div>
        <span class="card-emoji">🦌</span>
        <h3>Wildpark Aachen</h3>
        <p>Een gratis wildpark in het bos met herten, wilde zwijnen en andere dieren in een natuurlijke omgeving. Heerlijk te combineren met een boswandeling.</p>
        <div class="card-tip"><strong>Gratis toegang!</strong> Ideaal als luchtige start van de dag.</div>
        <br><a href="https://maps.google.com/?q=Wildpark+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-teal"></div>
        <span class="card-emoji">🌻</span>
        <h3>Karlsgarten</h3>
        <p>Een romantische, historische tuin verscholen in het stadscentrum. Omgeven door middeleeuwse muren, vol bloemen en rustige hoekjes. Het perfecte plekje om even neer te zitten.</p>
        <div class="card-tip"><strong>Verborgen parel:</strong> Weinig toeristen kennen dit hoekje.</div>
        <br><a href="https://maps.google.com/?q=Karlsgarten+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-green"></div>
        <span class="card-emoji">💧</span>
        <h3>Drielandenpunt hike</h3>
        <p>Op slechts 20 minuten rijden van Aachen ligt het punt waar België, Nederland en Duitsland samenkomen. Mooie wandelroutes, panoramisch uitzicht en een unieke grensbelevenis.</p>
        <div class="card-tip"><strong>Dagtrip optie:</strong> Combineer met lunch in Vaals of Kelmis.</div>
        <br><a href="https://maps.google.com/?q=Drielandenpunt+Vaals" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-teal"></div>
        <span class="card-emoji">🌊</span>
        <h3>Vaalserberg & Hells Valley</h3>
        <p>Spectaculaire natuur net buiten de stad. Diepe ravijnen, dicht bos en rotsige paden langs de Geul. Perfecte hike voor wie iets meer avontuur zoekt.</p>
        <div class="card-tip"><strong>Niveau:</strong> Matig, goed wandelschoenen aangeraden.</div>
        <br><a href="https://maps.google.com/?q=Vaalserberg" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-green"></div>
        <span class="card-emoji">🌿</span>
        <h3>Botanische Tuin Aachen</h3>
        <p>Een rustige groene oase met prachtige plantencollecties, waterpartijen en serres. Geweldig voor plantenliefhebbers en wie even de stad wil ontsnappen.</p>
        <div class="card-tip"><strong>Mei tip:</strong> In de lente staat alles in bloei — perfecte timing!</div>
        <br><a href="https://maps.google.com/?q=Botanischer+Garten+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>
    </div>
  </div>

  <!-- DIERENPARK -->
  <div class="section">
    <div class="section-label">Dieren & Natuur</div>
    <div class="section-title">🐘 <em>Dierenparkavontuur</em></div>

    <div class="cards-grid">
      <div class="card">
        <div class="card-accent accent-green"></div>
        <span class="card-emoji">🦁</span>
        <h3>Aachener Zoo – Euregiozoo</h3>
        <p>Een charmante stadszoo met meer dan 900 dieren uit 200 soorten. Compact, goed onderhouden en met een heel gezellige sfeer. Van roofdieren tot exotische vogels — er is van alles te zien.</p>
        <div class="card-tip"><strong>Aanrader:</strong> Goed te combineren met een wandeling in het aangrenzende park.</div>
        <a href="http://www.euregiozoo.de/" target="_blank" class="card-link">🌐 euregiozoo.de ↗</a><br>
        <a href="https://maps.google.com/?q=Euregiozoo+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-teal"></div>
        <span class="card-emoji">🦋</span>
        <h3>Schmetterlingshaus omgeving</h3>
        <p>In de buurt van Aken vind je prachtige vlindertunnel-ervaringen en interactieve natuurbelevingen. Check lokale evenementen in de regio voor tijdelijke expo's.</p>
        <div class="card-tip"><strong>Tip:</strong> Combineer met het Euregiozoo op dezelfde dag.</div>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- BOEKENWINKELS HIGHLIGHT -->
  <div class="highlight-box">
    <h3>📚 De Boekenminnaar's Gids voor Aachen</h3>
    <p>Aachen heeft een verrassend rijke boekencultuur voor een stad van zijn formaat. Hieronder de absolute must-visits voor bibliofiele reizigers.</p>
    <ul class="highlight-list">
      <li>
        <span>📖</span>
        <div>
          <strong>Mayersche Buchhandlung</strong> — De koningin van de Aachense boekenwinkels. Een meerdere verdiepingen tellende boekenhemel in het hartje van de stad, met een enorm aanbod van Duitstalige én Engelstalige boeken, cadeau-artikelen en een gezellig zithoekje.
          <br><a href="https://www.thalia.de/buchhandlung/5755" target="_blank">→ thalia.de/mayersche</a> &nbsp;|&nbsp; <a href="https://maps.google.com/?q=Mayersche+Aachen" target="_blank">📍 Maps</a>
        </div>
      </li>
      <li>
        <span>🏛️</span>
        <div>
          <strong>Bookstore Schmetz am Dom</strong> — Vlak bij de kathedraal, historisch pand, warme sfeer. Specialiteit in kunst- en cultuurboeken, maar ook heerlijke algemene selectie. Het type winkel waar je een uur binnen stapt en drie uur later buiten komt.
          <br><a href="http://www.buchhandlung-schmetz.de/" target="_blank">→ buchhandlung-schmetz.de</a> &nbsp;|&nbsp; <a href="https://maps.google.com/?q=Buchhandlung+Schmetz+Aachen" target="_blank">📍 Maps</a>
        </div>
      </li>
      <li>
        <span>🔍</span>
        <div>
          <strong>Antiquarische boekenwinkels</strong> — Aachen heeft meerdere antiquariaten verstopt in zijstraatjes. Perfect voor wie op zoek gaat naar verborgen boekenparels. Vraag locals naar tips in de buurt van de Jakobstraße.
        </div>
      </li>
    </ul>
  </div>

  <!-- GAMES & BORDSPELLEN -->
  <div class="section">
    <div class="section-label">Games & Play</div>
    <div class="section-title">🎲 <em>Speelparadijs</em> Aachen</div>

    <div class="cards-grid">
      <div class="card">
        <div class="card-accent accent-purple"></div>
        <span class="card-emoji">🐇</span>
        <h3>White Rabbit – Community Game Store</h3>
        <p>De geliefde lokale bordspellenwinkel van Aachen. Een gemeenschapswinkel met hart — hier vind je een geweldige selectie bordspellen, kaartspellen en rollenspellen, plus een community die weet waar ze het over heeft.</p>
        <div class="card-tip"><strong>Tip:</strong> Vraag de medewerkers om aanbevelingen — ze zijn geweldig behulpzaam.</div>
        <a href="http://www.whiterabbit-cgs.de/" target="_blank" class="card-link">🌐 whiterabbit-cgs.de ↗</a><br>
        <a href="https://maps.google.com/?q=White+Rabbit+Game+Store+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-purple"></div>
        <span class="card-emoji">🕹️</span>
        <h3>1Up Store Aachen</h3>
        <p>Een paradijs voor retrogame-liefhebbers. Vintage consoles, klassieke games, merchandise en nostalgie in overvloed. De winkel ruikt bijna naar de jaren '90 — in de beste zin van het woord.</p>
        <div class="card-tip"><strong>Retro pick:</strong> Controleer de ramsj-bakken voor verborgen gouden gameparels.</div>
        <a href="https://maps.google.com/?q=1Up+Store+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-blue"></div>
        <span class="card-emoji">🎮</span>
        <h3>Retro Gaming in Aachen</h3>
        <p>Naast de 1Up Store zijn er ook verscheidene kringloopwinkels en Flohmarkt-stands waar je soms onverwachte retrogame-vondsten doet. Een geweldige schatzoekactiviteit voor twee.</p>
        <div class="card-tip"><strong>Check:</strong> Weekendmarkt op het Marktplatz voor vintage items.</div>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- MUSEA -->
  <div class="section">
    <div class="section-label">Cultuur & Curiosa</div>
    <div class="section-title">🏛️ Originele & <em>bijzondere musea</em></div>

    <div class="cards-grid">
      <div class="card">
        <div class="card-accent accent-rose"></div>
        <span class="card-emoji">🎨</span>
        <h3>Ludwig Forum for International Art</h3>
        <p>Een imposant voormalig fabrieksgebouw dat nu hedendaagse internationale kunst herbergt. Altijd boeiend, soms provocerend, nooit saai. De collectie is groot en gevarieerd — van pop art tot installaties.</p>
        <div class="card-tip"><strong>Museumstip:</strong> Controleer de tijdelijke tentoonstellingen voor extra verrassingen.</div>
        <a href="http://www.ludwigforum.de/" target="_blank" class="card-link">🌐 ludwigforum.de ↗</a><br>
        <a href="https://maps.google.com/?q=Ludwig+Forum+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-amber"></div>
        <span class="card-emoji">👑</span>
        <h3>Schatzkammer Dom Aachen</h3>
        <p>De schatkamer van de Kathedraal van Aachen bevat een van de rijkste collecties middeleeuwse kunst in Europa. Verbijsterende relikwieën, gouden kunstwerken en de sfeer van 1200 jaar geschiedenis.</p>
        <div class="card-tip"><strong>Tip:</strong> Combineer met een bezoek aan de kathedraal zelf — samen onvergetelijk.</div>
        <a href="https://maps.google.com/?q=Domschatzkammer+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-rose"></div>
        <span class="card-emoji">🏚️</span>
        <h3>Couven Museum</h3>
        <p>Een verborgen parel: een volledig ingericht 18e-eeuws burgerhuis vol historische interieurs, curiositeiten en sfeervol meubilairkunst. Alsof de tijd er stillstond — fascinerend en origineel.</p>
        <div class="card-tip"><strong>Origineel:</strong> Weinig bezoekers, heel authentieke sfeer.</div>
        <a href="https://maps.google.com/?q=Couven+Museum+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-blue"></div>
        <span class="card-emoji">🔭</span>
        <h3>RWTH Aachen – Open Campus</h3>
        <p>De technische universiteit heeft soms open dagen en tentoonstellingen die gratis toegankelijk zijn. De architectuur van de campus is ook op zichzelf al de moeite waard om door te wandelen.</p>
        <div class="card-tip"><strong>Check:</strong> Actueel programma via rwth-aachen.de</div>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- CAFÉS & TERRASSEN -->
  <div class="section">
    <div class="section-label">Koffie & TerrasjesCultuur</div>
    <div class="section-title">☕ Chillplekken & <em>gezellige cafés</em></div>

    <div class="cards-grid">
      <div class="card">
        <div class="card-accent accent-amber"></div>
        <span class="card-emoji">☕</span>
        <h3>Leni loves coffee</h3>
        <p>De hipste koffiebar van Aachen. Specialty coffee, warme sfeer, mooie inrichting en medewerkers die echt passie hebben voor hun vak. Perfect voor een trage ochtend met een boek op schoot.</p>
        <div class="card-tip"><strong>Bestelling:</strong> Probeer de flat white of seizoensspecialiteit.</div>
        <a href="https://maps.google.com/?q=Leni+loves+coffee+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-amber"></div>
        <span class="card-emoji">🌸</span>
        <h3>Café Juli</h3>
        <p>Een romantisch, licht ingericht café met een fantastisch terras. De taarten zijn huisgemaakt, de koffie is goed en de sfeer is precies zoals je een middag-in-de-zon wil doorbrengen.</p>
        <div class="card-tip"><strong>Terras tip:</strong> Kom vroeg voor de beste plekjes buiten.</div>
        <a href="https://maps.google.com/?q=Café+Juli+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-rose"></div>
        <span class="card-emoji">🍺</span>
        <h3>Pontstraße – de bruisende bar-strip</h3>
        <p>De gezelligste straat van Aachen voor een avondje uit. Vol cafés, biercafés en terrassen. Studentensfeer, levendige vibe en de ideale plek voor een biertje na een dag stadsverkennen.</p>
        <div class="card-tip"><strong>Aachener Bier:</strong> Probeer de lokale brouwerijbieren die hier uitgeschonken worden.</div>
        <a href="https://maps.google.com/?q=Pontstrasse+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-teal"></div>
        <span class="card-emoji">🌿</span>
        <h3>Elisengarten – Terras in het park</h3>
        <p>Een charmant stadspark met een paviljoen en terras midden in het centrum. Rondom historische gebouwen, groene gazons en een ontspannen sfeer. De perfecte picknick- of terraslocatie.</p>
        <div class="card-tip"><strong>Mei tip:</strong> Het park staat in de lente prachtig in bloei.</div>
        <a href="https://maps.google.com/?q=Elisengarten+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-amber"></div>
        <span class="card-emoji">🧁</span>
        <h3>Bäckerei & lokale bakkers</h3>
        <p>Aachen heeft uitstekende Bäckereien met verse Brötchen, Kuchen en typisch Duits bakkersgoed. Een ontbijt van een lokale bakker met koffie to go is de perfecte start van elke dag.</p>
        <div class="card-tip"><strong>Must-try:</strong> Aachener Printen (speciaal peperkoekgebak van Aachen).</div>
      </div>

      <div class="card">
        <div class="card-accent accent-rose"></div>
        <span class="card-emoji">🌙</span>
        <h3>Avondsfeer in de binnenstad</h3>
        <p>Als de zon ondergaat krijgt Aachen een prachtige gouden gloed. De verlichte kathedraal, de oude markt en de gezellige kroegjes maken van een avondwandeling een echte belevenis.</p>
        <div class="card-tip"><strong>Romantisch:</strong> Wandel via het Katschhof naar het Münsterplatz bij schemer.</div>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- SHOPPEN -->
  <div class="section">
    <div class="section-label">Retail Therapy</div>
    <div class="section-title">🛍️ Shoppen & <em>slenteren</em></div>

    <div class="cards-grid">
      <div class="card">
        <div class="card-accent accent-rose"></div>
        <span class="card-emoji">🏬</span>
        <h3>Adalbertstraße & Krämerstraße</h3>
        <p>De voornaamste winkelstraten van Aachen. Afgewisseld met lokale boetieks, internationale ketens en gezellige terrassen. Goed voor een slenternamiddag met tasjes.</p>
        <a href="https://maps.google.com/?q=Adalbertstrasse+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-amber"></div>
        <span class="card-emoji">🏺</span>
        <h3>Klebermarkt & Flohmarkt</h3>
        <p>In het weekend is er vaak een rommelmarkt of Flohmarkt in de stad. Perfect om vintage items, curiositeiten en unieke souvenirs te scoren. Nooit hetzelfde, altijd verassend.</p>
        <div class="card-tip"><strong>Check:</strong> Aachen.de/veranstaltungen voor het weekendprogramma.</div>
      </div>

      <div class="card">
        <div class="card-accent accent-teal"></div>
        <span class="card-emoji">🎁</span>
        <h3>Lokale designwinkels & concept stores</h3>
        <p>Aachen heeft steeds meer kleine designwinkeltjes en concept stores verspreid over de binnenstad. Zoek in de zijstraatjes van de Pontstraße en rond de Münsterplatz.</p>
        <div class="card-tip"><strong>Tip:</strong> Vraag in een lokaal café naar hun favoriete winkels — locals weten het best.</div>
      </div>

      <div class="card">
        <div class="card-accent accent-purple"></div>
        <span class="card-emoji">🖼️</span>
        <h3>Kunstgaleries & atelier-winkels</h3>
        <p>Rondom het Ludwig Forum en in de Studentenwijk vind je kleine kunstgaleries en ateliers waar je originele werken kunt kopen. Een uniek aandenken aan jullie trip.</p>
        <a href="https://maps.google.com/?q=Ludwig+Forum+Aachen" target="_blank" class="maps-link">📍 Omgeving Ludwig Forum</a>
      </div>
    </div>
  </div>

  <!-- GEZELLIGE STRAATJES -->
  <div class="section">
    <div class="section-label">Sfeer & Architectuur</div>
    <div class="section-title">🏘️ Verborgen <em>pareltjes & straatjes</em></div>

    <div class="cards-grid">
      <div class="card">
        <div class="card-accent accent-amber"></div>
        <span class="card-emoji">🗿</span>
        <h3>Hühnermarkt & Fischmarkt</h3>
        <p>Twee van de gezelligste pleintjes van de Altstadt. Omgeven door vakwerkhuizen, terrasjes en een tijdloze sfeer. Perfect voor foto's en een wandeling door de oudste hoek van de stad.</p>
        <a href="https://maps.google.com/?q=Hühnermarkt+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-rose"></div>
        <span class="card-emoji">⛪</span>
        <h3>Rund um den Dom – de Domrondgang</h3>
        <p>Een wandeling rondom de magische kathedraal van Karel de Grote. 's Ochtends vroeg, bijna verlaten, is dit een van de mooiste ervaringen die Aachen te bieden heeft.</p>
        <a href="https://maps.google.com/?q=Aachener+Dom" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-green"></div>
        <span class="card-emoji">🌸</span>
        <h3>Burtscheid – het rustige thermal-kwartier</h3>
        <p>Een charmant, minder toeristisch kwartier net buiten het centrum met thermale bronnen, sfeervolle huizen en een bijna dorps gevoel. Aanrader voor een rustige wandeling.</p>
        <a href="https://maps.google.com/?q=Burtscheid+Aachen" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>

      <div class="card">
        <div class="card-accent accent-teal"></div>
        <span class="card-emoji">🏫</span>
        <h3>RWTH Universiteitswijk</h3>
        <p>De prachtige historische universiteitsgebouwen en de levendige studentenwijk eromheen. Cafés, boekenhandels, kleine winkeltjes en een bruisende sfeer het hele jaar door.</p>
        <a href="https://maps.google.com/?q=RWTH+Aachen+Hauptgebäude" target="_blank" class="maps-link">📍 Google Maps</a>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- PROEVEN -->
  <div class="food-strip">
    <div class="section-label" style="margin-bottom: 4px;">Lokale Smaken</div>
    <h3 style="font-family: 'Playfair Display', serif; font-size: 24px; color: #5a3a20; margin-bottom: 8px;">🍽️ Dit moet je proeven in Aachen</h3>
    <p style="font-size: 14px; color: #7a5a38; margin-bottom: 4px;">Aachen heeft een rijke culinaire traditie die je absoluut moet ontdekken.</p>
    <div class="food-items">
      <div class="food-item"><span>🍪</span> Aachener Printen</div>
      <div class="food-item"><span>🥨</span> Brezel met mosterd</div>
      <div class="food-item"><span>🍺</span> Lokaal Kölsch-stijl bier</div>
      <div class="food-item"><span>🥩</span> Sauerbraten</div>
      <div class="food-item"><span>🍰</span> Pflaumenkuchen</div>
      <div class="food-item"><span>☕</span> Verlängerter koffie</div>
      <div class="food-item"><span>🧀</span> Rheinischer Käse</div>
      <div class="food-item"><span>🥜</span> Lebkuchen met chocolade</div>
    </div>
  </div>

  <!-- FOTO PLEKKEN -->
  <div class="section">
    <div class="section-label">Fotomomenten</div>
    <div class="section-title">📸 De mooiste <em>fotoplekken</em></div>
    <div class="foto-list">
      <div class="foto-item">
        <strong>🏛️ Aachener Dom bij gouden uurtje</strong>
        <span>Fotogeniek van alle kanten — probeer een hoekperspectieffoto vanuit de Münsterplatz</span>
      </div>
      <div class="foto-item">
        <strong>🌿 Karlsgarten muuromgeving</strong>
        <span>De middeleeuwse muren met klimop en bloemen — tijdloos romantisch</span>
      </div>
      <div class="foto-item">
        <strong>📚 In de Mayersche Buchhandlung</strong>
        <span>Boekenwanden, leeslampjes, boekenliefhebbers-sfeer — perfect voor een cozy shot</span>
      </div>
      <div class="foto-item">
        <strong>🦁 Euregiozoo dierenportretten</strong>
        <span>Sluit dichtbij voor expressieve dierenportretten — gebruik een portretmodus</span>
      </div>
      <div class="foto-item">
        <strong>🌅 Pontstraße 's avonds</strong>
        <span>De terrasverlichting 's avonds — sfeervolle bokeh-foto's gegarandeerd</span>
      </div>
      <div class="foto-item">
        <strong>🌲 Aachener Wald mistige ochtend</strong>
        <span>Bij mist of vroeg in de ochtend wordt dit bos een sprookjeslandschap</span>
      </div>
      <div class="foto-item">
        <strong>🕹️ 1Up Store retro-wall</strong>
        <span>De kleurrijke muren vol game-nostalgie maken geweldige achtergronden</span>
      </div>
      <div class="foto-item">
        <strong>🌸 Elisengarten lentebloesem</strong>
        <span>In mei staat de tuin op z'n mooiste — romantische portretomgeving</span>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- REGENWEER -->
  <div class="section" style="padding-bottom: 0;">
    <div class="section-label">Plan B</div>
    <div class="section-title">🌧️ Regenweer-<em>alternatieven</em></div>
    <div class="rain-section">
      <h4>🏠 Binnen is ook prachtig</h4>
      <div class="tips-grid">
        <div class="tip-box">
          <h4>📚 Boeken & spellen</h4>
          <ul>
            <li>Uren slenteren bij Mayersche</li>
            <li>Schmetz am Dom verkennen</li>
            <li>White Rabbit Game Store</li>
            <li>1Up Store retro games</li>
          </ul>
        </div>
        <div class="tip-box">
          <h4>🏛️ Musea</h4>
          <ul>
            <li>Ludwig Forum (grote collectie)</li>
            <li>Domschatzkammer</li>
            <li>Couven Museum</li>
            <li>Dom-bezoek zelf</li>
          </ul>
        </div>
        <div class="tip-box">
          <h4>☕ Regen & koffie</h4>
          <ul>
            <li>Leni loves coffee (ideaal!)</li>
            <li>Café Juli met taart</li>
            <li>Willekeurig Grand Café</li>
            <li>Boekcafé combinatie</li>
          </ul>
        </div>
        <div class="tip-box">
          <h4>🛍️ Indoor shoppen</h4>
          <ul>
            <li>Adalbertstraße winkelstraat</li>
            <li>Kleinere concept stores</li>
            <li>Antiquarische boeken</li>
            <li>Ludwig Forum shop</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- PRAKTISCHE TIPS -->
  <div class="section" style="padding-bottom: 48px;">
    <div class="section-label">Handige Tips</div>
    <div class="section-title">💡 <em>Lokale</em> insider tips</div>
    <div class="tips-grid">
      <div class="tip-box">
        <h4>🚶 Verplaatsen</h4>
        <ul>
          <li>Centrum is zeer voetgangersvriendelijk</li>
          <li>Parking aan de rand + te voet</li>
          <li>Bus en e-step in de stad beschikbaar</li>
          <li>Drielandenpunt = 20 min rijden</li>
        </ul>
      </div>
      <div class="tip-box">
        <h4>🕐 Timing</h4>
        <ul>
          <li>Musea gesloten op maandag</li>
          <li>Dom's ochtends rustigst</li>
          <li>Markt actief op vrijdag & zaterdag</li>
          <li>Pontstraße levendig vanaf 19u</li>
        </ul>
      </div>
      <div class="tip-box">
        <h4>💶 Budget</h4>
        <ul>
          <li>Wildpark Aachen: gratis</li>
          <li>Dom-bezoek: gratis</li>
          <li>Botanische tuin: goedkoop</li>
          <li>Aachen Card voor kortingen</li>
        </ul>
      </div>
      <div class="tip-box">
        <h4>🗣️ Lokale tips</h4>
        <ul>
          <li>Vraag naar "Verborgene Aachen"</li>
          <li>Lokale Aachener Zeitung: agenda</li>
          <li>Bezoek niet alleen de Dom-zone</li>
          <li>Burtscheid is zeer ondergewaardeerd</li>
        </ul>
      </div>
    </div>
  </div>

</div>

<!-- FOOTER / SLOGAN -->
<div class="footer">
  <div class="slogan">"Twee harten, één stad,<br>oneindig veel verhalen om mee naar huis te nemen."</div>
  <p>Aachen wacht op jullie. Met zijn eeuwenoude straatjes, de geur van versgemalen koffie, stapels boeken in sfeervolle winkels en de perfecte mix van natuur en cultuur, is dit het ideale weekend voor twee mensen die van mooie dingen houden. Pak jullie rugzak, zet de GPS op Aachen, en ontdek samen een van de verborgen juwelen van Europa.</p>
  <p style="margin-top: 16px; opacity: 0.7; font-size: 13px;">15 – 17 mei &nbsp;·&nbsp; Voor 2 personen &nbsp;·&nbsp;</p>
  <div class="footer-hearts">📚 🌿 🎲</div>
</div>

</body>
</html>
