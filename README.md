<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Daytrading Crashkurs – Lernhandbuch (mit Baby Steps & Pattern-Schule)</title>
<meta name="description" content="Praxisnaher Daytrading-Crashkurs: Basis, Setups, Risiko, Psychologie, Backtesting, KPIs. Mit Baby Steps pro Kapitel, Pattern-Schule & Drills." />
<style>
  :root{
    --bg:#0f172a; --panel:#111827; --muted:#94a3b8; --text:#e5e7eb;
    --accent:#22d3ee; --accent-2:#60a5fa; --ok:#22c55e; --warn:#f59e0b; --bad:#ef4444;
    --border:#1f2937; --chip:#0b1223;
  }
  *{box-sizing:border-box}
  html,body{height:100%}
  body{
    margin:0;
    font:16px/1.55 system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,"Helvetica Neue",Arial;
    color:var(--text);
    background:
      radial-gradient(1200px 800px at 80% -100px, rgba(34,211,238,.07), transparent 60%),
      radial-gradient(1200px 800px at -40% 0px, rgba(96,165,250,.06), transparent 60%),
      var(--bg);
  }
  a{color:var(--accent)}
  header{position:sticky; top:0; z-index:10; background:linear-gradient(to bottom, rgba(15,23,42,.95), rgba(15,23,42,.7)); backdrop-filter: blur(6px); border-bottom:1px solid var(--border);}
  .wrap{max-width:1100px;margin:0 auto;padding:16px 20px}
  .title{display:flex;gap:12px;align-items:center;flex-wrap:wrap}
  .title h1{font-size:clamp(20px,3vw,30px);margin:.2rem 0}
  .live{font-size:12px;background:#083344;color:#a5f3fc;border:1px solid #155e75;padding:3px 8px;border-radius:999px;display:inline-flex;gap:6px;align-items:center}
  .dot{width:8px;height:8px;border-radius:50%;background:#34d399;animation:pulse 2s infinite}
  @keyframes pulse{50%{opacity:.45}}
  main{display:grid;grid-template-columns:260px 1fr;gap:24px}
  nav{position:sticky; top:76px; height:calc(100vh - 88px); overflow:auto; padding-right:6px}
  .toc{background:rgba(17,24,39,.6); border:1px solid var(--border); border-radius:12px; padding:14px}
  .toc h3{margin:.2rem 0 .6rem; font-size:14px; color:var(--muted)}
  .toc a{display:block; padding:6px 8px; color:#cbd5e1; border-radius:8px; text-decoration:none; font-size:14px}
  .toc a:hover{background:#0b1223}
  .toc .sub{padding-left:12px; font-size:13px}
  section{background:rgba(17,24,39,.6); border:1px solid var(--border); border-radius:16px; padding:18px 18px 10px; margin:18px 0}
  h2{margin:.2rem 0 .2rem; font-size:22px}
  h3{margin:1rem 0 .4rem; font-size:17px}
  p{color:#e2e8f0}
  .chips{display:flex;flex-wrap:wrap;gap:8px;margin:.25rem 0 .75rem}
  .chip{background:var(--chip); border:1px solid var(--border); color:#cbd5e1; font-size:12px; padding:4px 8px; border-radius:999px}
  .note{color:var(--muted); font-size:14px}
  .grid{display:grid; gap:14px}
  .g2{grid-template-columns:repeat(2,1fr)}
  .g3{grid-template-columns:repeat(3,1fr)}
  @media (max-width:900px){ main{grid-template-columns:1fr} nav{position:static; height:auto} .g2,.g3{grid-template-columns:1fr} }
  .panel{background:rgba(2,6,23,.45); border:1px solid var(--border); border-radius:12px; padding:12px}
  .kbd{background:#0b1223;border:1px solid var(--border);padding:2px 6px;border-radius:6px;font-size:12px}
  .tasklist{list-style:none;padding:0;margin:.2rem 0 .8rem}
  .tasklist li{display:flex;gap:10px;align-items:flex-start;margin:.4rem 0}
  .tasklist input{accent-color:var(--accent)}
  .badge{display:inline-block;border:1px solid var(--border); border-radius:6px; padding:2px 6px; font-size:12px; background:#0b1223; color:#cbd5e1}
  .callout{border-left:3px solid var(--accent); background:rgba(34,211,238,.08); padding:10px 12px; border-radius:10px; color:#dbeafe}
  .warn{border-left-color:var(--warn); background:rgba(245,158,11,.07)}
  .ok{border-left-color:var(--ok); background:rgba(34,197,94,.07)}
  .bad{border-left-color:var(--bad); background:rgba(239,68,68,.07)}
  code, pre{font-family: ui-monospace,SFMono-Regular,Menlo,Consolas,monospace}
  pre{background:#0b1223;border:1px solid var(--border);border-radius:10px;padding:10px;overflow:auto}
  textarea, input[type="number"],input[type="text"]{
    width:100%; background:#0b1223; border:1px solid var(--border); color:#e5e7eb;
    padding:8px 10px; border-radius:8px; outline:none
  }
  .btn{display:inline-flex; align-items:center; gap:8px; background:#0b1223; border:1px solid var(--border); color:#e5e7eb; padding:8px 12px; border-radius:10px; cursor:pointer}
  .btn:hover{background:#0f172a}
  .btn.primary{border-color:#155e75;background:#083344}
  .footer{color:var(--muted); font-size:13px; text-align:center; margin:24px 0}
  .right{float:right}
  .flex{display:flex; gap:10px; align-items:center; flex-wrap:wrap}
  .hide-print{ @media print { display:none } }
  @media print{
    header{position:static}
    a:link:after{content:" (" attr(href) ")"; font-size:10px}
    .btn{display:none}
    body{background:white}
    section{break-inside:avoid}
  }
  .switch{position:relative;width:44px;height:24px;background:#0b1223;border:1px solid var(--border);border-radius:999px;cursor:pointer}
  .switch i{position:absolute;top:2px;left:2px;width:20px;height:20px;border-radius:50%;background:#94a3b8;transition:all .2s}
  .switch.active{background:#083344;border-color:#155e75}
  .switch.active i{left:22px;background:#67e8f9}
  details{border:1px dashed var(--border); border-radius:10px; padding:10px; background:rgba(2,6,23,.35); margin:.6rem 0}
  details > summary{cursor:pointer; color:#cbd5e1}
</style>
</head>
<body>
<header>
  <div class="wrap">
    <div class="title">
      <h1><span style="background:linear-gradient(90deg,var(--accent),var(--accent-2));-webkit-background-clip:text;color:transparent">Daytrading Crashkurs</span> · Lernhandbuch</h1>
      <span class="live"><span class="dot"></span> LERNMODUS</span>
      <span class="badge">Paper-Trading zuerst • Keine Finanzberatung</span>
      <span class="right flex hide-print">
        <button id="printBtn" class="btn">🖨️ Drucken/Export</button>
        <span class="btn" id="resetBtn">♻️ Fortschritt zurücksetzen</span>
        <span class="switch" id="darkSwitch" title="Dark/Light"><i></i></span>
      </span>
    </div>
  </div>
</header>

<div class="wrap">
  <main>
    <!-- TOC -->
    <nav>
      <div class="toc">
        <h3>Inhalt</h3>
        <a href="#kap1">1. Basis & Setup</a>
        <a href="#kap2">2. Marktmechanik & Ordertypen</a>
        <a href="#kap3">3. Plattform & Workflow</a>
        <a href="#kap4">4. Risiko- & Money-Management</a>
        <a class="sub" href="#tools">• Rechner & Tools</a>
        <a href="#kap5">5. Zeiten, Volatilität & News</a>
        <a href="#kap6">6. Setup I: Breakouts (ORB)</a>
        <a href="#kap7">7. Setup II: Mean Reversion (VWAP)</a>
        <a href="#patterns">8½. Pattern-Schule & Handelslernen</a>
        <a href="#kap8">8. News/Katalysatoren</a>
        <a href="#kap9">9. Psychologie & Disziplin</a>
        <a href="#kap10">10. Backtesting & Daten</a>
        <a href="#kap11">11. Trading-Plan & Journal</a>
        <a href="#kap12">12. KPIs, Review & Skalierung</a>
        <a href="#tipps">Tipps & Tricks</a>
        <a href="#checklisten">Checklisten</a>
        <a href="#lernplan">14-Tage Lernplan</a>
        <a href="#haftung">Hinweise & Haftung</a>
      </div>
    </nav>

    <!-- Content -->
    <div>

      <!-- Kapitel 1 -->
      <section id="kap1">
        <h2>1) Basis & Setup</h2>
        <div class="chips">
          <span class="chip">Paper-Trading</span>
          <span class="chip">Realtime-Charts</span>
          <span class="chip">Prozessorientierung</span>
        </div>
        <p><strong>Ziel:</strong> Grundverständnis, Werkzeuge, sichere Übungsumgebung.</p>
        <div class="grid g2">
          <div class="panel">
            <h3>Kernpunkte</h3>
            <ul>
              <li><b>Broker/Simulator:</b> Ausführung, Gebühren, Stabilität; PDT/Margin-Regeln beachten.</li>
              <li><b>Daten & Charts:</b> 1-/3-/5-Min-Charts; Level 2/DOM optional.</li>
              <li><b>Paper-First:</b> Zuerst üben, dann klein live. Wahrscheinlichkeiten statt Sicherheiten.</li>
            </ul>
          </div>
          <div class="panel">
            <h3>Mini-Aufgaben</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="t1-1"> <label for="t1-1">Eröffne ein <b>Paper-Trading-Konto</b>.</label></li>
              <li><input type="checkbox" id="t1-2"> <label for="t1-2">Erstelle ein <b>1-Monitor-Layout</b>: Watchlist, Chart, Order-Ticket.</label></li>
              <li><input type="checkbox" id="t1-3"> <label for="t1-3">Definiere deine <b>Nische</b> (z. B. „US-Aktien Momentum, 15:30–17:00“).</label></li>
            </ul>
          </div>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b1-1"><label for="b1-1">Installiere/öffne deine Plattform & aktiviere <b>Paper/Sim</b>.</label></li>
            <li><input type="checkbox" id="b1-2"><label for="b1-2">Erstelle Watchlist mit 5 liquiden Tickern (z. B. SPY, AAPL, MSFT, NVDA, BTC-USD).</label></li>
            <li><input type="checkbox" id="b1-3"><label for="b1-3">Lege <b>Hotkeys</b> an: Buy, Sell, Stop @Last, Flatten.</label></li>
            <li><input type="checkbox" id="b1-4"><label for="b1-4">Stelle 1-Min & 5-Min Charts nebeneinander – gleiche Farbvorlage.</label></li>
            <li><input type="checkbox" id="b1-5"><label for="b1-5">Dokument: „Warum ich handle“ (5 Sätze) + Tageszeitfenster.</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 2 -->
      <section id="kap2">
        <h2>2) Marktmechanik & Ordertypen</h2>
        <div class="grid g2">
          <div class="panel">
            <h3>Was steuert Preis & Ausführung?</h3>
            <ul>
              <li><b>Bid/Ask/Spread:</b> Kauf zum Ask, Verkauf zum Bid. Enge Spreads = weniger Reibung.</li>
              <li><b>Ordertypen:</b> Market, Limit, Stop Market, Stop Limit (Limits können aussetzen).</li>
              <li><b>Liquidität & Gaps:</b> Dünne Bücher ⇒ Slippage, riskanter Exit.</li>
            </ul>
          </div>
          <div class="panel">
            <h3>Mini-Aufgaben</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="t2-1"><label for="t2-1">Erkläre <b>Spread</b> & <b>Slippage</b> in 3 Sätzen.</label></li>
              <li><input type="checkbox" id="t2-2"><label for="t2-2">Simuliere eine <b>Stop-Market</b>-Order unter dem Kerzentief.</label></li>
              <li><input type="checkbox" id="t2-3"><label for="t2-3">Finde eine <b>Limit-Wand</b> im Orderbuch und beobachte den Preis.</label></li>
            </ul>
          </div>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b2-1"><label for="b2-1">Platziere nacheinander 1 <b>Limit</b>-, 1 <b>Market</b>- und 1 <b>Stop</b>-Order im Simulator.</label></li>
            <li><input type="checkbox" id="b2-2"><label for="b2-2">Miss den Spread in ruhiger & volatiler Phase (notiere Werte).</label></li>
            <li><input type="checkbox" id="b2-3"><label for="b2-3">Übung: „Flat in 1 Sek.“ – Taste für Sofort-Exit trainieren (10×).</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 3 -->
      <section id="kap3">
        <h2>3) Trading-Plattform & Workflow</h2>
        <div class="grid g2">
          <div class="panel">
            <h3>Effizienz</h3>
            <ul>
              <li><b>Hotkeys:</b> Entry, Stop, Flat-All.</li>
              <li><b>Layouts:</b> Pre-Market, Live, Review.</li>
              <li><b>Checklisten:</b> Vor/Während/Nach dem Handel.</li>
            </ul>
          </div>
          <div class="panel">
            <h3>Mini-Aufgaben</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="t3-1"><label for="t3-1">Hotkeys für <b>Buy/Sell/Flatten/Stop</b> anlegen.</label></li>
              <li><input type="checkbox" id="t3-2"><label for="t3-2">1-Min (Entry) + 5-Min (Bias) parallel aufbauen.</label></li>
              <li><input type="checkbox" id="t3-3"><label for="t3-3">Pre-Market-Checkliste (5–7 Punkte) schreiben.</label></li>
            </ul>
          </div>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b3-1"><label for="b3-1">Baue ein <b>Live-Layout</b>: Links Watchlist, Mitte Charts, rechts Order-Ticket.</label></li>
            <li><input type="checkbox" id="b3-2"><label for="b3-2">Lege einen <b>Screenshot-Hotkey</b> für Post-Trade Review an.</label></li>
            <li><input type="checkbox" id="b3-3"><label for="b3-3">Timer: alle 30 Min <b>Micro-Review</b> (3 Stichpunkte).</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 4 -->
      <section id="kap4">
        <h2>4) Risiko- & Money-Management</h2>
        <div class="callout warn"><b>Überleben zuerst:</b> Max. Tagesverlust (z. B. 2–3R) und harte Stops sind Pflicht.</div>
        <div class="grid g2">
          <div class="panel">
            <h3>Kernformeln</h3>
            <ul>
              <li><b>Kontorisiko/Trade:</b> 0,25–1,0 %.</li>
              <li><b>Positionsgröße</b> = Euro-Risiko / (Entry − Stop).</li>
              <li><b>R-Multiple:</b> Ergebnis relativ zum Risiko.</li>
              <li><b>Expectancy</b>: E = W·ØGewinn − (1−W)·ØVerlust (in R).</li>
            </ul>
            <p class="note">Beispiel: Konto €5.000, 0,5 % (=€25). Entry 50,20, Stop 49,80 → Risiko €0,40/Aktie → Größe 62.</p>
          </div>
          <div class="panel">
            <h3>Mini-Aufgaben</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="t4-1"><label for="t4-1">Berechne 3 Größen mit Stops 0,12/0,30/0,55 € bei €25 Risiko.</label></li>
              <li><input type="checkbox" id="t4-2"><label for="t4-2">Definiere deine <b>Risikoklasse</b> (0,25 %, 0,5 %, 1,0 %).</label></li>
              <li><input type="checkbox" id="t4-3"><label for="t4-3">Schreibe deine <b>Daily-Stop-Rules</b>.</label></li>
            </ul>
          </div>
        </div>
        <div id="tools" class="panel">
          <h3>📐 Tools: Positionsgröße, Expectancy & Tagesstop</h3>
          <div class="grid g3">
            <div>
              <div class="badge">Positionsgröße</div>
              <label>Kontogröße (€)<input type="number" id="acct" value="5000" min="0"></label>
              <label>Risiko % pro Trade<input type="number" id="riskp" value="0.5" step="0.05" min="0"></label>
              <label>Entry-Preis<input type="number" id="entry" value="50.2" step="0.01"></label>
              <label>Stop-Preis<input type="number" id="stop" value="49.8" step="0.01"></label>
              <p class="note">Euro-Risiko: <b id="risk€">–</b> • Größe: <b id="size">–</b></p>
            </div>
            <div>
              <div class="badge">Expectancy</div>
              <label>Trefferquote W %<input type="number" id="win" value="45" step="1" min="0" max="100"></label>
              <label>Ø Gewinn (R)<input type="number" id="avgw" value="1.6" step="0.1"></label>
              <label>Ø Verlust (R)<input type="number" id="avgl" value="1.0" step="0.1"></label>
              <p class="note">E = <b id="exp">–</b> (R/Trade)</p>
            </div>
            <div>
              <div class="badge">Tagesstop</div>
              <label>R pro Trade (€)<input type="number" id="r-eur" value="25" step="1"></label>
              <label>Max R/Tag<input type="number" id="r-day" value="2" step="0.5"></label>
              <p class="note">Tagesverlust-Limit: <b id="day€">–</b></p>
            </div>
          </div>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b4-1"><label for="b4-1">Wähle <b>ein fixes R</b> (€-Betrag) pro Trade (z. B. €25).</label></li>
            <li><input type="checkbox" id="b4-2"><label for="b4-2">Setze <b>Tagesstop</b> (z. B. 2R) in der Plattform (Alarm/Auto-Flat).</label></li>
            <li><input type="checkbox" id="b4-3"><label for="b4-3">Trainiere Größenkalkulation (10 Beispiele, laut sprechen).</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 5 -->
      <section id="kap5">
        <h2>5) Handelszeiten, Volatilität & News</h2>
        <div class="grid g2">
          <div class="panel">
            <h3>Wann handeln?</h3>
            <ul>
              <li><b>US-Open:</b> Eröffnung (ca. 15:30 Berlin) – 60–90 Min am volatilsten.</li>
              <li><b>RVOL & ATR:</b> Qualitätsfilter für Bewegungen.</li>
              <li><b>News:</b> Spikes; bewusst handeln oder meiden.</li>
            </ul>
          </div>
          <div class="panel">
            <h3>Mini-Aufgaben</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="t5-1"><label for="t5-1">Finde 5 Ticker mit <b>RVOL &gt; 2</b>.</label></li>
              <li><input type="checkbox" id="t5-2"><label for="t5-2">Markiere die <b>Opening Range</b> im 1-/5-Min Chart.</label></li>
              <li><input type="checkbox" id="t5-3"><label for="t5-3">Logge 3 News-Events + erste Reaktion.</label></li>
            </ul>
          </div>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b5-1"><label for="b5-1">Definiere <b>Handelsfenster</b> (z. B. 15:30–17:00).</label></li>
            <li><input type="checkbox" id="b5-2"><label for="b5-2">Erstelle RVOL-Spalte in Watchlist (Filter &gt; 1,5).</label></li>
            <li><input type="checkbox" id="b5-3"><label for="b5-3">Kalender: trage wichtige <b>Makrozeiten</b> (CPI, FOMC) ein.</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 6 -->
      <section id="kap6">
        <h2>6) Setups I: Breakouts (Trend-Fortsetzung)</h2>
        <div class="panel">
          <h3>Opening-Range-Breakout (ORB) – Regeln</h3>
          <ul>
            <li><b>Bias:</b> 5/15-Min Trend up, Pre-Market-High nahe.</li>
            <li><b>Trigger:</b> Long bei Break über Hoch der ersten 5-Min Kerze/Range.</li>
            <li><b>Stop:</b> Unter Range-Tief oder letztem Pullback-Tief.</li>
            <li><b>Teilgewinn:</b> +1R; Rest <i>trailen</i>.</li>
            <li><b>Ungültig:</b> Starke Rejektion an VWAP, breiter Spread, News-Halt.</li>
          </ul>
        </div>
        <h3>Mini-Aufgaben</h3>
        <ul class="tasklist">
          <li><input type="checkbox" id="t6-1"><label for="t6-1">Backteste 20 ORBs (Replay). Logge Entry/Stop/R.</label></li>
          <li><input type="checkbox" id="t6-2"><label for="t6-2">Sammle 3 Fakeouts & gemeinsame Merkmale.</label></li>
          <li><input type="checkbox" id="t6-3"><label for="t6-3">Formuliere deine ORB-Checkliste (≤ 8 Zeilen).</label></li>
        </ul>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b6-1"><label for="b6-1"><b>Zeichne</b> die erste 5-Min Range auf 10 Charts.</label></li>
            <li><input type="checkbox" id="b6-2"><label for="b6-2">Definiere <b>genauen Entry</b> (z. B. +0,02 über Range-High) & <b>Stop</b>.</label></li>
            <li><input type="checkbox" id="b6-3"><label for="b6-3">Übe 10× Entry-Hotkey + Stop-Setzen im Replay.</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 7 -->
      <section id="kap7">
        <h2>7) Setups II: Mean Reversion (Rücklauf zu VWAP)</h2>
        <div class="panel">
          <h3>VWAP-Pullback – Regeln</h3>
          <ul>
            <li><b>Bias:</b> Überdehnter Move weg vom VWAP (&gt; ca. 2× ATR 1-Min).</li>
            <li><b>Trigger:</b> Reversal-Kerze + fallendes Volumen, Entry Richtung VWAP.</li>
            <li><b>Stop:</b> Über/unter Extremkerze.</li>
            <li><b>Ziele:</b> Teilgewinn am VWAP, Rest trailen.</li>
            <li><b>No-Trade:</b> Chop direkt am VWAP ohne Trend.</li>
          </ul>
        </div>
        <h3>Mini-Aufgaben</h3>
        <ul class="tasklist">
          <li><input type="checkbox" id="t7-1"><label for="t7-1">Markiere 10 VWAP-Fades + Distanz zum VWAP beim Entry.</label></li>
          <li><input type="checkbox" id="t7-2"><label for="t7-2">Definiere No-Trade-Zonen textlich.</label></li>
          <li><input type="checkbox" id="t7-3"><label for="t7-3">Übe konsequent mit <b>Hard-Stops</b>.</label></li>
        </ul>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b7-1"><label for="b7-1">Aktiviere VWAP-Indikator & markiere Überdehnung (Prozent).</label></li>
            <li><input type="checkbox" id="b7-2"><label for="b7-2">Definiere Reversal-Signal (z. B. Hammer + Volumen-Abnahme).</label></li>
            <li><input type="checkbox" id="b7-3"><label for="b7-3">Replay: 10 Trades nur bis <b>VWAP</b> skalieren (Teilgewinn).</label></li>
          </ul>
        </details>
      </section>

      <!-- Pattern-Schule -->
      <section id="patterns">
        <h2>8½) Pattern-Schule & Handelslernen</h2>
        <div class="grid g2">
          <div class="panel">
            <h3>Core-Bibliothek (Kontext + Trigger)</h3>
            <ul>
              <li><b>Flag / Pennant (Trend-Fortsetzung):</b> Starker Impuls, kurze Konsolidierung; Entry Break aus der Flag, Stop unter Flag-Low.</li>
              <li><b>ABCD / Pullback:</b> A→B Impuls, B→C Rücklauf (flach), Entry C→D bei HH über B; Stop unter C.</li>
              <li><b>Doppelboden / Doppeltop:</b> Zweites Tief/Hoch mit abnehmendem Volumen; Entry Break der Zwischenlinie (Neckline).</li>
              <li><b>Range-Breakout:</b> Mehrfache Tests eines Levels; Entry über/unter Range, Stop innerhalb Range.</li>
              <li><b>Candles:</b> Engulfing, Hammer, Shooting Star <i>nur im passenden Kontext</i> (Trend/VWAP/Level).</li>
            </ul>
          </div>
          <div class="panel">
            <h3>So lernst du Pattern richtig</h3>
            <ol>
              <li><b>Wähle 2 Pattern</b> (z. B. Flag & ABCD) – maximal!</li>
              <li><b>Regel-Karte</b> schreiben: Kontext (Trend, VWAP, RVOL), Entry-Trigger, Invalidation, Stop, Teilgewinn/Trail.</li>
              <li><b>20 Screenshots</b> je Pattern (gute & schlechte Beispiele) – markiere Entry/Stop/Level.</li>
              <li><b>Replay-Drill:</b> 20 Trades je Pattern, strikt Regeln befolgen. Logge R, MAE, MFE.</li>
              <li><b>Review:</b> „Was war gleich?“ → verdichte zu 5 Bullet-Regeln.</li>
              <li><b>Go/No-Go-Kriterien</b>: Erst live (klein), wenn W% &gt; 45 % <i>oder</i> E &gt; 0 über ≥ 40 Trades.</li>
            </ol>
          </div>
        </div>
        <div class="panel">
          <h3>Drills (Handwerk & Motorik)</h3>
          <ul class="tasklist">
            <li><input type="checkbox" id="pd-1"><label for="pd-1"><b>Hotkey-Muscle-Memory</b>: 20× Buy-Stop-Flat im Replay (ohne zu schauen).</label></li>
            <li><input type="checkbox" id="pd-2"><label for="pd-2"><b>Entry-Simulator</b>: Nur Entry setzen, sofort abbrechen – 15 Minuten.</label></li>
            <li><input type="checkbox" id="pd-3"><label for="pd-3"><b>Level-Marking</b>: Zeichne 10× Range + Break-Level (HH/HL/LL/LH benennen).</label></li>
            <li><input type="checkbox" id="pd-4"><label for="pd-4"><b>Screenshot-Review</b>: 10 Bilder, Fehler rot, korrekte Regeln grün.</label></li>
          </ul>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="bp-1"><label for="bp-1">Wähle <b>genau 2 Pattern</b> (Flag & ABCD empfohlen) für 2 Wochen.</label></li>
            <li><input type="checkbox" id="bp-2"><label for="bp-2">Erstelle 2 <b>Regel-Karten</b> (je 1 Screenshot + 5 Regeln).</label></li>
            <li><input type="checkbox" id="bp-3"><label for="bp-3">Sammle 40 Screenshots (20/Pattern), markiere Entry/Stop.</label></li>
            <li><input type="checkbox" id="bp-4"><label for="bp-4">Mache 40 Replay-Trades (20/Pattern) & berechne W % & E.</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 8 -->
      <section id="kap8">
        <h2>8) News- & Katalysator-Trading</h2>
        <div class="grid g2">
          <div class="panel">
            <h3>Playbooks</h3>
            <ul>
              <li><b>Gap-&-Go:</b> Hohe RVOL, frisches High, früher Teilgewinn.</li>
              <li><b>Halt-Resume:</b> Nach Trading-Halt kleine Size, klare Regeln.</li>
              <li><b>Risiko:</b> Gaps, Slippage, erneute News → Size runter.</li>
            </ul>
          </div>
          <div class="panel">
            <h3>Mini-Aufgaben</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="t8-1"><label for="t8-1">Klassifiziere 5 Replay-Newsfälle (Gap-&-Go/Trend/Reversal).</label></li>
              <li><input type="checkbox" id="t8-2"><label for="t8-2">Schreibe ein <b>News-Playbook</b> (Entry, Invalidierung, Exit, Size).</label></li>
              <li><input type="checkbox" id="t8-3"><label for="t8-3">Setze eine <b>Slippage-Annahme</b> (z. B. +0,05 €) im Risk-Modell.</label></li>
            </ul>
          </div>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b8-1"><label for="b8-1">Erstelle <b>News-Watch</b> (Earnings-Kalender, Makro-Termine).</label></li>
            <li><input type="checkbox" id="b8-2"><label for="b8-2">Definiere: handle ich News aktiv oder meide ich sie? (Schriftlich)</label></li>
            <li><input type="checkbox" id="b8-3"><label for="b8-3">Replay: 10 News-Bewegungen nur <b>beobachten</b>, keine Trades.</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 9 -->
      <section id="kap9">
        <h2>9) Psychologie, Disziplin & Fehlervermeidung</h2>
        <div class="callout bad"><b>Häufige Fehler:</b> Revenge-Trading, Overtrading, Stops verschieben, FOMO, zu große Size.</div>
        <div class="panel">
          <h3>Gegenmittel</h3>
          <ul>
            <li><b>If-Then:</b> „Wenn 3 Verluste → 20 Min Pause & Review.“</li>
            <li><b>Handelsfenster:</b> Feste Zeiten; außerhalb: kein Trading.</li>
            <li><b>Atemanker:</b> 90 Sek Pause vor jeder Order; Outcome-Detachment.</li>
          </ul>
          <h3>Mini-Aufgaben</h3>
          <ul class="tasklist">
            <li><input type="checkbox" id="t9-1"><label for="t9-1">Top-3 Fehler + If-Then-Gegenregeln notieren.</label></li>
            <li><input type="checkbox" id="t9-2"><label for="t9-2">1 Woche <b>Emotions-Score</b> (1–5) je Trade führen.</label></li>
            <li><input type="checkbox" id="t9-3"><label for="t9-3"><b>Max-Trades/Tag</b> festlegen.</label></li>
          </ul>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b9-1"><label for="b9-1">Setze Handy-Timer für <b>90-Sek Atempause</b> vor Orders.</label></li>
            <li><input type="checkbox" id="b9-2"><label for="b9-2">Formuliere 3 <b>Wenn-Dann</b>-Sätze und hänge sie an den Monitor.</label></li>
            <li><input type="checkbox" id="b9-3"><label for="b9-3">Tracke 10 Trades mit Emotions-Score & Regel-Compliance.</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 10 -->
      <section id="kap10">
        <h2>10) Backtesting & Datenerhebung</h2>
        <div class="grid g2">
          <div class="panel">
            <h3>Was tracken?</h3>
            <p>Pro Setup: Datum/Zeit, Ticker, Setup, Entry, Stop, Target, Größe, R, MAE, MFE, Halted?, Spread, RVOL, News-Flag.</p>
            <p><b>Schnellstart:</b> Manual-Replay (1-Min), 50–100 Fälle je Setup → W %, Avg Win/Loss (R), Expectancy, Profit-Factor.</p>
          </div>
          <div class="panel">
            <h3>Mini-Aufgaben</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="t10-1"><label for="t10-1">Backteste 30 Trades eines Setups & berechne W % & E.</label></li>
              <li><input type="checkbox" id="t10-2"><label for="t10-2">Erstelle ein Histogramm der R-Ergebnisse.</label></li>
              <li><input type="checkbox" id="t10-3"><label for="t10-3">Definiere Ausschlusskriterien (Spread, RVOL, Zeitfenster).</label></li>
            </ul>
          </div>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b10-1"><label for="b10-1">Baue ein <b>Google-Sheet/Excel-Journal</b> mit obigem Header.</label></li>
            <li><input type="checkbox" id="b10-2"><label for="b10-2">Fülle 10 Trades aus Replay – ohne Ausnahmen/Regelbrüche.</label></li>
            <li><input type="checkbox" id="b10-3"><label for="b10-3">Rechne W %, Avg Win/Loss, E, Profit-Factor (Formeln im Sheet).</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 11 -->
      <section id="kap11">
        <h2>11) Trading-Plan & Journal</h2>
        <div class="grid g2">
          <div class="panel">
            <h3>Plan-Template</h3>
            <pre><code>Ziel: Konstanz, Regeln einhalten, Drawdown klein
Märkte: US-Aktien (Large/Mid), optional Krypto
Zeiten: 15:30–17:00 (Berlin), optional 20:00–21:30
Setups: ORB (5-Min), VWAP-Pullback
Risiko: 0,5 % pro Trade; Tagesstop = 2R
Order: Entry Limit, Stop Market, Teilgewinn +1R, Rest trail
No-Trade: Earnings in &lt;10 Min, Spread &gt; 0,10 €, RVOL &lt; 1,5
Review: Täglich 10 Min, Wöchentlich 30 Min (KPIs)
Focus: Fewer better trades; Hotkeys; Pre-Flight
</code></pre>
          </div>
          <div class="panel">
            <h3>Journal-CSV (Header)</h3>
            <pre><code>date,time,ticker,setup,entry,stop,exit,size,R,MAE,MFE,spread,rvol,notes,emotion(1-5)</code></pre>
            <h3>Mini-Aufgaben</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="t11-1"><label for="t11-1">Fülle deinen <b>Trading-Plan</b> (≤ 1 Seite).</label></li>
              <li><input type="checkbox" id="t11-2"><label for="t11-2">Journalisiere 1 Woche Paper-Trading (≥ 10 Trades).</label></li>
              <li><input type="checkbox" id="t11-3"><label for="t11-3">Schreibe je Trade eine 1-Satz-Lektion.</label></li>
            </ul>
          </div>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b11-1"><label for="b11-1">Setze eine <b>Regel-Compliance-Spalte</b> (Ja/Nein) im Journal.</label></li>
            <li><input type="checkbox" id="b11-2"><label for="b11-2">Lege Ordner „Screenshots/Datum“ an und speichere jedes Setup.</label></li>
            <li><input type="checkbox" id="b11-3"><label for="b11-3">Wöchentliche Review-Notiz (max. 10 Zeilen) anlegen.</label></li>
          </ul>
        </details>
      </section>

      <!-- Kapitel 12 -->
      <section id="kap12">
        <h2>12) KPIs, Review & Skalierung</h2>
        <div class="grid g2">
          <div class="panel">
            <h3>Wichtige Kennzahlen</h3>
            <ul>
              <li>W % (Trefferquote), Avg Win/Loss (R), Expectancy E</li>
              <li>Profit-Factor, Max Drawdown, R/Monat, Zeit im Trade</li>
              <li>Slippage/Trade</li>
            </ul>
            <p><b>Interpretation:</b> E &gt; 0 stabil über ≥ 50 Trades → tragfähiges Regelwerk. PF &gt; 1,4 bei DD &lt; 5R → vorsichtig skalieren.</p>
          </div>
          <div class="panel">
            <h3>Mini-Aufgaben</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="t12-1"><label for="t12-1">Berechne W %, Avg Win/Loss, E, Profit-Factor (50 Trades).</label></li>
              <li><input type="checkbox" id="t12-2"><label for="t12-2">Definiere <b>Skalierungsregel</b> (+10 % Size nach 2 grünen Wochen).</label></li>
              <li><input type="checkbox" id="t12-3"><label for="t12-3">Erstelle 1-Seiten-Weekly-Review.</label></li>
            </ul>
          </div>
        </div>
        <details>
          <summary><b>Lernkurs (Baby Steps) – What to do first</b></summary>
          <ul class="tasklist">
            <li><input type="checkbox" id="b12-1"><label for="b12-1">Setze KPI-Dashboard (4 Zahlen): W %, Avg W/L, E, PF.</label></li>
            <li><input type="checkbox" id="b12-2"><label for="b12-2">Grenze für <b>Drawdown-Pause</b> (z. B. −5R) definieren.</label></li>
            <li><input type="checkbox" id="b12-3"><label for="b12-3">Plane dein <b>Next Level</b> (z. B. zweite Uhrzeit oder Ticker).</label></li>
          </ul>
        </details>
      </section>

      <!-- Tipps -->
      <section id="tipps">
        <h2>Tipps & Tricks (kompakt)</h2>
        <div class="panel">
          <ul>
            <li><b>Paper zuerst, klein live später.</b></li>
            <li><b>Ein Setup</b> meistern statt zehn halb.</li>
            <li>Denke in <b>R-Multiples</b>, nicht in Euro.</li>
            <li><b>Hard Stops</b> im System, nie „mental“.</li>
            <li>Fixe <b>Handelsfenster</b>; nach 2–3R Down: Schluss.</li>
            <li>News: bewusst handeln oder meiden – nicht zufällig.</li>
            <li><b>Hotkeys</b> für Entry/Exit/Stop/Flat.</li>
            <li>Spread & RVOL checken – schlechte Bedingungen = <b>kein Trade</b>.</li>
            <li><b>Journaling</b>: kurz, aber immer.</li>
            <li><b>Prozess &gt; Ergebnis</b>: Regel-Compliance messen.</li>
          </ul>
        </div>
      </section>

      <!-- Checklisten -->
      <section id="checklisten">
        <h2>Checklisten</h2>
        <div class="grid g3">
          <div class="panel">
            <h3>Pre-Market (5–7 Punkte)</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="c1"><label for="c1">Daten/Plattform okay (Ping, Feed, Hotkeys)</label></li>
              <li><input type="checkbox" id="c2"><label for="c2">Watchlist (RVOL, Katalysator, Spread)</label></li>
              <li><input type="checkbox" id="c3"><label for="c3">Levels: PM High/Low, Vortag H/L, VWAP</label></li>
              <li><input type="checkbox" id="c4"><label for="c4">Makro-Events/Uhrzeiten notiert</label></li>
              <li><input type="checkbox" id="c5"><label for="c5">Tagesziel & Max-Verlust (R) gesetzt</label></li>
            </ul>
          </div>
          <div class="panel">
            <h3>Vor dem Entry</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="c6"><label for="c6">Setup erfüllt <b>alle</b> Regeln</label></li>
              <li><input type="checkbox" id="c7"><label for="c7">Entry/Stop/Teilgewinn exakt definiert</label></li>
              <li><input type="checkbox" id="c8"><label for="c8">Positionsgröße berechnet</label></li>
              <li><input type="checkbox" id="c9"><label for="c9">News-Risiko in X Min? (oder bewusstes Play)</label></li>
            </ul>
          </div>
          <div class="panel">
            <h3>Nach dem Trade</h3>
            <ul class="tasklist">
              <li><input type="checkbox" id="c10"><label for="c10">Ergebnis in <b>R</b> geloggt</label></li>
              <li><input type="checkbox" id="c11"><label for="c11">1 Satz: „Next time I will…“</label></li>
              <li><input type="checkbox" id="c12"><label for="c12">Screenshot gesichert</label></li>
            </ul>
          </div>
        </div>
      </section>

      <!-- Lernplan -->
      <section id="lernplan">
        <h2>14-Tage Lernplan (60–90 Min/Tag)</h2>
        <div class="panel">
          <ol>
            <li><b>Tag 1–2:</b> Basis, Plattform, Hotkeys; 20 Paper-„Stops setzen“-Übungen.</li>
            <li><b>Tag 3–5:</b> ORB; 30 Backtests; Regeln schreiben.</li>
            <li><b>Tag 6–7:</b> VWAP-Pullback; 30 Backtests; Regeln schreiben.</li>
            <li><b>Tag 8–9:</b> Risiko-Mgmt; Größen live kalkulieren (Paper).</li>
            <li><b>Tag 10:</b> News-Playbooks; 10 Replay-Newsfälle.</li>
            <li><b>Tag 11–12:</b> 10 Paper-Trades live-simuliert; Journal + Review.</li>
            <li><b>Tag 13:</b> KPIs; Schwachstellen; Plan schärfen.</li>
            <li><b>Tag 14:</b> „Mock-Live“ 60 Min, max. 2 Trades, 0,5 % Risiko.</li>
          </ol>
        </div>
      </section>

      <!-- Hinweise -->
      <section id="haftung">
        <h2>Hinweise & Haftung</h2>
        <div class="callout">
          Dieses Material dient ausschließlich Bildungszwecken und stellt <b>keine Finanzberatung</b> dar. Prüfe lokale Vorschriften
          (z. B. PDT-Regeln, Steuern). Nutze nur Kapital, dessen Verlust du verkraften kannst.
        </div>
      </section>

      <div class="footer">© 2025 – Lernhandbuch (Education only). Frei nutzbar in deinem GitHub-Repo.</div>
    </div>
  </main>
</div>

<script>
/* ---------- Theme toggle ---------- */
const sw = document.getElementById('darkSwitch');
sw.addEventListener('click', ()=>{ sw.classList.toggle('active'); document.documentElement.classList.toggle('light'); });
/* Light mode (optional) */
const lightCSS = `
  :root.light{ --bg:#f8fafc; --panel:#ffffff; --text:#0f172a; --muted:#334155; --border:#e2e8f0; --chip:#eef2ff; }
  :root.light body{ background:#f8fafc }
  :root.light .toc a{ color:#334155 }
  :root.light .badge{ background:#eff6ff; color:#1f2937 }
  :root.light .panel{ background:#ffffffc0 }
  :root.light pre{ background:#f1f5f9; color:#0f172a }
  :root.light .callout{ color:#0f172a }
`;
document.head.appendChild(Object.assign(document.createElement('style'),{textContent:lightCSS}));

/* ---------- Print/Export ---------- */
document.getElementById('printBtn').onclick = ()=> window.print();

/* ---------- Persist checkboxes (v2) ---------- */
const STORAGE_KEY = 'dt-crashkurs-v2';
function saveState(){
  const checks = [...document.querySelectorAll('input[type="checkbox"]')].map(x=>({id:x.id,checked:x.checked}));
  localStorage.setItem(STORAGE_KEY, JSON.stringify({checks}));
}
function loadState(){
  try{
    const s = JSON.parse(localStorage.getItem(STORAGE_KEY)||'{}');
    (s.checks||[]).forEach(o=>{ const el = document.getElementById(o.id); if (el) el.checked = !!o.checked; });
  }catch(e){}
}
document.addEventListener('change', (e)=>{ if (e.target.matches('input[type="checkbox"]')) saveState(); });
document.getElementById('resetBtn').onclick = ()=>{ if (confirm('Fortschritt wirklich zurücksetzen?')) { localStorage.removeItem(STORAGE_KEY); location.reload(); } };
loadState();

/* ---------- Calculators ---------- */
function fmt€(x){ return isFinite(x)? new Intl.NumberFormat('de-DE',{style:'currency',currency:'EUR',maximumFractionDigits:2}).format(x):'–' }
function recalcPosition(){
  const acct = parseFloat(document.getElementById('acct').value)||0;
  const riskp= parseFloat(document.getElementById('riskp').value)||0;
  const entry= parseFloat(document.getElementById('entry').value);
  const stop = parseFloat(document.getElementById('stop').value);
  const risk€ = acct * (riskp/100);
  const perShare = Math.max((entry - stop), 0.0000001);
  const size = Math.floor(risk€ / perShare);
  document.getElementById('risk€').textContent = fmt€(risk€);
  document.getElementById('size').textContent  = isFinite(size)? size : '–';
}
['acct','riskp','entry','stop'].forEach(id=> document.getElementById(id).addEventListener('input', recalcPosition));

function recalcExpectancy(){
  const w  = (parseFloat(document.getElementById('win').value)||0)/100;
  const aw = parseFloat(document.getElementById('avgw').value)||0;
  const al = parseFloat(document.getElementById('avgl').value)||0;
  const E = (w*aw) - ((1-w)*al);
  document.getElementById('exp').textContent = (Math.round(E*100)/100).toString();
}
['win','avgw','avgl'].forEach(id=> document.getElementById(id).addEventListener('input', recalcExpectancy));

function recalcDaily(){
  const r€ = parseFloat(document.getElementById('r-eur').value)||0;
  const rD = parseFloat(document.getElementById('r-day').value)||0;
  document.getElementById('day€').textContent = fmt€(r€*rD);
}
['r-eur','r-day'].forEach(id=> document.getElementById(id).addEventListener('input', recalcDaily));

recalcPosition(); recalcExpectancy(); recalcDaily();
</script>
</body>
</html>
