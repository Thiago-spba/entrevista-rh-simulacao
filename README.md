<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>Nexus Virtual Solutions | Simulação de Entrevista RH</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-main: #F7F4EE;
      --bg-card: #FFFFFF;
      --bg-subtle: #EFECE4;
      --text-main: #1F2421;
      --text-muted: #667069;
      --brand-primary: #1E3A8A;
      --brand-primary-light: #EFF6FF;
      --brand-accent: #D97706;
      --brand-accent-light: #FEF3C7;
      --brand-success: #15803D;
      --brand-success-light: #DCFCE7;
      --border-color: #E6E1D5;
      --radius-sm: 8px;
      --radius-md: 14px;
      --radius-lg: 20px;
      --shadow-sm: 0 1px 3px rgba(0,0,0,0.05);
      --shadow-md: 0 4px 12px rgba(30,58,138,0.08);
      --shadow-lg: 0 10px 25px rgba(0,0,0,0.08);
      --font-main: 'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      -webkit-tap-highlight-color: transparent;
    }

    body {
      font-family: var(--font-main);
      background-color: var(--bg-main);
      color: var(--text-main);
      line-height: 1.5;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    .view-screen {
      display: none;
      width: 100%;
      max-width: 760px;
      margin: 0 auto;
      padding: 16px;
    }

    .view-screen.active {
      display: block;
      animation: fadeIn 0.25s ease-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(6px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* TELA 1: HOME */
    .home-header {
      text-align: center;
      padding: 24px 12px 16px;
    }

    .badge-institution {
      display: inline-block;
      background-color: var(--bg-subtle);
      color: var(--brand-primary);
      font-size: 0.75rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      padding: 6px 14px;
      border-radius: 999px;
      margin-bottom: 12px;
      border: 1px solid var(--border-color);
    }

    .home-title {
      font-size: 1.75rem;
      font-weight: 800;
      color: var(--brand-primary);
      line-height: 1.25;
      margin-bottom: 8px;
    }

    .home-subtitle {
      font-size: 0.95rem;
      color: var(--text-muted);
      max-width: 580px;
      margin: 0 auto 20px;
    }

    .card-info {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 20px;
      margin-bottom: 16px;
      box-shadow: var(--shadow-sm);
    }

    .card-info-title {
      font-size: 1.1rem;
      font-weight: 700;
      color: var(--brand-primary);
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 12px;
    }

    .card-info p {
      font-size: 0.9rem;
      margin-bottom: 10px;
    }

    .card-info ul {
      padding-left: 20px;
      font-size: 0.88rem;
    }

    .card-info li {
      margin-bottom: 6px;
    }

    .author-box {
      background: #F4EFE6;
      border-left: 4px solid var(--brand-accent);
      padding: 14px 16px;
      border-radius: 0 var(--radius-sm) var(--radius-sm) 0;
      margin: 16px 0;
      font-size: 0.85rem;
    }

    .author-box strong {
      color: var(--brand-primary);
      display: block;
      font-size: 0.95rem;
      margin-bottom: 2px;
    }

    .btn-start-interview {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      width: 100%;
      background: var(--brand-primary);
      color: #FFFFFF;
      font-family: var(--font-main);
      font-size: 1.1rem;
      font-weight: 700;
      padding: 18px 24px;
      border-radius: var(--radius-lg);
      border: none;
      cursor: pointer;
      box-shadow: 0 4px 15px rgba(30, 58, 138, 0.25);
      transition: transform 0.15s ease, background 0.15s ease;
      margin: 24px 0 32px;
    }

    .btn-start-interview:active {
      transform: scale(0.98);
      background: #172554;
    }

    /* TELA 2: SALA DE ENTREVISTA (STICKY HEADER) */
    .interview-view-container {
      padding-top: 0;
      padding-bottom: 40px;
    }

    .sticky-top-bar {
      position: sticky;
      top: 0;
      z-index: 100;
      background: rgba(247, 244, 238, 0.96);
      backdrop-filter: blur(8px);
      -webkit-backdrop-filter: blur(8px);
      padding: 10px 16px 12px;
      border-bottom: 1px solid var(--border-color);
      margin: -16px -16px 16px -16px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.03);
    }

    .bar-top-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 8px;
    }

    .candidate-badge {
      font-size: 0.82rem;
      font-weight: 700;
      color: var(--brand-primary);
      background: #E0E7FF;
      padding: 4px 10px;
      border-radius: 999px;
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    .bar-actions {
      display: flex;
      gap: 8px;
      align-items: center;
    }

    .btn-icon {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      color: var(--text-main);
      width: 36px;
      height: 36px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1rem;
      cursor: pointer;
      box-shadow: var(--shadow-sm);
    }

    .timer-widget {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 8px 14px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      box-shadow: var(--shadow-sm);
    }

    .timer-display {
      font-size: 1.4rem;
      font-weight: 800;
      font-variant-numeric: tabular-nums;
      color: var(--brand-primary);
      letter-spacing: -0.02em;
    }

    .timer-display.danger {
      color: #DC2626;
      animation: pulse 1s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.5; }
    }

    .timer-controls {
      display: flex;
      gap: 6px;
    }

    .btn-timer {
      background: var(--bg-subtle);
      border: 1px solid var(--border-color);
      color: var(--text-main);
      font-family: var(--font-main);
      font-size: 0.75rem;
      font-weight: 600;
      padding: 6px 10px;
      border-radius: var(--radius-sm);
      cursor: pointer;
    }

    .btn-timer.primary {
      background: var(--brand-primary);
      color: #FFFFFF;
      border-color: var(--brand-primary);
    }

    .controls-panel {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 16px;
      align-items: center;
    }

    .btn-draw {
      flex: 1 1 auto;
      background: var(--brand-accent);
      color: #FFFFFF;
      font-family: var(--font-main);
      font-size: 0.95rem;
      font-weight: 700;
      padding: 12px 18px;
      border-radius: var(--radius-md);
      border: none;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      box-shadow: 0 2px 8px rgba(217, 119, 6, 0.25);
    }

    .btn-next-candidate {
      background: var(--bg-card);
      border: 1px solid var(--brand-primary);
      color: var(--brand-primary);
      font-family: var(--font-main);
      font-size: 0.85rem;
      font-weight: 700;
      padding: 12px 14px;
      border-radius: var(--radius-md);
      cursor: pointer;
      white-space: nowrap;
    }

    .pool-status {
      font-size: 0.78rem;
      color: var(--text-muted);
      width: 100%;
      text-align: center;
      margin-top: -4px;
      margin-bottom: 8px;
    }

    /* CARD DA QUESTÃO */
    .question-card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      box-shadow: var(--shadow-md);
      overflow: hidden;
      margin-bottom: 20px;
    }

    .card-header-meta {
      background: #FAF8F5;
      padding: 14px 18px;
      border-bottom: 1px solid var(--border-color);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .category-tag {
      font-size: 0.75rem;
      font-weight: 700;
      padding: 4px 10px;
      border-radius: 999px;
      text-transform: uppercase;
      letter-spacing: 0.03em;
    }

    .tag-comportamental { background: #FEF3C7; color: #92400E; }
    .tag-tecnica { background: #EFF6FF; color: #1E40AF; }

    .step-indicator {
      font-size: 0.78rem;
      font-weight: 700;
      color: var(--brand-primary);
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      padding: 3px 8px;
      border-radius: var(--radius-sm);
    }

    .card-body-content {
      padding: 20px 18px;
    }

    .question-theme-title {
      font-size: 0.85rem;
      font-weight: 700;
      color: var(--brand-accent);
      text-transform: uppercase;
      letter-spacing: 0.05em;
      margin-bottom: 6px;
    }

    .step-section { display: none; }
    .step-section.active { display: block; animation: fadeIn 0.2s ease-out; }

    .question-prompt {
      font-size: 1.15rem;
      font-weight: 700;
      color: var(--text-main);
      line-height: 1.4;
      margin-bottom: 18px;
    }

    .instructions-rh-hint {
      background: #F8FAFC;
      border-left: 3px solid var(--brand-primary);
      padding: 10px 14px;
      font-size: 0.85rem;
      color: #334155;
      border-radius: 0 var(--radius-sm) var(--radius-sm) 0;
      margin-bottom: 16px;
    }

    .options-list {
      display: flex;
      flex-direction: column;
      gap: 10px;
      margin-bottom: 18px;
    }

    .option-item {
      background: var(--bg-main);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 12px 14px;
      font-size: 0.92rem;
      line-height: 1.35;
      color: var(--text-main);
    }

    .option-item.correct-revealed {
      background: var(--brand-success-light);
      border-color: var(--brand-success);
      font-weight: 600;
      color: #14532D;
    }

    .answer-box {
      background: var(--brand-success-light);
      border: 1px solid #86EFAC;
      border-radius: var(--radius-md);
      padding: 14px 16px;
      margin-bottom: 16px;
    }

    .answer-title {
      font-size: 0.95rem;
      font-weight: 800;
      color: var(--brand-success);
      margin-bottom: 4px;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .feedback-rh-box {
      background: #F4EFE6;
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 14px 16px;
      margin-bottom: 16px;
    }

    .feedback-rh-title {
      font-size: 0.88rem;
      font-weight: 700;
      color: var(--brand-primary);
      margin-bottom: 6px;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .feedback-rh-text {
      font-size: 0.88rem;
      color: var(--text-main);
      line-height: 1.4;
    }

    .card-footer-controls {
      display: flex;
      gap: 10px;
      margin-top: 10px;
    }

    .btn-step {
      flex: 1;
      font-family: var(--font-main);
      font-size: 0.95rem;
      font-weight: 700;
      padding: 12px 16px;
      border-radius: var(--radius-md);
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      border: none;
    }

    .btn-step-primary { background: var(--brand-primary); color: #FFFFFF; }
    .btn-step-primary:active { background: #172554; }
    .btn-step-secondary { background: var(--bg-subtle); color: var(--text-main); border: 1px solid var(--border-color); }

    /* MODAL DE AJUDA */
    .modal-backdrop {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: rgba(0,0,0,0.5);
      z-index: 999;
      align-items: center;
      justify-content: center;
      padding: 16px;
    }

    .modal-backdrop.active { display: flex; animation: fadeIn 0.2s ease-out; }

    .modal-window {
      background: var(--bg-card);
      border-radius: var(--radius-lg);
      max-width: 520px;
      width: 100%;
      max-height: 85vh;
      overflow-y: auto;
      padding: 24px;
      box-shadow: var(--shadow-lg);
      position: relative;
    }

    .modal-close-btn {
      position: absolute;
      top: 16px;
      right: 16px;
      background: var(--bg-subtle);
      border: none;
      width: 32px;
      height: 32px;
      border-radius: 50%;
      font-size: 1.1rem;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .modal-title {
      font-size: 1.2rem;
      font-weight: 800;
      color: var(--brand-primary);
      margin-bottom: 12px;
    }

    .modal-content p { font-size: 0.9rem; margin-bottom: 10px; }
    .modal-content ul { padding-left: 20px; font-size: 0.88rem; margin-bottom: 14px; }
    .modal-content li { margin-bottom: 6px; }

    footer {
      margin-top: auto;
      text-align: center;
      padding: 20px 16px;
      font-size: 0.78rem;
      color: var(--text-muted);
      border-top: 1px solid var(--border-color);
      background: #F4EFE6;
    }
  </style>
</head>
<body>

  <!-- ================= TELA 1: HOME ================= -->
  <div id="screen-home" class="view-screen active">
    <div class="home-header">
      <span class="badge-institution">Educação Profissional Paulista</span>
      <h1 class="home-title">Nexus Virtual Solutions</h1>
      <p class="home-subtitle">Simulação de Entrevista de Emprego | Processo Seletivo para Desenvolvedor(a) Júnior & Estágio</p>
    </div>

    <div class="card-info">
      <div class="card-info-title"><span>👨‍🏫</span> Projeto Pedagógico & Autoria</div>
      <div class="author-box">
        <strong>Idealização e Mediação:</strong>
        Prof. Thiago Fernando (Graduando em Engenharia de Computação | Licenciado em Matemática)
      </div>
      <p><strong>Componentes Integrados:</strong></p>
      <ul>
        <li><strong>Carreiras e Competências:</strong> Persona profissional, etiqueta corporativa, comunicação digital (e-mails/chats), postura ética e feedback.</li>
        <li><strong>Desenvolvimento de Sistemas:</strong> Lógica de programação, vetores (listas), matrizes bidimensionais e modularização com funções em Python.</li>
      </ul>
    </div>

    <div class="card-info">
      <div class="card-info-title"><span>🏢</span> Sobre a Nexus Virtual Solutions</div>
      <p>Empresa de tecnologia focada em soluções virtuais (apps, sites e softwares). Os estudantes concorrem a vagas de estágio técnico.</p>
      <p><strong>Papel da Direção (RH):</strong> Conduzir as entrevistas de 3 a 5 minutos, avaliando a clareza, a postura e a segurança dos alunos diante das situações apresentadas.</p>
    </div>

    <div class="card-info">
      <div class="card-info-title"><span>📋</span> Como Conduzir a Simulação</div>
      <ul>
        <li><strong>Tempo por aluno:</strong> 3 a 5 minutos (utilize o cronômetro no topo da tela).</li>
        <li><strong>Passo 1:</strong> Leia a pergunta sorteada para o aluno.</li>
        <li><strong>Passo 2:</strong> Mostre/leia as alternativas para apoiar a resposta.</li>
        <li><strong>Passo 3:</strong> Consulte o gabarito e a dica do RH para validar a resposta e dar o feedback final de 30 segundos.</li>
      </ul>
    </div>

    <button class="btn-start-interview" onclick="startInterviewSession()">
      <span>Iniciar Entrevistas</span> <span>➔</span>
    </button>
  </div>

  <!-- ================= TELA 2: SALA DE ENTREVISTA ================= -->
  <div id="screen-interview" class="view-screen interview-view-container">

    <!-- Topo Fixo com Cronômetro (Sticky) -->
    <div class="sticky-top-bar">
      <div class="bar-top-row">
        <div class="candidate-badge">
          <span>👤</span> <span id="candidate-label">Candidato #1</span>
        </div>
        <div class="bar-actions">
          <button class="btn-icon" onclick="openHelpModal()" title="Instruções Rápidas">❓</button>
          <button class="btn-icon" onclick="goToHome()" title="Voltar ao Início">🏠</button>
        </div>
      </div>

      <div class="timer-widget">
        <div class="timer-display" id="timer-text">03:00</div>
        <div class="timer-controls">
          <button class="btn-timer primary" id="btn-timer-toggle" onclick="toggleTimer()">Iniciar</button>
          <button class="btn-timer" onclick="resetTimer(180)">3 min</button>
          <button class="btn-timer" onclick="resetTimer(300)">5 min</button>
          <button class="btn-timer" onclick="resetTimer(180)">↺</button>
        </div>
      </div>
    </div>

    <!-- Painel de Sorteio -->
    <div class="controls-panel">
      <button class="btn-draw" onclick="drawNewQuestion()">
        <span>🎲</span> <span>Sortear Nova Questão</span>
      </button>
      <button class="btn-next-candidate" onclick="nextCandidate()">
        <span>Próximo Aluno 👤</span>
      </button>
    </div>
    <div class="pool-status" id="pool-status-text">Carregando banco de questões...</div>

    <!-- Card da Questão -->
    <div class="question-card">
      <div class="card-header-meta">
        <span class="category-tag tag-comportamental" id="card-category-badge">Comportamental</span>
        <span class="step-indicator" id="step-indicator-text">Passo 1 de 3</span>
      </div>

      <div class="card-body-content">
        <div class="question-theme-title" id="card-sub-title">Persona Profissional</div>

        <!-- PASSO 1: PERGUNTA -->
        <div id="step-1-view" class="step-section active">
          <div class="instructions-rh-hint">
            <strong>Instrução ao RH:</strong> Leia a pergunta abaixo de forma clara para o candidato.
          </div>
          <div class="question-prompt" id="question-text">
            Clique em "Sortear Nova Questão" para começar.
          </div>
          <div class="card-footer-controls">
            <button class="btn-step btn-step-primary" onclick="goToStep(2)">
              <span>Ver Alternativas ➔</span>
            </button>
          </div>
        </div>

        <!-- PASSO 2: ALTERNATIVAS -->
        <div id="step-2-view" class="step-section">
          <div class="instructions-rh-hint">
            <strong>Instrução ao RH:</strong> Leia as alternativas e peça para o aluno escolher uma e justificar.
          </div>
          <div class="options-list" id="options-container"></div>
          <div class="card-footer-controls">
            <button class="btn-step btn-step-secondary" onclick="goToStep(1)">
              <span>⬅ Voltar à Pergunta</span>
            </button>
            <button class="btn-step btn-step-primary" onclick="goToStep(3)">
              <span>Ver Gabarito & Dica RH ➔</span>
            </button>
          </div>
        </div>

        <!-- PASSO 3: GABARITO & DICA RH -->
        <div id="step-3-view" class="step-section">
          <div class="answer-box">
            <div class="answer-title">
              <span>✅</span> <span id="correct-option-label">Alternativa Correta: B</span>
            </div>
            <p style="font-size: 0.9rem; color: #166534;" id="correct-option-text"></p>
          </div>

          <div class="feedback-rh-box">
            <div class="feedback-rh-title"><span>💡</span> O que a Direção (RH) deve avaliar:</div>
            <div class="feedback-rh-text" id="tip-rh-text"></div>
          </div>

          <div class="card-footer-controls">
            <button class="btn-step btn-step-secondary" onclick="goToStep(2)">
              <span>⬅ Ver Opções</span>
            </button>
            <button class="btn-step btn-step-primary" onclick="drawNewQuestion()">
              <span>🎲 Próxima Questão</span>
            </button>
          </div>
        </div>

      </div>
    </div>
  </div>

  <!-- ================= MODAL DE AJUDA ================= -->
  <div id="help-modal" class="modal-backdrop" onclick="closeHelpModalOnBackdrop(event)">
    <div class="modal-window">
      <button class="modal-close-btn" onclick="closeHelpModal()">✕</button>
      <h2 class="modal-title">Guia Rápido do Entrevistador (RH)</h2>
      <div class="modal-content">
        <p><strong>🎯 Objetivo:</strong> Proporcionar aos estudantes uma vivência acolhedora e real de entrevista corporativa em tecnologia.</p>
        <p><strong>⏱️ Gestão do Tempo (3 a 5 min):</strong></p>
        <ul>
          <li><strong>1 min:</strong> Apresentação pessoal e quebra-gelo.</li>
          <li><strong>2 a 3 min:</strong> 1 ou 2 perguntas sorteadas pelo app.</li>
          <li><strong>30 seg:</strong> Feedback final rápido (Elogio + Ponto de melhoria).</li>
        </ul>
        <p><strong>💡 Foco de Avaliação:</strong></p>
        <ul>
          <li><strong>Comunicação:</strong> Clareza, ausência de gírias excessivas.</li>
          <li><strong>Postura:</strong> Contato visual e firmeza.</li>
          <li><strong>Maturidade:</strong> Acolhimento de correções e honestidade.</li>
        </ul>
      </div>
    </div>
  </div>

  <footer>
    Nexus Virtual Solutions • Simulação de Entrevistas<br>
    Prof. Thiago Fernando • Educação Profissional Paulista
  </footer>

  <!-- ================= JAVASCRIPT: LÓGICA COMPLETA ================= -->
  <script>
    const QUESTIONS_DATA = [
      {
        id: 1, category: "Comportamental", sub: "Persona Profissional", title: "Apresentação Pessoal em Entrevista",
        question: "Ao iniciar a entrevista e ser solicitado(a) a falar sobre você, qual postura e comunicação são as mais adequadas?",
        options: [
          "A) Falar de forma muito informal com gírias: 'tipo assim, eu faço várias coisas e ajudo geral lá'.",
          "B) Apresentar-se com clareza, destacando seus estudos, facilidade em equipe e experiências na escola.",
          "C) Ficar de braços cruzados e responder apenas com 'não sei o que falar'.",
          "D) Focar apenas em desabafos sobre problemas pessoais e vida íntima."
        ],
        correct: "B", tip_rh: "Avalie se o candidato fala com clareza, bom tom de voz e postura madura, valorizando sua trajetória escolar."
      },
      {
        id: 2, category: "Comportamental", sub: "Dress Code & Imagem", title: "Código de Vestimenta na Área de TI",
        question: "Sobre o Dress Code (código de vestimenta) em empresas de desenvolvimento de software, o que é correto afirmar?",
        options: [
          "A) É obrigatório usar terno e gravata todos os dias em qualquer empresa de tecnologia.",
          "B) Roupas não importam no trabalho; higiene e bom senso são totalmente irrelevantes.",
          "C) Varia conforme a cultura da empresa; no setor de TI costuma ser casual/flexível, mantendo o bom senso e a higiene.",
          "D) O código de vestimenta só se aplica para diretores da empresa."
        ],
        correct: "C", tip_rh: "O candidato deve demonstrar que compreende adequação ao contexto, higiene pessoal e equilíbrio entre conforto e profissionalismo."
      },
      {
        id: 3, category: "Comportamental", sub: "Linguagem Corporal", title: "Comunicação Não-Verbal e Postura",
        question: "Durante a entrevista, de que forma a postura corporal e o contato visual influenciam a percepção do entrevistador?",
        options: [
          "A) Não influenciam em nada; o entrevistador só presta atenção nas palavras exatas.",
          "B) Manter contato visual, postura ereta e atenção transmite segurança, respeito e interesse genuíno na vaga.",
          "C) Olhar fixamente para o celular durante a conversa mostra que você é multitarefa.",
          "D) Sentar-se debruçado na mesa transmite ar de autoridade e liderança."
        ],
        correct: "B", tip_rh: "Observe a linguagem corporal do aluno: contato visual com a banca, postura confiante e escuta atenta."
      },
      {
        id: 4, category: "Comportamental", sub: "Etiqueta Diária", title: "Postura em Reuniões de Equipe",
        question: "Durante uma reunião para definir o lançamento de um site, um colega ao lado puxa conversas paralelas insistentes. Como você age?",
        options: [
          "A) Entra na conversa paralela e ri alto com o colega.",
          "B) Grita no meio da sala exigindo silêncio imediato.",
          "C) Mantém a atenção no líder e sinaliza discretamente ao colega para conversarem após o término da reunião.",
          "D) Levanta e vai embora sem dar explicações."
        ],
        correct: "C", tip_rh: "Avalie o bom senso, a maturidade para evitar conflitos desnecessários e o respeito ao tempo da equipe."
      },
      {
        id: 5, category: "Comportamental", sub: "Comunicação Digital", title: "O 'Efeito Suspense' no Chat Corporativo",
        question: "Por que mandar apenas 'Oi, tudo bem?' no WhatsApp/Teams e sumir sem explicar o assunto é uma má prática?",
        options: [
          "A) Porque gera ansiedade no colega, interrompe a produtividade e atrasa a resolução da demanda.",
          "B) Porque o aplicativo cobra taxa extra por cada mensagem enviada.",
          "C) Porque o gestor é obrigado a responder em menos de 10 segundos.",
          "D) Não é má prática; é a forma mais formal e elegante de iniciar conversas."
        ],
        correct: "A", tip_rh: "O aluno deve entender o conceito de assertividade: enviar a saudação acompanhada do contexto e da dúvida na mesma mensagem."
      },
      {
        id: 6, category: "Comportamental", sub: "Comunicação Digital", title: "Boas Práticas no Uso de Áudios",
        question: "Qual é a recomendação para o envio de mensagens de áudio em canais profissionais de trabalho?",
        options: [
          "A) Enviar sempre áudios longos de 10 minutos para não precisar digitar.",
          "B) Priorizar mensagens de texto claras; caso precise enviar áudio, pedir autorização prévia e ser breve e objetivo.",
          "C) Mandar áudios com barulho de trânsito ao fundo para provar que está em deslocamento.",
          "D) Substituir todos os relatórios escritos por áudios no WhatsApp."
        ],
        correct: "B", tip_rh: "O candidato deve valorizar a facilidade de busca e a clareza das mensagens de texto no ambiente de trabalho."
      },
      {
        id: 7, category: "Comportamental", sub: "Formalidade Suave", title: "A Arte da Formalidade Suave",
        question: "O que caracteriza o estilo de 'formalidade suave' trabalhado na comunicação profissional?",
        options: [
          "A) Usar gerundismos excessivos como 'estaremos solicitando a verificação'.",
          "B) Ser educado, claro e direto ao ponto, evitando tanto gírias exageradas quanto formalidades arcaicas.",
          "C) Falar de forma excessivamente íntima como se estivesse em um churrasco de família.",
          "D) Responder todas as mensagens usando apenas figurinhas e emojis."
        ],
        correct: "B", tip_rh: "Destaque da aula: equilíbrio, clareza e naturalidade sem informalidade desrespeitosa nem rebuscamento."
      },
      {
        id: 8, category: "Comportamental", sub: "E-mail Corporativo", title: "Anatomia do Assunto de um E-mail",
        question: "Ao enviar uma atualização do código de um aplicativo para seu gestor, qual assunto de e-mail é o mais profissional?",
        options: [
          "A) Assunto: 'olha ae'",
          "B) Assunto em branco (sem título)",
          "C) Assunto: '[Atualização] Módulo de Cadastro - Versão 1.2'",
          "D) Assunto: 'URGENTE LEIA POR FAVOR ME RESPONDE'"
        ],
        correct: "C", tip_rh: "Um bom assunto de e-mail resume o tema e a prioridade, facilitando a organização do destinatário."
      },
      {
        id: 9, category: "Comportamental", sub: "E-mail Corporativo", title: "Cuidado com o 'Responder a Todos'",
        question: "Quando você DEVE EVITAR usar a opção 'Responder a Todos' em uma conversa por e-mail?",
        options: [
          "A) Quando a informação for relevante para todos os envolvidos no projeto.",
          "B) Quando a resposta for apenas um agradecimento simples ou uma dúvida pontual direcionada a quem enviou.",
          "C) Quando o líder pedir para manter a equipe informada.",
          "D) Em caso de alteração no cronograma geral do sistema."
        ],
        correct: "B", tip_rh: "Evitar poluição desnecessária na caixa de entrada dos colegas de equipe."
      },
      {
        id: 10, category: "Comportamental", sub: "Comunicação Digital", title: "Respeito ao Horário de Expediente",
        question: "Você finalizou uma tarefa do sistema às 23h30. Qual é a conduta mais adequada para avisar o gestor?",
        options: [
          "A) Ligar várias vezes para o celular pessoal dele até ele atender.",
          "B) Mandar mensagem no WhatsApp particular exigindo confirmação de leitura imediata.",
          "C) Registrar o commit no repositório ou programar a mensagem/e-mail para o início do horário comercial no dia seguinte.",
          "D) Publicar no grupo de bate-papo informal da empresa cobrando retorno."
        ],
        correct: "C", tip_rh: "Observe a consciência sobre etiqueta profissional e respeito aos momentos de descanso da equipe."
      },
      {
        id: 11, category: "Comportamental", sub: "Feedback Profissional", title: "Recepção de Feedback e Mentalidade de Crescimento",
        question: "O líder técnico revisou seu código e disse: 'A sua lógica funciona, mas está desorganizada e precisa ser refatorada'. Como você reage?",
        options: [
          "A) Fica bravo(a), diz que o líder não entende nada e se recusa a alterar o código.",
          "B) Recebe com mentalidade de crescimento, agradece a orientação e pede dicas para melhorar a estrutura.",
          "C) Diz que 'funcionando é o que importa' e abandona a tarefa.",
          "D) Fica em silêncio, mas não faz nenhuma alteração no código."
        ],
        correct: "B", tip_rh: "Capacidade de receber feedback construtivo sem defensividade, enxergando oportunidade de evolução técnica."
      },
      {
        id: 12, category: "Comportamental", sub: "Feedback Profissional", title: "O Modelo SCI de Feedback",
        question: "O que propõe o modelo SCI (Situação, Comportamento, Impacto) ao analisar um problema no trabalho?",
        options: [
          "A) Fazer ataques à personalidade do colega na frente de todos.",
          "B) Descrever o contexto exato (Situação), a atitude observada (Comportamento) e o resultado gerado (Impacto), com foco em fatos.",
          "C) Inventar boatos sobre o colega para que o chefe tome uma atitude.",
          "D) Mandar um bilhete anônimo desrespeitoso."
        ],
        correct: "B", tip_rh: "O feedback deve ser objetivo, respeitoso e livre de julgamentos pessoais."
      },
      {
        id: 13, category: "Comportamental", sub: "Ética Profissional", title: "Sigilo e Proteção de Dados de Clientes",
        question: "Ao testar o banco de dados de um aplicativo, você tem acesso a senhas e dados confidenciais de clientes. Qual é a conduta ética?",
        options: [
          "A) Compartilhar os dados nos grupos de amigos para mostrar que tem acesso restrito.",
          "B) Manter sigilo absoluto e utilizar os dados estritamente para os testes autorizados do sistema.",
          "C) Enviar mensagens pessoais para os clientes através das redes sociais.",
          "D) Vender as informações de contato para empresas de propaganda."
        ],
        correct: "B", tip_rh: "Consciência clara sobre ética, compliance, privacidade de dados e segurança da informação."
      },
      {
        id: 14, category: "Comportamental", sub: "Ética Profissional", title: "Responsabilidade por Erros no Sistema",
        question: "Você cometeu um engano ao alterar uma linha de código e a página de login parou de funcionar. Qual é a atitude correta?",
        options: [
          "A) Colocar a culpa no colega novato para não ser advertido.",
          "B) Tentar apagar os logs e fingir que não sabe o que aconteceu.",
          "C) Assumir o erro com transparência, reportar imediatamente e ajudar na correção.",
          "D) Desligar o computador e ir embora para casa."
        ],
        correct: "C", tip_rh: "Transparência e maturidade ao assumir responsabilidades por falhas, focando na solução rápida."
      },
      {
        id: 15, category: "Comportamental", sub: "Proatividade", title: "Iniciativa Diante de um Erro no App",
        question: "Você notou que um botão do aplicativo está com um pequeno atraso para responder. O que representa uma atitude proativa?",
        options: [
          "A) Esperar os clientes reclamarem na loja de aplicativos para ver se é sério.",
          "B) Investigar a causa básica, documentar o problema e apresentar ao gestor já com uma sugestão de melhoria.",
          "C) Reclamar com os colegas que o aplicativo é ruim.",
          "D) Ignorar o fato, pois você foi contratado apenas para desenhar telas."
        ],
        correct: "B", tip_rh: "Proatividade é identificar o problema com antecedência e propor caminhos práticos de solução."
      },
      {
        id: 16, category: "Comportamental", sub: "Proatividade", title: "Comunicação Preventiva de Prazos",
        question: "Você percebeu que não conseguirá entregar uma tela no prazo combinado devido a uma dúvida técnica. O que fazer?",
        options: [
          "A) Avisar a liderança com antecedência, explicar o obstáculo e solicitar apoio para alinhar o prazo.",
          "B) Esperar vencer o prazo e só falar se alguém vier cobrar.",
          "C) Entregar a tela incompleta e sem funcionar só para cumprir o dia.",
          "D) Faltar no dia da entrega para evitar explicações."
        ],
        correct: "A", tip_rh: "Demonstração de responsabilidade com os compromissos da equipe e clareza na comunicação."
      },
      {
        id: 17, category: "Técnica", sub: "Vetores (Listas)", title: "Por que Usar Vetores em um Sistema?",
        question: "Em uma loja virtual com 50 produtos, por que usamos um vetor (lista) em vez de criar 50 variáveis soltas (p1, p2, p3...)?",
        options: [
          "A) Porque o computador trava se criarmos mais de cinco variáveis.",
          "B) Porque o vetor armazena vários valores relacionados em uma única estrutura, facilitando a organização e o uso de laços de repetição.",
          "C) Porque o Python proíbe criar variáveis individuais.",
          "D) Porque listas servem apenas para somar notas escolares."
        ],
        correct: "B", tip_rh: "O candidato deve explicar a vantagem de agrupar dados em sequência para facilitar o processamento em lote."
      },
      {
        id: 18, category: "Técnica", sub: "Vetores (Listas)", title: "Indexação Base 0 em Programação",
        question: "Dada a lista `jogos = ['Mario', 'Zelda', 'Sonic']`, qual comando acessa o primeiro jogo ('Mario') em Python?",
        options: [
          "A) `jogos[1]`",
          "B) `jogos[0]`",
          "C) `jogos['primeiro']`",
          "D) `jogos.item(1)`"
        ],
        correct: "B", tip_rh: "Regra fundamental das aulas: em programação, os índices começam no zero (Base 0)."
      },
      {
        id: 19, category: "Técnica", sub: "Vetores (Listas)", title: "Erro de Índice Fora da Faixa (IndexError)",
        question: "Se uma lista tem 3 elementos (`nomes = ['Ana', 'Bia', 'Caio']`), o que ocorre se tentarmos acessar `nomes`?",
        options: [
          "A) O Python inventa dois nomes vazios automaticamente.",
          "B) O sistema retorna zero sem avisar nada.",
          "C) Ocorre um erro de índice fora dos limites (`IndexError`), pois a posição 5 não existe.",
          "D) O programa apaga os arquivos do sistema."
        ],
        correct: "C", tip_rh: "Conhecimento sobre os limites válidos de uma lista (de 0 até tamanho - 1)."
      },
      {
        id: 20, category: "Técnica", sub: "Vetores (Listas)", title: "Função len() em Python",
        question: "Para que serve a função `len(minha_lista)` ao manipular dados em Python?",
        options: [
          "A) Para apagar todos os itens da lista.",
          "B) Para retornar a quantidade total de elementos dentro da lista.",
          "C) Para ordenar os números em ordem decrescente.",
          "D) Para imprimir a lista na impressora."
        ],
        correct: "B", tip_rh: "A função `len()` retorna o tamanho da lista, essencial para laços de repetição."
      },
      {
        id: 21, category: "Técnica", sub: "Vetores (Listas)", title: "Percorrendo Itens com o Laço for",
        question: "Qual é a forma mais prática de exibir todos os nomes de uma lista de clientes na tela?",
        options: [
          "A) Utilizar um laço `for nome in lista:` para iterar automaticamente sobre cada elemento.",
          "B) Escrever um comando `print()` manual para cada posição da lista.",
          "C) Copiar e colar a lista 50 vezes no código.",
          "D) O Python não consegue ler listas inteiras."
        ],
        correct: "A", tip_rh: "O aluno deve reconhecer o uso do loop `for` para percurso sequencial automatizado."
      },
      {
        id: 22, category: "Técnica", sub: "Vetores (Listas)", title: "Conceito de Busca Linear",
        question: "Como funciona o algoritmo de 'Busca Linear' para encontrar um item em uma lista?",
        options: [
          "A) O computador sorteia posições aleatórias até acertar.",
          "B) O programa percorre a lista elemento por elemento, do início ao fim, comparando se o item atual é o procurado.",
          "C) O sistema apaga a lista e recria apenas com o item buscado.",
          "D) É uma busca que só funciona se os dados estiverem criptografados."
        ],
        correct: "B", tip_rh: "Busca linear é a verificação sequencial item a item em uma coleção de dados."
      },
      {
        id: 23, category: "Técnica", sub: "Matrizes Bidimensionais", title: "Quando Usar uma Matriz (2D)?",
        question: "Quando uma matriz bidimensional é mais recomendada do que um vetor unidimensional simples?",
        options: [
          "A) Quando temos apenas uma lista simples de compras.",
          "B) Quando precisamos organizar dados em formato de tabela com linhas e colunas (ex: planilha, tabuleiro ou notas por matéria).",
          "C) Quando o programa não utiliza números.",
          "D) Matrizes não são usadas na área de sistemas."
        ],
        correct: "B", tip_rh: "Diferença conceitual: vetor = 1 dimensão (sequência simples); matriz = 2 dimensões (tabela com linhas e colunas)."
      },
      {
        id: 24, category: "Técnica", sub: "Matrizes Bidimensionais", title: "Acesso por Linha e Coluna",
        question: "Como acessamos um elemento localizado na Linha 1 e Coluna 2 de uma matriz em Python?",
        options: [
          "A) `matriz[coluna, linha]`",
          "B) `matriz`",
          "C) `matriz(1)(2)`",
          "D) `matriz.posicao(1, 2)`"
        ],
        correct: "B", tip_rh: "Sintaxe padrão: `matriz[linha][coluna]`, lembrando que ambos começam em zero."
      },
      {
        id: 25, category: "Técnica", sub: "Matrizes Bidimensionais", title: "Laços Aninhados em Matrizes",
        question: "Por que usamos dois laços de repetição (laços aninhados) para percorrer uma matriz completa?",
        options: [
          "A) Porque um laço percorre as linhas e o outro percorre as colunas/elementos de cada linha.",
          "B) Porque o computador precisa de dois laços para não travar.",
          "C) Porque o primeiro laço calcula a raiz quadrada e o segundo imprime.",
          "D) Não é necessário dois laços; um laço simples lê qualquer matriz."
        ],
        correct: "A", tip_rh: "Loop externo controla as linhas; loop interno percorre os elementos de cada coluna."
      },
      {
        id: 26, category: "Técnica", sub: "Matrizes Bidimensionais", title: "Agregação de Dados em Matrizes",
        question: "Em uma tabela de vendas organizada em matriz, o que significa fazer a 'agregação de dados'?",
        options: [
          "A) Excluir todas as vendas cadastradas.",
          "B) Resumir múltiplos valores em informações consolidadas, como calcular o total vendido ou a média de uma coluna.",
          "C) Alterar a fonte do texto do programa.",
          "D) Converter todos os números em letras."
        ],
        correct: "B", tip_rh: "Agregação = somar, calcular média, encontrar maior/menor valor em uma estrutura de dados."
      },
      {
        id: 27, category: "Técnica", sub: "Funções & Modularização", title: "Conceito de Função (Analogia da Receita)",
        question: "Nas aulas de lógica, por que uma função (`def`) é comparada a uma 'receita de bolo'?",
        options: [
          "A) Porque ela só pode ser executada uma única vez na história do programa.",
          "B) Porque é um bloco de código que você escreve uma vez e pode executar sempre que precisar, sem ter que reescrever tudo do zero.",
          "C) Porque funções em Python servem exclusivamente para sites de culinária.",
          "D) Porque é obrigatório colocar farinha e ovos no computador."
        ],
        correct: "B", tip_rh: "Analogia central da aula: escreve o bloco uma vez (receita) e reutiliza várias vezes (faz o bolo)."
      },
      {
        id: 28, category: "Técnica", sub: "Funções & Modularização", title: "Definir versus Chamar uma Função",
        question: "Qual a diferença entre 'definir uma função' e 'chamar uma função' em Python?",
        options: [
          "A) São exatamente a mesma coisa.",
          "B) Definir é criar o código da função (`def saudacao():`); chamar é executar esse código (`saudacao()`).",
          "C) Chamar é quando ocorre um erro e definir é quando o código compila.",
          "D) Definir é em português e chamar é em inglês."
        ],
        correct: "B", tip_rh: "O aluno deve entender que `def` cria o molde, e os parênteses `()` colocam o bloco em ação."
      },
      {
        id: 29, category: "Técnica", sub: "Funções & Modularização", title: "Parâmetros em Funções",
        question: "Em uma função `calcular_media(nota1, nota2)`, o que representam `nota1` e `nota2`?",
        options: [
          "A) São comentários que o programa não lê.",
          "B) São parâmetros (portas de entrada) que recebem os valores externos necessários para o cálculo.",
          "C) São comandos para fechar o sistema operacional.",
          "D) São textos fixos que nunca mudam."
        ],
        correct: "B", tip_rh: "Parâmetros permitem que a função receba dados diferentes a cada chamada."
      },
      {
        id: 30, category: "Técnica", sub: "Funções & Modularização", title: "O Comando return",
        question: "Qual é a função da palavra-chave `return` dentro de uma função em Python?",
        options: [
          "A) Desligar o monitor do computador.",
          "B) Encerrar a função e devolver o valor calculado para a parte do programa que a chamou.",
          "C) Reiniciar o programa do início.",
          "D) Imprimir o texto na tela obrigatoriamente."
        ],
        correct: "B", tip_rh: "`return` envia o resultado da função de volta para o código principal."
      },
      {
        id: 31, category: "Técnica", sub: "Funções & Modularização", title: "Escopo de Variáveis (Local x Global)",
        question: "O que acontece com uma variável criada DENTRO de uma função (variável local) após a função terminar?",
        options: [
          "A) Ela se torna global e pode ser acessada em qualquer arquivo.",
          "B) Ela é apagada da memória e não pode ser acessada fora da função.",
          "C) Ela é gravada no banco de dados automaticamente.",
          "D) O programa trava com tela azul."
        ],
        correct: "B", tip_rh: "Escopo local: a variável 'vive' e existe apenas dentro da execução daquela função específica."
      },
      {
        id: 32, category: "Técnica", sub: "Funções & Modularização", title: "Vantagem da Modularização para Manutenção",
        question: "Se a regra de cálculo de desconto de uma loja mudar, qual a grande vantagem do código estar modularizado com funções?",
        options: [
          "A) Ter que reescrever todo o sistema do zero.",
          "B) Precisar alterar a fórmula em um único lugar: dentro da função responsável pelo cálculo.",
          "C) Nenhuma vantagem, modularização é apenas estética.",
          "D) Não precisar fazer nada porque o Python adivinha a nova regra."
        ],
        correct: "B", tip_rh: "Manutenção centralizada e reaproveitamento de código são os pilares da engenharia de software."
      }
    ];

    let availableQuestions = [...QUESTIONS_DATA];
    let usedQuestions = [];
    let currentQuestion = null;
    let candidateCount = 1;

    let timerDuration = 180;
    let timerRemaining = 180;
    let timerInterval = null;
    let isTimerRunning = false;

    function showScreen(screenId) {
      document.querySelectorAll('.view-screen').forEach(s => s.classList.remove('active'));
      const target = document.getElementById(screenId);
      if (target) {
        target.classList.add('active');
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }
    }

    function startInterviewSession() {
      showScreen('screen-interview');
      if (!currentQuestion) {
        drawNewQuestion();
      }
      resetTimer(180);
    }

    function goToHome() {
      if (confirm('Deseja voltar para a página inicial de apresentação?')) {
        pauseTimer();
        showScreen('screen-home');
      }
    }

    function updatePoolStatus() {
      const statusEl = document.getElementById('pool-status-text');
      statusEl.innerHTML = `Banco: <strong>${availableQuestions.length}</strong> disponíveis | <strong>${usedQuestions.length}</strong> realizadas`;
    }

    function drawNewQuestion() {
      if (availableQuestions.length === 0) {
        alert('Todas as 32 questões do banco já foram sorteadas! O banco será reiniciado automaticamente para novas rodadas.');
        availableQuestions = [...QUESTIONS_DATA];
        usedQuestions = [];
      }

      const randomIndex = Math.floor(Math.random() * availableQuestions.length);
      currentQuestion = availableQuestions.splice(randomIndex, 1)[0];
      usedQuestions.push(currentQuestion);

      renderQuestionCard(currentQuestion);
      updatePoolStatus();
      goToStep(1);
    }

    function renderQuestionCard(q) {
      const catBadge = document.getElementById('card-category-badge');
      catBadge.textContent = q.category;
      catBadge.className = 'category-tag ' + (q.category === 'Comportamental' ? 'tag-comportamental' : 'tag-tecnica');

      document.getElementById('card-sub-title').textContent = `${q.sub} • ${q.title}`;
      document.getElementById('question-text').textContent = q.question;

      const optionsContainer = document.getElementById('options-container');
      optionsContainer.innerHTML = '';
      q.options.forEach(opt => {
        const optDiv = document.createElement('div');
        optDiv.className = 'option-item';
        optDiv.textContent = opt;
        if (opt.startsWith(q.correct + ')')) {
          optDiv.dataset.isCorrect = "true";
        }
        optionsContainer.appendChild(optDiv);
      });

      const correctOptText = q.options.find(o => o.startsWith(q.correct + ')')) || '';
      document.getElementById('correct-option-label').textContent = `Alternativa Correta: ${q.correct}`;
      document.getElementById('correct-option-text').textContent = correctOptText;
      document.getElementById('tip-rh-text').textContent = q.tip_rh;
    }

    function goToStep(stepNum) {
      document.querySelectorAll('.step-section').forEach(el => el.classList.remove('active'));
      const targetStep = document.getElementById(`step-${stepNum}-view`);
      if (targetStep) targetStep.classList.add('active');

      document.getElementById('step-indicator-text').textContent = `Passo ${stepNum} de 3`;

      if (stepNum === 3) {
        document.querySelectorAll('.option-item').forEach(item => {
          if (item.dataset.isCorrect === "true") {
            item.classList.add('correct-revealed');
          }
        });
      }
    }

    function nextCandidate() {
      candidateCount++;
      document.getElementById('candidate-label').textContent = `Candidato #${candidateCount}`;
      resetTimer(180);
      drawNewQuestion();
    }

    function formatTime(seconds) {
      const mins = Math.floor(seconds / 60);
      const secs = seconds % 60;
      return `${mins.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
    }

    function updateTimerDisplay() {
      const display = document.getElementById('timer-text');
      display.textContent = formatTime(timerRemaining);
      if (timerRemaining <= 30 && timerRemaining > 0) {
        display.classList.add('danger');
      } else {
        display.classList.remove('danger');
      }
    }

    function toggleTimer() {
      if (isTimerRunning) pauseTimer();
      else startTimer();
    }

    function startTimer() {
      if (isTimerRunning) return;
      isTimerRunning = true;
      document.getElementById('btn-timer-toggle').textContent = 'Pausar';
      timerInterval = setInterval(() => {
        if (timerRemaining > 0) {
          timerRemaining--;
          updateTimerDisplay();
        } else {
          pauseTimer();
          alert('⏱️ Tempo limite de entrevista atingido para este candidato!');
        }
      }, 1000);
    }

    function pauseTimer() {
      isTimerRunning = false;
      clearInterval(timerInterval);
      const btn = document.getElementById('btn-timer-toggle');
      if (btn) btn.textContent = 'Iniciar';
    }

    function resetTimer(seconds = 180) {
      pauseTimer();
      timerDuration = seconds;
      timerRemaining = seconds;
      updateTimerDisplay();
    }

    function openHelpModal() { document.getElementById('help-modal').classList.add('active'); }
    function closeHelpModal() { document.getElementById('help-modal').classList.remove('active'); }
    function closeHelpModalOnBackdrop(e) { if (e.target.id === 'help-modal') closeHelpModal(); }

    document.addEventListener('DOMContentLoaded', () => { updatePoolStatus(); });
  </script>
</body>
</html>
