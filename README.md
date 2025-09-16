<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Projeto Basquete — Acessibilidade</title>
  <style>
    :root{
      --base-font: 16px;
      --bg: #0b1220;
      --card: #0f2840;
      --accent: #ff8a00;
      --text: #ffffff;
      --muted: #cfe3ff;
    }
    *{box-sizing:border-box}
    html{font-family:Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial; font-size:var(--base-font)}
    body{margin:0;background:var(--bg);color:var(--text);line-height:1.4}
    .skip-link{position:absolute;left:-999px;top:auto;width:1px;height:1px;overflow:hidden}
    .skip-link:focus{left:1rem;top:1rem;width:auto;height:auto;padding:.5rem 1rem;background:#fff;color:#000;border-radius:4px;z-index:999}
    header{display:flex;align-items:center;justify-content:space-between;padding:1rem 1.5rem;background:linear-gradient(90deg,#071529 0%, #0d1f34 100%);box-shadow:0 4px 18px rgba(0,0,0,.6)}
    .brand{display:flex;gap:.8rem;align-items:center}
    .logo{width:48px;height:48px;border-radius:50%;background:conic-gradient(from 180deg,#ff8a00,#ff3b30);display:flex;align-items:center;justify-content:center;font-weight:700;color:#fff}
    h1{font-size:1.25rem;margin:0}
    nav{display:flex;gap:.5rem}
    main{max-width:1000px;margin:1.25rem auto;padding:1rem}
    .grid{display:grid;grid-template-columns:1fr 320px;gap:1rem}
    @media (max-width:880px){.grid{grid-template-columns:1fr}}
    .card{background:var(--card);padding:1rem;border-radius:12px;box-shadow:0 6px 30px rgba(2,6,23,.6)}
    .a11y{display:flex;flex-direction:column;gap:.75rem}
    .a11y h2{font-size:1rem;margin:0 0 .25rem}
    .controls{display:flex;gap:.5rem;flex-wrap:wrap;align-items:center}
    .btn{background:transparent;border:1px solid rgba(255,255,255,.12);padding:.5rem .75rem;border-radius:8px;color:var(--text);cursor:pointer;transition:background .2s}
    .btn:hover{background:rgba(255,255,255,.1)}
    .btn:focus{outline:3px solid rgba(255,138,0,.45);outline-offset:3px}
    input[type=range]{flex:1}
    .section{margin-bottom:1.5rem}
    .section h3{margin-top:0;color:var(--accent)}
    footer{padding:1rem;text-align:center;color:var(--muted)}
    body.high-contrast{--bg:#000;--card:#fff;--accent:#ff0;--text:#000;--muted:#333}
    body.high-contrast .logo{background:conic-gradient(from 180deg,#ff0,#fff);color:#000}
    body.high-contrast .btn{border-color:#000;color:#000}
    .aria-status{position:fixed;left:-9999px;top:auto;height:1px;width:1px;overflow:hidden}
  </style>
</head>
<body>
  <a class="skip-link" href="#main">Pular para o conteúdo</a>
  <header>
    <div class="brand">
      <div class="logo" aria-hidden="true">BB</div>
      <div>
        <h1>Projeto Basquete</h1>
        <div class="description" style="font-size:.85rem;color:var(--muted)">Tudo sobre o esporte e acessibilidade digital</div>
      </div>
    </div>
    <nav aria-label="Menu principal">
      <button class="btn" id="open-a11y" aria-haspopup="true" aria-controls="a11y-title">Menu de Acessibilidade</button>
    </nav>
  </header>

  <main id="main">
    <div class="grid">
      <section class="card">
        <div class="section">
          <h3>Como funciona o basquete</h3>
          <p>O basquete é um esporte coletivo jogado entre duas equipes de cinco jogadores. O objetivo é marcar pontos arremessando a bola dentro da cesta adversária. Cada partida é dividida em quatro períodos e envolve fundamentos como drible, passe, arremesso e defesa.</p>
        </div>
        <div class="section">
          <h3>Principais campeonatos</h3>
          <ul>
            <li><strong>NBA (EUA):</strong> maior liga profissional do mundo, referência em qualidade técnica e espetáculo.</li>
            <li><strong>NBB (Brasil):</strong> Novo Basquete Brasil, principal campeonato nacional masculino.</li>
            <li><strong>EuroLeague:</strong> competição europeia de alto nível com clubes de diversos países.</li>
            <li><strong>Jogos Olímpicos:</strong> torneio internacional realizado a cada quatro anos, reunindo seleções nacionais.</li>
          </ul>
        </div>
        <div class="section">
          <h3>Melhores jogadores</h3>
          <p>Ao longo da história, vários atletas se destacaram no basquete:</p>
          <ul>
            <li><strong>Michael Jordan:</strong> considerado o maior jogador de todos os tempos, multicampeão pela NBA.</li>
            <li><strong>LeBron James:</strong> ícone da era atual, conhecido por sua versatilidade e longevidade.</li>
            <li><strong>Kobe Bryant:</strong> símbolo de dedicação e técnica refinada, campeão com o Los Angeles Lakers.</li>
            <li><strong>Oscar Schmidt:</strong> brasileiro reconhecido mundialmente por seu talento e poder de pontuação.</li>
            <li><strong>Larry Bird, Magic Johnson, Stephen Curry</strong> e outros também marcaram gerações.</li>
          </ul>
        </div>
      </section>
      <aside class="card" aria-labelledby="a11y-title">
        <h2 id="a11y-title">Menu de Acessibilidade</h2>
        <div class="a11y">
          <p style="margin:0 .0 0.5rem;color:var(--muted);font-size:.95rem">Personalize a interface: tamanho da fonte, contraste e preferências.</p>
          <div>
            <label for="font-size-range">Tamanho da fonte</label>
            <div class="controls" style="margin-top:.5rem">
              <button class="btn" id="decrease-font" aria-label="Diminuir fonte">A-</button>
              <input id="font-size-range" type="range" min="12" max="22" step="1" value="16" aria-valuemin="12" aria-valuemax="22" aria-valuenow="16">
              <button class="btn" id="increase-font" aria-label="Aumentar fonte">A+</button>
            </div>
          </div>
          <div>
            <label for="contrast-toggle">Modo alto contraste</label>
            <div style="margin-top:.5rem" class="controls">
              <button class="btn" id="toggle-contrast" aria-pressed="false">Ativar contraste</button>
            </div>
          </div>
          <div>
            <label for="motion-toggle">Reduzir movimentos</label>
            <div style="margin-top:.5rem" class="controls">
              <button class="btn" id="toggle-motion" aria-pressed="false">Reduzir animações</button>
            </div>
          </div>
          <div style="margin-top:.5rem">
            <button class="btn" id="reset" aria-label="Restaurar padrões">Restaurar padrões</button>
          </div>
          <div style="margin-top:.5rem;font-size:.9rem;color:var(--muted)">Dica: as preferências são salvas no seu navegador.</div>
        </div>
      </aside>
    </div>
  </main>

  <div class="aria-status" aria-live="polite" id="a11y-status"></div>

  <footer>
    <small>© Projeto Basquete — Lucas Batista</small>
  </footer>

  <script>
    const root = document.documentElement;
    const range = document.getElementById('font-size-range');
    const inc = document.getElementById('increase-font');
    const dec = document.getElementById('decrease-font');
    const toggleContrast = document.getElementById('toggle-contrast');
    const resetBtn = document.getElementById('reset');
    const status = document.getElementById('a11y-status');
    const toggleMotion = document.getElementById('toggle-motion');

    function announce(msg){
      status.textContent = msg;
    }

    const saved = JSON.parse(localStorage.getItem('a11yPrefs') || '{}');
    if(saved.fontSize) setFontSize(saved.fontSize, false);
    if(saved.highContrast) setContrast(saved.highContrast, false);
    if(saved.reduceMotion) setMotion(saved.reduceMotion, false);

    function setFontSize(size, save=true){
      root.style.setProperty('--base-font', size + 'px');
      range.value = size;
      range.setAttribute('aria-valuenow', String(size));
      announce('Tamanho da fonte definido para ' + size + ' pixels.');
      if(save) savePrefs();
    }

    inc.addEventListener('click', ()=>{
      let v = Math.min(Number(range.max), Number(range.value) + 1);
      setFontSize(v);
    });
    dec.addEventListener('click', ()=>{
      let v = Math.max(Number(range.min), Number(range.value) - 1);
      setFontSize(v);
    });
    range.addEventListener('input', (e)=>{ setFontSize(e.target.value); });

    function setContrast(on, save=true){
      const body = document.body;
      if(on){
        body.classList.add('high-contrast');
        toggleContrast.textContent = 'Desativar contraste';
        toggleContrast.setAttribute('aria-pressed','true');
        announce('Modo alto contraste ativado: fundo branco, letras pretas e destaques em amarelo.');
      } else {
        body.classList.remove('high-contrast');
        toggleContrast.textContent = 'Ativar contraste';
        toggleContrast.setAttribute('aria-pressed','false');
        announce('Modo alto contraste desativado.');
      }
      if(save) savePrefs();
    }

    toggleContrast.addEventListener('click', ()=>{
      const isOn = document.body.classList.contains('high-contrast');
      setContrast(!isOn);
    });

    function setMotion(on, save=true){
      if(on){
        document.documentElement.style.setProperty('scroll-behavior','auto');
        toggleMotion.textContent = 'Animações reduzidas';
        toggleMotion.setAttribute('aria-pressed','true');
        announce('Redução de movimento ativada');
      } else {
        document.documentElement.style.removeProperty('scroll-behavior');
        toggleMotion.textContent = 'Reduzir animações';
        toggleMotion.setAttribute('aria-pressed','false');
        announce('Redução de movimento desativada');
      }
      if(save) savePrefs();
    }

    toggleMotion.addEventListener('click', ()=>{
      const on = toggleMotion.getAttribute('aria-pressed') === 'true';
      setMotion(!on);
    });

    resetBtn.addEventListener('click', ()=>{
      setFontSize(16);
      setContrast(false);
      setMotion(false);
      localStorage.removeItem('a11yPrefs');
      announce('Preferências restauradas');
    });

    function savePrefs(){
      const prefs = {
        fontSize: Number(range.value),
        highContrast: document.body.classList.contains('high-contrast'),
        reduceMotion: toggleMotion.getAttribute('aria-pressed') === 'true'
      };
      localStorage.setItem('a11yPrefs', JSON.stringify(prefs));
    }

    document.getElementById('open-a11y').addEventListener('click', ()=>{
      document.getElementById('font-size-range').focus();
    });

    range.addEventListener('change', ()=> range.setAttribute('aria-valuenow', range.value));

    announce('Menu de acessibilidade carregado. Preferências carregadas do navegador.');
  </script>
</body>
</html>
