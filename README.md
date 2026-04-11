<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Matheus Eduardo | Backend</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&display=swap');

    :root {
      --bg: #070c1a;
      --panel: #0e152b;
      --stroke: #16203b;
      --accent: #00d4ff;
      --accent-2: #7b5cff;
      --text: #e8efff;
      --muted: #9db1d6;
      --shadow: 0 20px 70px rgba(0, 212, 255, 0.15);
    }

    * { box-sizing: border-box; }

    body {
      margin: 0;
      min-height: 100vh;
      background: radial-gradient(circle at 20% 20%, rgba(0, 212, 255, 0.08), transparent 35%),
                  radial-gradient(circle at 80% 0%, rgba(123, 92, 255, 0.10), transparent 30%),
                  var(--bg);
      color: var(--text);
      font-family: 'Space Grotesk', system-ui, -apple-system, sans-serif;
      display: grid;
      place-items: center;
      padding: 32px;
    }

    main {
      width: min(1100px, 100%);
    }

    .card {
      position: relative;
      background: linear-gradient(135deg, rgba(14, 21, 43, 0.92), rgba(10, 16, 32, 0.92));
      border: 1px solid var(--stroke);
      border-radius: 28px;
      padding: 36px clamp(24px, 3vw, 48px);
      box-shadow: var(--shadow);
      overflow: hidden;
    }

    .glow {
      position: absolute;
      inset: -30% -10% auto auto;
      width: 320px;
      height: 320px;
      background: radial-gradient(circle, rgba(0, 212, 255, 0.22), transparent 60%);
      filter: blur(50px);
      pointer-events: none;
      z-index: 0;
    }

    header {
      display: grid;
      grid-template-columns: auto 1fr;
      gap: 24px;
      align-items: center;
      position: relative;
      z-index: 1;
    }

    .avatar {
      position: relative;
      width: 160px;
      height: 160px;
    }

    .avatar::before {
      content: "";
      position: absolute;
      inset: -8px;
      border-radius: 50%;
      background: conic-gradient(from 90deg, var(--accent), var(--accent-2), var(--accent));
      filter: blur(1px);
      animation: spin 10s linear infinite;
      opacity: 0.85;
    }

    .avatar img {
      position: relative;
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 50%;
      border: 4px solid var(--panel);
      box-shadow: 0 15px 40px rgba(0, 0, 0, 0.35);
      z-index: 1;
    }

    @keyframes spin {
      to { transform: rotate(360deg); }
    }

    .title-block h1 {
      margin: 0;
      font-size: clamp(26px, 4vw, 36px);
      letter-spacing: -0.02em;
    }

    .title-block .role {
      color: var(--muted);
      margin: 6px 0 16px;
      font-weight: 500;
    }

    .chips {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .chip {
      background: rgba(0, 212, 255, 0.08);
      color: var(--text);
      border: 1px solid rgba(0, 212, 255, 0.2);
      padding: 8px 12px;
      border-radius: 12px;
      font-size: 14px;
      letter-spacing: 0.01em;
    }

    .cta {
      margin-top: 18px;
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .btn {
      padding: 12px 18px;
      border-radius: 12px;
      border: 1px solid var(--stroke);
      color: var(--text);
      text-decoration: none;
      font-weight: 600;
      transition: transform 0.15s ease, box-shadow 0.15s ease, border-color 0.2s ease;
      display: inline-flex;
      gap: 8px;
      align-items: center;
    }

    .btn.primary {
      background: linear-gradient(135deg, var(--accent), #15b1ff);
      color: #04101d;
      border: none;
      box-shadow: 0 10px 30px rgba(0, 212, 255, 0.35);
    }

    .btn.ghost {
      background: rgba(255, 255, 255, 0.04);
    }

    .btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 14px 30px rgba(0, 0, 0, 0.25);
      border-color: var(--accent);
    }

    section.content {
      margin-top: 32px;
      position: relative;
      z-index: 1;
      display: grid;
      gap: 20px;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    }

    .panel {
      background: rgba(255, 255, 255, 0.02);
      border: 1px solid var(--stroke);
      border-radius: 18px;
      padding: 18px 20px;
      backdrop-filter: blur(6px);
    }

    .panel h2 {
      margin: 0 0 12px;
      font-size: 18px;
      letter-spacing: -0.01em;
    }

    .panel p {
      margin: 0;
      color: var(--muted);
      line-height: 1.6;
    }

    .stack-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      gap: 12px;
    }

    .tech {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 10px 12px;
      border: 1px solid var(--stroke);
      border-radius: 12px;
      background: rgba(255, 255, 255, 0.02);
      transition: border-color 0.2s ease, transform 0.15s ease;
    }

    .tech img {
      width: 26px;
      height: 26px;
      object-fit: contain;
    }

    .tech span {
      font-weight: 600;
      letter-spacing: 0.01em;
      color: var(--text);
    }

    .tech:hover {
      border-color: var(--accent);
      transform: translateY(-2px);
    }

    .contacts {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .contact-pill {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 10px 12px;
      border-radius: 12px;
      border: 1px solid var(--stroke);
      color: var(--text);
      text-decoration: none;
      background: rgba(255, 255, 255, 0.02);
      transition: border-color 0.2s ease, transform 0.15s ease;
    }

    .contact-pill:hover {
      border-color: var(--accent);
      transform: translateY(-2px);
    }

    .contact-pill img {
      width: 18px;
      height: 18px;
      transition: filter 0.2s ease, opacity 0.2s ease;
    }

    .contact-pill img.mono {
      filter: brightness(0) invert(1);
      opacity: 0.9;
    }

    footer {
      margin-top: 18px;
      color: var(--muted);
      font-size: 14px;
      text-align: center;
    }

    @media (max-width: 700px) {
      header {
        grid-template-columns: 1fr;
        justify-items: center;
        text-align: center;
      }
      .avatar { margin: 0 auto; }
      .cta { justify-content: center; }
    }
  </style>
</head>
<body>
  <main>
    <article class="card">
      <div class="glow"></div>

      <header>
        <div class="avatar">
          <img src="img/foto-github.jpg" alt="Foto de perfil de Matheus Eduardo">
        </div>
        <div class="title-block">
          <h1>Matheus Eduardo</h1>
          <div class="role">Desenvolvedor Backend • Python • SQL • Cloud</div>
          <div class="chips">
            <span class="chip">APIs e automações</span>
            <span class="chip">Boas práticas & testes</span>
            <span class="chip">Escalabilidade na nuvem</span>
          </div>
          <div class="cta">
            <a class="btn primary" href="https://matheuseduardo04-dotcom.github.io/PORTIFOLIO/" target="_blank" rel="noopener">🚀 Ver portfólio</a>
            <a class="btn ghost" href="mailto:me8164755@gmail.com">✉️ Fale comigo</a>
          </div>
        </div>
      </header>

      <section class="content">
        <div class="panel">
          <h2>Sobre mim</h2>
          <p>Sou um desenvolvedor Back-End focado em Python, SQL e Cloud. Crio soluções robustas e escaláveis que resolvem problemas reais. Apaixonado por código limpo, boas práticas e por aprender novas tecnologias todos os dias.</p>
        </div>

        <div class="panel">
          <h2>Tecnologias</h2>
          <div class="stack-grid">
            <div class="tech">
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python">
              <span>Python</span>
            </div>
            <div class="tech">
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="SQL">
              <span>MySQL</span>
            </div>
            <div class="tech">
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git">
              <span>Git</span>
            </div>
            <div class="tech">
              <img src="cloud.jpg" alt="AWS">
              <span>Cloud AWS</span>
            </div>
          </div>
        </div>

        <div class="panel">
          <h2>Contato</h2>
          <div class="contacts">
            <a class="contact-pill" href="https://www.linkedin.com/in/matheus-eduardo-6a71463b0" target="_blank" rel="noopener">
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" alt="LinkedIn">
              <span>LinkedIn</span>
            </a>
            <a class="contact-pill" href="mailto:me8164755@gmail.com">
              <img class="mono" src="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/gmail.svg" alt="Email">
              <span>Email</span>
            </a>
            <a class="contact-pill" href="https://wa.me/5543996353642" target="_blank" rel="noopener">
              <img class="mono" src="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/whatsapp.svg" alt="WhatsApp">
              <span>WhatsApp</span>
            </a>
          </div>
        </div>
      </section>

      <footer>
        Desenvolvedor | Backend | Python | SQL | Cloud | Git
      </footer>
    </article>
  </main>
</body>
</html>
