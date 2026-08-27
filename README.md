<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Nexus Virtual Solutions | Simulação de Entrevista RH</title>
    
    <!-- Google Fonts: Plus Jakarta Sans -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-page: #FAF7F2;
            --bg-card: #FFFFFF;
            --bg-card-subtle: #F5F1E9;
            --bg-card-highlight: #FFFDF9;
            
            --text-primary: #1F2937;
            --text-secondary: #4B5563;
            --text-muted: #6B7280;
            
            --primary: #1E3A8A;
            --primary-light: #3B82F6;
            --primary-bg: #EFF6FF;
            
            --accent: #D97706;
            --accent-light: #F59E0B;
            --accent-bg: #FEF3C7;
            
            --success: #059669;
            --success-bg: #ECFDF5;
            --success-border: #A7F3D0;
            
            --border-subtle: #E5E0D8;
            --border-hover: #D1C9BE;
            
            --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.04);
            --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.06);
            --shadow-lg: 0 14px 36px rgba(0, 0, 0, 0.08);
            
            --radius-sm: 10px;
            --radius-md: 16px;
            --radius-lg: 24px;
            --radius-full: 9999px;
            
            --transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: 'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background-color: var(--bg-page);
            color: var(--text-primary);
            line-height: 1.5;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        header {
            background-color: var(--bg-card);
            border-bottom: 1px solid var(--border-subtle);
            padding: 14px 20px;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: var(--shadow-sm);
        }

        .header-container {
            max-width: 760px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .brand-logo {
            width: 38px;
            height: 38px;
            background: linear-gradient(135deg, var(--primary) 0%, #1E40AF 100%);
            border-radius: var(--radius-sm);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #FFFFFF;
            font-weight: 800;
            font-size: 18px;
            box-shadow: 0 4px 10px rgba(30, 58, 138, 0.2);
        }

        .brand-text h1 {
            font-size: 16px;
            font-weight: 700;
            color: var(--primary);
            letter-spacing: -0.3px;
            line-height: 1.2;
        }

        .brand-text p {
            font-size: 11px;
            font-weight: 500;
            color: var(--text-muted);
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .btn-icon {
            background-color: var(--bg-card-subtle);
            border: 1px solid var(--border-subtle);
            color: var(--text-secondary);
            padding: 7px 12px;
            border-radius: var(--radius-full);
            font-size: 12px;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 6px;
            transition: var(--transition);
        }

        .btn-icon:hover {
            background-color: var(--border-subtle);
            color: var(--text-primary);
        }

        main {
            flex: 1;
            max-width: 760px;
            width: 100%;
            margin: 0 auto;
            padding: 16px 16px 40px;
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .status-bar {
            background-color: var(--bg-card);
            border: 1px solid var(--border-subtle);
            border-radius: var(--radius-md);
            padding: 12px 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: var(--shadow-sm);
        }

        .timer-box {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .timer-display {
            font-size: 18px;
            font-weight: 700;
            font-variant-numeric: tabular-nums;
            color: var(--primary);
            background-color: var(--primary-bg);
            padding: 4px 10px;
            border-radius: 8px;
            border: 1px solid #BFDBFE;
        }

        .timer-display.warning {
            color: #DC2626;
            background-color: #FEE2E2;
            border-color: #FCA5A5;
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.6; }
            100% { opacity: 1; }
        }

        .timer-controls {
            display: flex;
            gap: 6px;
        }

        .btn-timer {
            background: none;
            border: 1px solid var(--border-subtle);
            padding: 4px 8px;
            border-radius: 6px;
            font-size: 11px;
            font-weight: 600;
            cursor: pointer;
            background-color: #FFFFFF;
        }

        .candidate-tracker {
            text-align: right;
        }

        .tracker-title {
            font-size: 11px;
            font-weight: 600;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .tracker-stats {
            font-size: 13px;
            font-weight: 700;
            color: var(--text-primary);
        }

        .category-tabs {
            display: flex;
            gap: 8px;
            overflow-x: auto;
            padding-bottom: 2px;
            scrollbar-width: none;
        }
        .category-tabs::-webkit-scrollbar {
            display: none;
        }

        .tab-btn {
            padding: 8px 14px;
            border-radius: var(--radius-full);
            font-size: 12px;
            font-weight: 600;
            border: 1px solid var(--border-subtle);
            background-color: var(--bg-card);
            color: var(--text-secondary);
            cursor: pointer;
            white-space: nowrap;
            transition: var(--transition);
        }

        .tab-btn.active {
            background-color: var(--primary);
            color: #FFFFFF;
            border-color: var(--primary);
            box-shadow: 0 2px 8px rgba(30, 58, 138, 0.25);
        }

        .flashcard-wrapper {
            position: relative;
            perspective: 1000px;
        }

        .flashcard {
            background-color: var(--bg-card);
            border: 1px solid var(--border-subtle);
            border-radius: var(--radius-lg);
            padding: 24px;
            box-shadow: var(--shadow-md);
            display: flex;
            flex-direction: column;
            gap: 18px;
            position: relative;
            transition: var(--transition);
        }

        .steps-nav {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background-color: var(--bg-card-subtle);
            padding: 4px;
            border-radius: var(--radius-full);
            margin-bottom: 6px;
        }

        .step-item {
            flex: 1;
            text-align: center;
            padding: 6px 4px;
            font-size: 11px;
            font-weight: 700;
            color: var(--text-muted);
            border-radius: var(--radius-full);
            transition: var(--transition);
        }

        .step-item.active {
            background-color: #FFFFFF;
            color: var(--primary);
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.06);
        }

        .step-item.completed {
            color: var(--success);
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            gap: 12px;
        }

        .badge-category {
            font-size: 11px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            padding: 4px 10px;
            border-radius: var(--radius-full);
            background-color: var(--accent-bg);
            color: var(--accent);
            border: 1px solid #FDE68A;
        }

        .badge-category.tech {
            background-color: var(--primary-bg);
            color: var(--primary);
            border-color: #BFDBFE;
        }

        .q-number {
            font-size: 12px;
            font-weight: 600;
            color: var(--text-muted);
        }

        .card-title {
            font-size: 18px;
            font-weight: 700;
            color: var(--text-primary);
            line-height: 1.35;
        }

        .phase-question {
            background-color: var(--bg-card-highlight);
            border-left: 4px solid var(--primary);
            padding: 16px 18px;
            border-radius: 0 var(--radius-sm) var(--radius-sm) 0;
            font-size: 16px;
            font-weight: 600;
            color: var(--text-primary);
            line-height: 1.5;
        }

        .rh-reader-tip {
            font-size: 12px;
            font-weight: 500;
            color: var(--text-muted);
            display: flex;
            align-items: center;
            gap: 6px;
            margin-top: 4px;
        }

        .phase-options {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .option-card {
            background-color: #FFFFFF;
            border: 1.5px solid var(--border-subtle);
            border-radius: var(--radius-md);
            padding: 12px 16px;
            font-size: 14px;
            font-weight: 500;
            color: var(--text-primary);
            display: flex;
            align-items: flex-start;
            gap: 10px;
            transition: var(--transition);
        }

        .option-card.correct-highlight {
            background-color: var(--success-bg);
            border-color: var(--success);
            color: #065F46;
            font-weight: 600;
        }

        .phase-answer {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .answer-badge {
            background-color: var(--success-bg);
            border: 1px solid var(--success-border);
            padding: 14px 18px;
            border-radius: var(--radius-md);
            color: #065F46;
        }

        .answer-badge h4 {
            font-size: 14px;
            font-weight: 700;
            margin-bottom: 4px;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .answer-badge p {
            font-size: 14px;
            font-weight: 500;
        }

        .rh-evaluation-box {
            background-color: #FEF3C7;
            border: 1px solid #FDE68A;
            padding: 14px 18px;
            border-radius: var(--radius-md);
            color: #92400E;
        }

        .rh-evaluation-box h4 {
            font-size: 13px;
            font-weight: 700;
            margin-bottom: 4px;
            display: flex;
            align-items: center;
            gap: 6px;
            text-transform: uppercase;
            letter-spacing: 0.3px;
        }

        .rh-evaluation-box p {
            font-size: 13px;
            font-weight: 500;
            line-height: 1.45;
        }

        .card-actions {
            display: flex;
            gap: 10px;
            margin-top: 8px;
        }

        .btn-action {
            flex: 1;
            padding: 14px 18px;
            border-radius: var(--radius-md);
            font-size: 14px;
            font-weight: 700;
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            transition: var(--transition);
        }

        .btn-primary {
            background-color: var(--primary);
            color: #FFFFFF;
            box-shadow: 0 4px 12px rgba(30, 58, 138, 0.2);
        }

        .btn-primary:hover {
            background-color: #1E40AF;
            transform: translateY(-1px);
        }

        .btn-secondary {
            background-color: var(--bg-card-subtle);
            color: var(--text-secondary);
            border: 1px solid var(--border-subtle);
        }

        .btn-secondary:hover {
            background-color: var(--border-subtle);
            color: var(--text-primary);
        }

        .btn-random {
            background: linear-gradient(135deg, var(--accent) 0%, #B45309 100%);
            color: #FFFFFF;
            box-shadow: 0 4px 12px rgba(217, 119, 6, 0.25);
        }

        .btn-random:hover {
            filter: brightness(1.05);
            transform: translateY(-1px);
        }

        .candidate-control-bar {
            background-color: var(--bg-card);
            border: 1px solid var(--border-subtle);
            border-radius: var(--radius-lg);
            padding: 16px 20px;
            display: flex;
            flex-direction: column;
            gap: 12px;
            box-shadow: var(--shadow-sm);
        }

        .candidate-control-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .candidate-control-header h3 {
            font-size: 14px;
            font-weight: 700;
            color: var(--text-primary);
        }

        .candidate-btns {
            display: flex;
            gap: 10px;
        }

        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(15, 23, 42, 0.5);
            backdrop-filter: blur(4px);
            z-index: 200;
            display: none;
            align-items: center;
            justify-content: center;
            padding: 16px;
        }

        .modal-overlay.active {
            display: flex;
        }

        .modal-content {
            background-color: #FFFFFF;
            border-radius: var(--radius-lg);
            max-width: 600px;
            width: 100%;
            max-height: 88vh;
            overflow-y: auto;
            padding: 24px;
            box-shadow: var(--shadow-lg);
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid var(--border-subtle);
            padding-bottom: 12px;
        }

        .modal-header h2 {
            font-size: 18px;
            font-weight: 800;
            color: var(--primary);
        }

        .btn-close {
            background: none;
            border: none;
            font-size: 22px;
            color: var(--text-muted);
            cursor: pointer;
        }

        .modal-body {
            font-size: 14px;
            color: var(--text-secondary);
            line-height: 1.6;
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .info-card {
            background-color: var(--bg-page);
            border-left: 4px solid var(--accent);
            padding: 12px 14px;
            border-radius: 0 8px 8px 0;
        }

        .info-card h4 {
            font-size: 13px;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 4px;
        }

        .rubric-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 12px;
        }

        .rubric-item {
            background-color: var(--bg-card-subtle);
            padding: 12px;
            border-radius: var(--radius-sm);
            border: 1px solid var(--border-subtle);
        }

        .rubric-label {
            font-weight: 700;
            font-size: 13px;
            margin-bottom: 4px;
            display: block;
        }

        .rubric-desc {
            font-size: 12px;
            color: var(--text-muted);
            margin-bottom: 8px;
        }

        .star-rating {
            display: flex;
            gap: 6px;
        }

        .star-btn {
            background: #FFFFFF;
            border: 1px solid var(--border-subtle);
            width: 32px;
            height: 32px;
            border-radius: 6px;
            font-weight: 700;
            font-size: 12px;
            color: var(--text-secondary);
            cursor: pointer;
        }

        .star-btn.selected {
            background-color: var(--accent);
            color: #FFFFFF;
            border-color: var(--accent);
        }

        footer {
            text-align: center;
            padding: 24px 16px;
            background-color: var(--bg-card);
            border-top: 1px solid var(--border-subtle);
            font-size: 12px;
            color: var(--text-muted);
            margin-top: auto;
        }

        footer strong {
            color: var(--text-primary);
        }

        @media (max-width: 480px) {
            .card-title {
                font-size: 16px;
            }
            .phase-question {
                font-size: 15px;
            }
            .btn-action {
                padding: 12px 14px;
                font-size: 13px;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="header-container">
            <div class="brand">
                <div class="brand-logo">N</div>
                <div class="brand-text">
                    <h1>Nexus Virtual Solutions</h1>
                    <p>Painel do Selecionador (RH) | Simulação de Entrevista</p>
                </div>
            </div>
            <div class="header-actions">
                <button class="btn-icon" onclick="openModal('briefingModal')">
                    📋 <span>Instruções</span>
                </button>
                <button class="btn-icon" onclick="openModal('evaluationModal')">
                    ⭐ <span>Ficha RH</span>
                </button>
            </div>
        </div>
    </header>

    <main>
        <section class="status-bar">
            <div class="timer-box">
                <div class="timer-display" id="timerDisplay">03:00</div>
                <div class="timer-controls">
                    <button class="btn-timer" id="timerBtn" onclick="toggleTimer()">▶ Iniciar</button>
                    <button class="btn-timer" onclick="resetTimer()">↺ Zerar</button>
                </div>
            </div>
            <div class="candidate-tracker">
                <div class="tracker-title">Questão do Candidato</div>
                <div class="tracker-stats" id="candidateStat">Q 1 de 3</div>
            </div>
        </section>

        <nav class="category-tabs">
            <button class="tab-btn active" onclick="setCategoryFilter('TODAS')">Todas as Questões (<span id="totalCount">0</span>)</button>
            <button class="tab-btn" onclick="setCategoryFilter('Comportamental')">💬 Comportamental (<span id="compCount">0</span>)</button>
            <button class="tab-btn" onclick="setCategoryFilter('Técnica Básica')">💻 Técnica Básica (<span id="techCount">0</span>)</button>
        </nav>

        <section class="flashcard-wrapper">
            <div class="flashcard" id="flashcard">
                
                <div class="steps-nav">
                    <div class="step-item active" id="stepIndicator1">1. Pergunta</div>
                    <div class="step-item" id="stepIndicator2">2. Alternativas</div>
                    <div class="step-item" id="stepIndicator3">3. Gabarito & Dica RH</div>
                </div>

                <div class="card-header">
                    <div>
                        <span class="badge-category" id="cardBadge">Comportamental</span>
                        <span style="font-size: 11px; color: var(--text-muted); margin-left: 6px;" id="cardSub">Apresentação</span>
                    </div>
                    <div class="q-number" id="cardIndexTracker">ID #1</div>
                </div>

                <h2 class="card-title" id="cardTitle">Título da Questão</h2>

                <div class="phase-question" id="cardQuestion">
                    Carregando pergunta...
                </div>
                <div class="rh-reader-tip" id="rhTipReader">
                    🎙️ <em>Direção: Leia esta pergunta em voz alta para o(a) candidato(a).</em>
                </div>

                <div class="phase-options" id="optionsContainer" style="display: none;"></div>

                <div class="phase-answer" id="answerContainer" style="display: none;">
                    <div class="answer-badge">
                        <h4>✅ Resposta Esperada: <span id="correctOptionLetter">B</span></h4>
                        <p id="correctOptionText">Descrição da resposta correta.</p>
                    </div>
                    <div class="rh-evaluation-box">
                        <h4>🎯 O que o RH deve observar na fala do aluno:</h4>
                        <p id="rhGuidanceText">Dica para a direção avaliar a segurança, vocabulário e clareza.</p>
                    </div>
                </div>

                <div class="card-actions">
                    <button class="btn-action btn-secondary" id="btnBackStep" onclick="prevStep()" style="display: none;">
                        ⬅ Voltar
                    </button>
                    <button class="btn-action btn-primary" id="btnNextStep" onclick="nextStep()">
                        Ver Alternativas ➔
                    </button>
                </div>

            </div>
        </section>

        <section class="candidate-control-bar">
            <div class="candidate-control-header">
                <div>
                    <h3>🎲 Sorteador Sem Repetição</h3>
                    <p style="font-size: 12px; color: var(--text-muted);">
                        Restam <strong id="availablePoolCount" style="color: var(--primary);">0</strong> questões inéditas no banco.
                    </p>
                </div>
                <button class="btn-action btn-random" style="flex: none; padding: 10px 16px; font-size: 13px;" onclick="drawNextQuestion(true)">
                    🎲 Sortear Próxima
                </button>
            </div>
            
            <div class="candidate-btns">
                <button class="btn-action btn-secondary" onclick="nextCandidate()">
                    👤 Próximo Candidato (Reset 3 Qs)
                </button>
                <button class="btn-action btn-secondary" style="flex: 0.6;" onclick="resetQuestionPool()" title="Reinicia todas as questões descartadas">
                    🔄 Reiniciar Banco
                </button>
            </div>
        </section>
    </main>

    <div class="modal-overlay" id="briefingModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>🏢 Guia Rápido do Selecionador (RH)</h2>
                <button class="btn-close" onclick="closeModal('briefingModal')">&times;</button>
            </div>
            <div class="modal-body">
                <div class="info-card">
                    <h4>Cenário da Empresa Fictícia</h4>
                    <p>A <strong>Nexus Virtual Solutions</strong> é uma empresa que desenvolve sites, aplicativos mobile e sistemas em nuvem. Vocês (Direção da Escola) estão entrevistando candidatos para vagas de <strong>Estágio / Desenvolvedor(a) Júnior</strong>.</p>
                </div>

                <div class="info-card" style="border-left-color: var(--primary);">
                    <h4>Como conduzir a simulação em 3 minutos:</h4>
                    <ol style="margin-left: 18px; font-size: 13px;">
                        <li><strong>Acolhimento (30s):</strong> Dê boas-vindas ao aluno e inicie o cronômetro no topo.</li>
                        <li><strong>Perguntas (2 min):</strong> Faça 2 a 3 perguntas sorteadas pelo app.</li>
                        <li><strong>Dica Pedagógica:</strong> O foco principal é a <strong>segurança, comunicação clara, honestidade e sociabilidade</strong>.</li>
                        <li><strong>Fechamento & Feedback (30s):</strong> Utilize o método Sanduíche: 1 elogio sincero, 1 ponto a lapidar e 1 incentivo!</li>
                    </ol>
                </div>
                
                <p style="font-size: 12px; color: var(--text-muted); text-align: center;">
                    <em>Idealizado pelo Prof. Thiago Fernando para a formação integral dos estudantes.</em>
                </p>
            </div>
            <button class="btn-action btn-primary" onclick="closeModal('briefingModal')">Entendido, Voltar à Entrevista</button>
        </div>
    </div>

    <div class="modal-overlay" id="evaluationModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>⭐ Ficha Rápida de Avaliação (1 Minuto)</h2>
                <button class="btn-close" onclick="closeModal('evaluationModal')">&times;</button>
            </div>
            <div class="modal-body">
                <p style="font-size: 13px;">Use esta rubrica rápida para avaliar a desenvoltura geral do candidato durante a entrevista:</p>
                
                <div class="rubric-grid">
                    <div class="rubric-item">
                        <span class="rubric-label">1. Postura & Comunicação Oral</span>
                        <div class="rubric-desc">Clareza na fala, contato visual, ausência de gírias excessivas e formalidade suave.</div>
                        <div class="star-rating">
                            <button class="star-btn" onclick="rate(this)">1</button>
                            <button class="star-btn" onclick="rate(this)">2</button>
                            <button class="star-btn" onclick="rate(this)">3</button>
                            <button class="star-btn" onclick="rate(this)">4</button>
                            <button class="star-btn selected" onclick="rate(this)">5</button>
                        </div>
                    </div>

                    <div class="rubric-item">
                        <span class="rubric-label">2. Raciocínio Lógico & Conceitos de TI</span>
                        <div class="rubric-desc">Compreensão de funções (receita), listas/vetores e organização de dados.</div>
                        <div class="star-rating">
                            <button class="star-btn" onclick="rate(this)">1</button>
                            <button class="star-btn" onclick="rate(this)">2</button>
                            <button class="star-btn" onclick="rate(this)">3</button>
                            <button class="star-btn selected" onclick="rate(this)">4</button>
                            <button class="star-btn" onclick="rate(this)">5</button>
                        </div>
                    </div>

                    <div class="rubric-item">
                        <span class="rubric-label">3. Maturidade & Recepção de Feedback</span>
                        <div class="rubric-desc">Mentalidade de crescimento ao lidar com erros e disposição para aprender.</div>
                        <div class="star-rating">
                            <button class="star-btn" onclick="rate(this)">1</button>
                            <button class="star-btn" onclick="rate(this)">2</button>
                            <button class="star-btn" onclick="rate(this)">3</button>
                            <button class="star-btn selected" onclick="rate(this)">4</button>
                            <button class="star-btn" onclick="rate(this)">5</button>
                        </div>
                    </div>

                    <div class="rubric-item">
                        <span class="rubric-label">4. Proatividade & Ética</span>
                        <div class="rubric-desc">Iniciativa para propor soluções e respeito à confidencialidade e prazos.</div>
                        <div class="star-rating">
                            <button class="star-btn" onclick="rate(this)">1</button>
                            <button class="star-btn" onclick="rate(this)">2</button>
                            <button class="star-btn" onclick="rate(this)">3</button>
                            <button class="star-btn" onclick="rate(this)">4</button>
                            <button class="star-btn selected" onclick="rate(this)">5</button>
                        </div>
                    </div>
                </div>

                <div class="info-card" style="background-color: var(--success-bg); border-left-color: var(--success);">
                    <h4 style="color: #065F46;">Dica para o Feedback Final (30 segundos):</h4>
                    <p style="color: #065F46; font-size: 13px;"><em>"Parabéns pela sua segurança na resposta sobre [ponto forte]. Como sugestão para sua carreira, busque apenas [ponto a lapidar]. Temos certeza de que você terá muito sucesso!"</em></p>
                </div>
            </div>
            <button class="btn-action btn-primary" onclick="closeModal('evaluationModal')">Fechar Ficha</button>
        </div>
    </div>

    <footer>
        <p><strong>Simulação de Recrutamento & Seleção</strong> | Educação Profissional Paulista</p>
        <p style="margin-top: 4px;">Mediação Pedagógica: <strong>Prof. Thiago Fernando</strong> (Graduando em Eng. de Computação | Licenciado em Matemática)</p>
    </footer>

    <script>
        const QUESTIONS_DATA = [
            {
                "id": 1,
                "category": "Comportamental",
                "sub": "Persona Profissional",
                "title": "Apresentação Pessoal em Entrevista",
                "question": "Ao iniciar a entrevista e ser convidado(a) a falar um pouco sobre você e seus interesses, qual postura e fala são as mais adequadas?",
                "options": [
                    "A) Falar de forma muito informal, dizendo apenas: 'Tipo assim... eu faço várias coisas, ajudo geral lá e sou bem de boa'.",
                    "B) Apresentar-se com clareza e respeito, destacando seus estudos na escola técnica, facilidade de trabalhar em equipe e motivação para aprender.",
                    "C) Dizer apenas 'Não sei muito o que falar' e esperar o entrevistador adivinhar.",
                    "D) Focar em assuntos puramente íntimos e reclamações sobre tarefas anteriores."
                ],
                "correct": "B",
                "tip_rh": "Observe a oratória, a segurança e a capacidade de conectar os estudos escolares ao interesse na empresa de tecnologia. Evite premiar respostas vagas com excesso de gírias."
            },
            {
                "id": 2,
                "category": "Comportamental",
                "sub": "Dress Code & Imagem",
                "title": "Código de Vestimenta na Área de TI",
                "question": "Sobre o Dress Code (código de vestimenta) em empresas modernas de desenvolvimento de software, o que é correto afirmar?",
                "options": [
                    "A) É obrigatório o uso de terno e gravata todos os dias para qualquer programador.",
                    "B) As roupas não importam nada, podendo trabalhar sem qualquer critério ou cuidado.",
                    "C) Geralmente segue um estilo casual ou business casual (flexível e confortável), mantendo sempre o bom senso, a higiene e o alinhamento com a cultura da empresa.",
                    "D) É uma regra fixa idêntica em absolutamente todas as empresas do mundo."
                ],
                "correct": "C",
                "tip_rh": "O candidato deve demonstrar que a imagem profissional envolve bom senso, higiene e adequação à cultura do ambiente de trabalho."
            },
            {
                "id": 3,
                "category": "Comportamental",
                "sub": "Linguagem Corporal",
                "title": "Comunicação Não-Verbal e Postura",
                "question": "Durante a conversa com os selecionadores, qual atitude corporal transmite mais profissionalismo e confiança?",
                "options": [
                    "A) Olhar nos olhos dos entrevistadores, manter a postura ereta e demonstrar atenção ativa.",
                    "B) Ficar mexendo no celular e digitando mensagens durante as perguntas.",
                    "C) Ficar de braços cruzados olhando para o teto ou para o chão.",
                    "D) Ficar com a cabeça debruçada sobre a mesa."
                ],
                "correct": "A",
                "tip_rh": "Avalie a presença e postura do aluno na cadeira: contato visual, serenidade e atenção aos entrevistadores."
            },
            {
                "id": 4,
                "category": "Comportamental",
                "sub": "Etiqueta Corporativa",
                "title": "Postura em Reuniões de Equipe",
                "question": "Em uma reunião de alinhamento com o time sobre a entrega de um sistema, um colega ao lado inicia conversas paralelas insistentes. Como você age?",
                "options": [
                    "A) Entra na conversa paralela e começa a rir alto.",
                    "B) Grita no meio da reunião expondo o colega para o gestor.",
                    "C) Mantém a atenção na reunião e sinaliza discretamente ao colega para conversarem no momento oportuno após a reunião.",
                    "D) Levanta-se e vai embora da sala sem avisar ninguém."
                ],
                "correct": "C",
                "tip_rh": "Demonstra maturidade, respeito à liderança e equilíbrio nas relações interpessoais sem criar conflitos desnecessários."
            },
            {
                "id": 5,
                "category": "Comportamental",
                "sub": "Comunicação Digital",
                "title": "O 'Efeito Suspense' no Chat Profissional",
                "question": "Por que enviar apenas 'Oi, tudo bem?' no Teams/WhatsApp de trabalho e aguardar a resposta para só depois falar o assunto é uma prática ruim?",
                "options": [
                    "A) Porque interrompe a concentração do colega, gera ansiedade e atrasa a solução da dúvida.",
                    "B) Porque o aplicativo bloqueia o usuário após enviar duas mensagens seguidas.",
                    "C) Porque não é permitido dar 'bom dia' no ambiente corporativo.",
                    "D) Não é uma prática ruim; é o padrão exigido por lei."
                ],
                "correct": "A",
                "tip_rh": "Conceito trabalhado em aula: assertividade é enviar a saudação + o contexto + a dúvida objetiva na mesma mensagem para economizar tempo."
            },
            {
                "id": 6,
                "category": "Comportamental",
                "sub": "Comunicação Digital",
                "title": "Boas Práticas no Envio de Áudios",
                "question": "Qual é a recomendação sobre o uso de áudios no WhatsApp profissional da empresa?",
                "options": [
                    "A) Enviar sempre áudios de mais de 4 minutos em vez de escrever.",
                    "B) Priorizar mensagens de texto claras e objetivas; caso o áudio seja realmente necessário, perguntar antes se o colega pode ouvir e ser suscinto.",
                    "C) Mandar áudios com música alta ou barulho ao fundo.",
                    "D) Enviar áudios na madrugada para adiantar o serviço do dia seguinte."
                ],
                "correct": "B",
                "tip_rh": "Verifique se o candidato entende que a mensagem de texto facilita a busca de informações e não interrompe reuniões alheias."
            },
            {
                "id": 7,
                "category": "Comportamental",
                "sub": "Formalidade Suave",
                "title": "A Arte da Formalidade Suave",
                "question": "O que caracteriza a chamada 'formalidade suave' na comunicação com gestores e clientes?",
                "options": [
                    "A) Linguagem excessivamente rebuscada e cheia de gerundismos ('estaremos verificando').",
                    "B) Uma comunicação educada, respeitosa, clara e direta, sem gírias infantis e sem frieza ou artificialidade.",
                    "C) Conversar usando apelidos e gírias de rua como se fossem amigos de infância.",
                    "D) Comunicar-se apenas enviando memes e figurinhas."
                ],
                "correct": "B",
                "tip_rh": "O candidato deve valorizar a clareza, a simplicidade e a educação sem soar robótico ou desleixado."
            },
            {
                "id": 8,
                "category": "Comportamental",
                "sub": "E-mail Corporativo",
                "title": "Assunto Preciso em E-mails",
                "question": "Ao enviar uma atualização do aplicativo para validação da diretoria, qual é o melhor título/assunto para o e-mail?",
                "options": [
                    "A) 'Olha aí o negócio'",
                    "B) '(Sem Assunto)'",
                    "C) '[Validação] Módulo de Cadastro de Usuários - Versão 1.2'",
                    "D) 'URGENTE LEIA POR FAVOR HOJE'"
                ],
                "correct": "C",
                "tip_rh": "O assunto correto resume o objetivo entre colchetes, o tema específico e a versão, facilitando a organização da caixa de entrada."
            },
            {
                "id": 9,
                "category": "Comportamental",
                "sub": "E-mail Corporativo",
                "title": "Uso Cauteloso do 'Responder a Todos'",
                "question": "Quando você DEVE EVITAR utilizar a opção 'Responder a Todos' em uma conversa por e-mail?",
                "options": [
                    "A) Quando a informação for relevante para todo o time do projeto.",
                    "B) Quando a resposta for apenas um 'Obrigado(a)' pessoal ou uma dúvida pontual direcionada somente ao remetente.",
                    "C) Quando o diretor pedir para todos confirmarem a presença.",
                    "D) Quando o e-mail tiver sido enviado para um grupo de avisos gerais."
                ],
                "correct": "B",
                "tip_rh": "Evita lotar a caixa de correio de dezenas de colaboradores com mensagens que não dizem respeito a eles."
            },
            {
                "id": 10,
                "category": "Comportamental",
                "sub": "Comunicação Digital",
                "title": "Horários de Comunicação e Respeito ao Descanso",
                "question": "Você terminou uma tarefa no código às 23h de uma terça-feira. Como deve proceder para avisar o líder da equipe?",
                "options": [
                    "A) Ligar no telefone particular do líder até ele atender.",
                    "B) Enviar mensagens no WhatsApp marcando como urgente com vários pontos de exclamação.",
                    "C) Registrar a entrega na ferramenta de tarefas ou programar o e-mail/mensagem para o início do horário comercial na manhã seguinte.",
                    "D) Postar nos stories das redes sociais cobrando retorno da empresa."
                ],
                "correct": "C",
                "tip_rh": "Demonstra maturidade em relação ao respeito aos limites de trabalho e equilíbrio profissional."
            },
            {
                "id": 11,
                "category": "Comportamental",
                "sub": "Feedback Profissional",
                "title": "Mentalidade de Crescimento ao Receber Correções",
                "question": "Seu gestor revisou seu primeiro projeto e apontou que as telas precisam de melhorias visuais e ajustes na lógica. Qual é a reação esperada de um profissional?",
                "options": [
                    "A) Ficar irritado, dizer que o gestor está com perseguição e não mexer no projeto.",
                    "B) Ouvir com atenção, entender os pontos levantados como oportunidade de evolução (mentalidade de crescimento) e pedir orientações práticas.",
                    "C) Dizer que vai refazer, mas ignorar todas as sugestões.",
                    "D) Desistir da vaga e pedir demissão no mesmo dia."
                ],
                "correct": "B",
                "tip_rh": "Capacidade essencial: maturidade emocional para receber feedback construtivo sem adotar postura defensiva."
            },
            {
                "id": 12,
                "category": "Comportamental",
                "sub": "Feedback Profissional",
                "title": "O Modelo SCI (Situação, Comportamento, Impacto)",
                "question": "Ao dar um retorno sobre o trabalho de um colega usando o modelo SCI, o que você deve destacar?",
                "options": [
                    "A) Julgamentos sobre o caráter ou personalidade da pessoa.",
                    "B) Fatos objetivos: o contexto (Situação), a atitude observada (Comportamento) e a consequência para o projeto (Impacto).",
                    "C) Comentários sarcásticos na frente dos outros membros da equipe.",
                    "D) Apenas fofocas ouvidas nos corredores."
                ],
                "correct": "B",
                "tip_rh": "O feedback de qualidade é técnico e baseado em fatos concretos, mantendo o respeito e a parceria."
            },
            {
                "id": 13,
                "category": "Comportamental",
                "sub": "Ética & Compliance",
                "title": "Sigilo e Confidencialidade de Dados",
                "question": "Durante os testes de um sistema, você encontra dados reais de clientes (endereços, CPFs, senhas). Qual é a sua responsabilidade ética?",
                "options": [
                    "A) Salvar os dados no pendrive pessoal para mostrar aos amigos.",
                    "B) Manter total confidencialidade e sigilo, utilizando os dados estritamente para o teste autorizado e seguindo as normas da empresa.",
                    "C) Compartilhar prints das informações em grupos de redes sociais.",
                    "D) Utilizar os contatos para oferecer serviços particulares."
                ],
                "correct": "B",
                "tip_rh": "Avalie o compromisso com a ética, compliance e respeito à privacidade de dados (LGPD)."
            },
            {
                "id": 14,
                "category": "Comportamental",
                "sub": "Ética Profissional",
                "title": "Transparência ao Cometer um Erro",
                "question": "Você cometeu um engano no código e uma página importante do site ficou fora do ar. Qual é a conduta ética correta?",
                "options": [
                    "A) Culpar outro colega de equipe para não levar bronca.",
                    "B) Apagar os registros e fingir que foi um ataque hacker externo.",
                    "C) Assumir o erro com transparência, comunicar o líder imediatamente e focar em encontrar a solução rápida.",
                    "D) Não falar nada e esperar alguém descobrir por conta própria."
                ],
                "correct": "C",
                "tip_rh": "Assumir responsabilidades por falhas e focar na solução constrói confiança sólida com a liderança."
            },
            {
                "id": 15,
                "category": "Comportamental",
                "sub": "Proatividade",
                "title": "Proatividade na Solução de Problemas",
                "question": "Você notou que os clientes estão tendo dificuldades para encontrar o botão de 'Finalizar Pedido' no site. O que é uma postura proativa?",
                "options": [
                    "A) Ignorar o fato, pois você não foi contratado para cuidar de design.",
                    "B) Analisar o problema, documentar onde os usuários estão travando e sugerir uma melhoria prática ao gestor.",
                    "C) Reclamar nas redes sociais que a empresa faz sistemas ruins.",
                    "D) Aguardar a chefia notar a queda nas vendas para fazer algo."
                ],
                "correct": "B",
                "tip_rh": "Proatividade é antecipar problemas e propor soluções viáveis antes que virem prejuízo."
            },
            {
                "id": 16,
                "category": "Comportamental",
                "sub": "Proatividade",
                "title": "Gestão de Prazos e Imprevistos",
                "question": "Sua máquina de trabalho apresentou um defeito técnico e você não conseguirá entregar a tarefa no prazo combinado. O que fazer?",
                "options": [
                    "A) Avisar a liderança imediatamente, explicar o ocorrido com clareza e propor um novo prazo viável.",
                    "B) Deixar o prazo vencer e esperar o gestor vir perguntar o que aconteceu.",
                    "C) Faltar na data da entrega para evitar cobranças.",
                    "D) Dizer que entregou tudo perfeitamente mesmo sem ter feito."
                ],
                "correct": "A",
                "tip_rh": "Demonstra responsabilidade, comunicação preventiva e respeito com o cronograma da equipe."
            },
            {
                "id": 17,
                "category": "Técnica Básica",
                "sub": "Vetores (Listas)",
                "title": "Por que Usar Vetores (Listas)?",
                "question": "Em um sistema que gerencia 50 produtos, por que usamos uma lista/vetor em vez de criar 50 variáveis soltas (prod1, prod2, prod3...)?",
                "options": [
                    "A) Porque o computador não aceita nomes de variáveis que terminem em números.",
                    "B) Porque o vetor armazena múltiplos dados relacionados em uma única estrutura, tornando o código mais limpo, organizado e fácil de percorrer.",
                    "C) Porque variáveis normais são apagadas após 1 minuto de uso.",
                    "D) Porque vetores só servem para somar notas de matemática."
                ],
                "correct": "B",
                "tip_rh": "Conceito visto na Semana 15: vetores agrupam dados do mesmo tipo facilitando o processamento em lote."
            },
            {
                "id": 18,
                "category": "Técnica Básica",
                "sub": "Vetores (Listas)",
                "title": "Indexação Base 0 em Programação",
                "question": "Dada a lista `linguagens = ['Python', 'JavaScript', 'HTML']`, qual comando acessa o primeiro elemento ('Python')?",
                "options": [
                    "A) `linguagens[1]`",
                    "B) `linguagens[0]`",
                    "C) `linguagens['primeiro']`",
                    "D) `linguagens.primeiro()`"
                ],
                "correct": "B",
                "tip_rh": "Regra básica universal: no Python e na maioria das linguagens, os índices começam no 0. O primeiro item é sempre `[0]`."
            },
            {
                "id": 19,
                "category": "Técnica Básica",
                "sub": "Vetores (Listas)",
                "title": "Erro de Índice Fora da Faixa (IndexError)",
                "question": "Se temos a lista `itens = ['Mouse', 'Teclado']` (tamanho 2) e tentamos executar `print(itens)`, o que acontece?",
                "options": [
                    "A) O programa cria 3 espaços em branco automaticamente.",
                    "B) Ocorre um erro de índice fora do limite (`IndexError`), pois a posição 5 não existe na lista.",
                    "C) O programa imprime a palavra 'Mouse' repetida.",
                    "D) O computador reinicia sozinho."
                ],
                "correct": "B",
                "tip_rh": "O aluno deve entender que os índices válidos vão de 0 até tamanho-1 (neste caso, índices 0 e 1)."
            },
            {
                "id": 20,
                "category": "Técnica Básica",
                "sub": "Vetores (Listas)",
                "title": "A Função len() em Python",
                "question": "Para que serve a função nativa `len(minha_lista)` ao manipular dados no sistema?",
                "options": [
                    "A) Para apagar os dados da lista.",
                    "B) Para retornar a quantidade total de elementos presentes na lista.",
                    "C) Para somar todos os valores numéricos da lista.",
                    "D) Para duplicar os valores da lista."
                ],
                "correct": "B",
                "tip_rh": "Função fundamental para saber o tamanho de vetores e controlar laços de repetição com segurança."
            },
            {
                "id": 21,
                "category": "Técnica Básica",
                "sub": "Vetores (Listas)",
                "title": "Percorrendo uma Lista com Laço for",
                "question": "Qual comando é o mais prático e elegante para exibir na tela todos os nomes cadastrados na lista `alunos`?",
                "options": [
                    "A) `for aluno in alunos: print(aluno)`",
                    "B) Escrever 50 comandos `print()` manuais um embaixo do outro.",
                    "C) Usar um comando `if` para cada nome.",
                    "D) Criar uma função para cada aluno cadastrado."
                ],
                "correct": "A",
                "tip_rh": "O candidato deve reconhecer o laço `for` como a estrutura padrão para percurso sequencial de listas."
            },
            {
                "id": 22,
                "category": "Técnica Básica",
                "sub": "Vetores (Listas)",
                "title": "Algoritmo de Busca Linear",
                "question": "Como funciona o método de 'Busca Linear' para encontrar um produto em uma lista de estoque?",
                "options": [
                    "A) O sistema adivinha a posição usando inteligência artificial instantânea.",
                    "B) O programa percorre a lista elemento por elemento, do início ao fim, comparando cada item até encontrar o que procura.",
                    "C) O sistema apaga todos os produtos diferentes até sobrar apenas o desejado.",
                    "D) Só funciona se a lista estiver em ordem decrescente."
                ],
                "correct": "B",
                "tip_rh": "Conceito trabalhado na Semana 15 Aula 3: percorrer a lista sequencialmente comparando elemento por elemento."
            },
            {
                "id": 23,
                "category": "Técnica Básica",
                "sub": "Matrizes Bidimensionais",
                "title": "Quando Usar Matriz em vez de Vetor?",
                "question": "Em qual das situações abaixo uma matriz bidimensional (tabela 2D) é mais indicada do que um vetor comum?",
                "options": [
                    "A) Para guardar apenas uma lista simples com os nomes dos dias da semana.",
                    "B) Para organizar uma tabela de notas contendo vários alunos e várias disciplinas (linhas e colunas).",
                    "C) Para armazenar a idade de uma única pessoa.",
                    "D) Para calcular o dobro de um número inteiro."
                ],
                "correct": "B",
                "tip_rh": "Diferença conceitual: vetor = 1 dimensão linear; matriz = 2 dimensões (tabela com linhas e colunas / lista de listas)."
            },
            {
                "id": 24,
                "category": "Técnica Básica",
                "sub": "Matrizes Bidimensionais",
                "title": "Acessando Posições em uma Matriz",
                "question": "Em Python, representamos matrizes como listas de listas. Como acessamos o elemento que está na linha 1 e coluna 2?",
                "options":`",
                    "B) `matriz`",
                    "C) `matriz(1)(2)`",
                    "D) `matriz.linha(1).coluna(2)`"
                ],
                "correct": "B",
                "tip_rh": "Sintaxe correta: primeiro colchete para a linha, segundo colchete para a coluna: `matriz[linha][coluna]`."
            },
            {
                "id": 25,
                "category": "Técnica Básica",
                "sub": "Matrizes Bidimensionais",
                "title": "Laços Aninhados em Matrizes",
                "question": "Por que usamos dois laços `for` (um dentro do outro) ao processar uma matriz?",
                "options": [
                    "A) Porque o primeiro laço percorre as linhas e o segundo laço percorre os elementos (colunas) de cada linha.",
                    "B) Porque um laço serve para somar e o outro para subtrair.",
                    "C) Porque o Python obriga a ter dois laços para o código não travar.",
                    "D) Na verdade, matrizes só podem ser lidas sem laços."
                ],
                "correct": "A",
                "tip_rh": "Compreensão de laços aninhados: estrutura essencial para varrer grades e tabelas bidimensionais."
            },
            {
                "id": 26,
                "category": "Técnica Básica",
                "sub": "Matrizes Bidimensionais",
                "title": "Agregação de Dados em Matrizes",
                "question": "Em uma planilha de vendas de uma loja representada por uma matriz, o que significa 'agregar dados'?",
                "options": [
                    "A) Excluir todas as linhas da matriz.",
                    "B) Resumir vários dados numéricos em informações consolidadas, como calcular a soma total ou a média de vendas de um mês.",
                    "C) Trocar os nomes das variáveis por letras maiúsculas.",
                    "D) Adicionar novas telas no aplicativo."
                ],
                "correct": "B",
                "tip_rh": "Conceito da Semana 16 Aula 3: transformar registros detalhados em estatísticas (soma, média, valor máximo)."
            },
            {
                "id": 27,
                "category": "Técnica Básica",
                "sub": "Funções & Modularização",
                "title": "O que é uma Função (Analogia da Receita)?",
                "question": "Por que dizemos que uma função (`def`) na programação é semelhante a uma 'receita de bolo'?",
                "options": [
                    "A) Porque ela só pode ser executada uma única vez e depois desaparece.",
                    "B) Porque é um bloco de código que você escreve uma vez e pode executar (chamar) sempre que precisar, sem ter que reescrever todos os passos.",
                    "C) Porque funções só servem para calcular ingredientes de culinária.",
                    "D) Porque ela é executada automaticamente sem ninguém chamar."
                ],
                "correct": "B",
                "tip_rh": "Analogia clássica das aulas: define a receita uma vez, invoca para assar o bolo quantas vezes for necessário."
            },
            {
                "id": 28,
                "category": "Técnica Básica",
                "sub": "Funções & Modularização",
                "title": "Definição vs. Chamada de Função",
                "question": "Qual é a diferença entre 'definir' e 'chamar' uma função em Python?",
                "options": [
                    "A) Não existe diferença; os dois termos significam a mesma coisa.",
                    "B) 'Definir' é escrever o código da função com `def nome():`; 'chamar' é colocar o nome com parênteses `nome()` para que ela seja executada.",
                    "C) 'Definir' é para números e 'chamar' é para textos.",
                    "D) 'Chamar' é quando o programa dá erro e 'definir' é quando compila."
                ],
                "correct": "B",
                "tip_rh": "O candidato deve saber que a definição apenas guarda as instruções na memória, enquanto a chamada efetivamente executa o bloco."
            },
            {
                "id": 29,
                "category": "Técnica Básica",
                "sub": "Funções & Modularização",
                "title": "O que são Parâmetros em uma Função?",
                "question": "Na função `def calcular_salario(horas_trabalhadas, valor_hora):`, o que são `horas_trabalhadas` e `valor_hora`?",
                "options": [
                    "A) São parâmetros (portas de entrada) que recebem valores externos para a função poder realizar a conta.",
                    "B) São comentários que o computador ignora.",
                    "C) São erros de digitação do desenvolvedor.",
                    "D) São variáveis que só podem valer zero."
                ],
                "correct": "A",
                "tip_rh": "Parâmetros permitem que a função receba dados diferentes a cada chamada, tornando-a reutilizável e dinâmica."
            },
            {
                "id": 30,
                "category": "Técnica Básica",
                "sub": "Funções & Modularização",
                "title": "O Comando return",
                "question": "Para que serve a palavra-chave `return` dentro de uma função?",
                "options": [
                    "A) Para reiniciar o computador.",
                    "B) Para finalizar a função e devolver o valor calculado para a parte do programa que fez a chamada.",
                    "C) Para apagar o código da tela.",
                    "D) Para pausar o programa para o almoço."
                ],
                "correct": "B",
                "tip_rh": "O comando `return` envia o resultado da função de volta para o algoritmo principal poder armazenar ou exibir."
            },
            {
                "id": 31,
                "category": "Técnica Básica",
                "sub": "Funções & Modularização",
                "title": "Escopo de Variáveis (Local vs Global)",
                "question": "O que acontece com uma variável que é criada DENTRO de uma função (variável local) após o término da função?",
                "options": [
                    "A) Ela se torna pública para toda a internet.",
                    "B) Ela é destruída da memória e não pode mais ser acessada pelo restante do programa.",
                    "C) Ela é salva em um arquivo de texto no disco rígido.",
                    "D) Ela impede que outras funções sejam criadas."
                ],
                "correct": "B",
                "tip_rh": "Conceito de escopo local: a variável 'vive' apenas durante a execução da função onde foi declarada."
            },
            {
                "id": 32,
                "category": "Técnica Básica",
                "sub": "Funções & Modularização",
                "title": "Modularização e Manutenção do Código",
                "question": "Se a regra de cálculo de desconto de uma loja mudar de 5% para 10%, qual é a grande vantagem do código estar modularizado com funções?",
                "options": [
                    "A) Precisar alterar a fórmula apenas em um único lugar: dentro da função responsável pelo cálculo.",
                    "B) Ter que procurar e alterar a regra em dezenas de arquivos e centenas de linhas manuais.",
                    "C) Não precisar fazer nada porque a função adivinha a nova regra por telepatia.",
                    "D) O programa fica mais lento quando tem funções."
                ],
                "correct": "A",
                "tip_rh": "A modularização centraliza as regras de negócio, facilitando correções e manutenções futuras sem retrabalho."
            },
            {
                "id": 33,
                "category": "Comportamental",
                "sub": "Ética no Código",
                "title": "Uso Ético de Códigos de Terceiros",
                "question": "Ao encontrar um trecho de código na internet ou usar uma ferramenta de IA para resolver um problema do projeto da empresa, qual a conduta adequada?",
                "options": [
                    "A) Copiar e colar sem entender nada do que o código faz e sem citar referências.",
                    "B) Compreender o funcionamento do código, testá-lo, adaptá-lo à realidade do projeto e respeitar licenças e políticas de segurança da empresa.",
                    "C) Dizer para a diretoria que você inventou aquela tecnologia do zero.",
                    "D) Enviar dados confidenciais de clientes para ferramentas públicas de IA."
                ],
                "correct": "B",
                "tip_rh": "Maturidade técnica: usar referências e IA com responsabilidade, segurança e entendimento do código."
            },
            {
                "id": 34,
                "category": "Técnica Básica",
                "sub": "Lógica & Boas Práticas",
                "title": "Nomes Claros de Variáveis e Funções",
                "question": "Por que nomes descritivos como `calcular_media()` e `lista_alunos` são muito melhores do que `func1()` e `x`?",
                "options": [
                    "A) Porque tornam o código legível, facilitando para que você e sua equipe entendam o programa no futuro.",
                    "B) Porque o Python só executa funções com nomes compridos.",
                    "C) Porque nomes curtos gastam mais energia do processador.",
                    "D) Não há diferença; qualquer nome serve igualmente."
                ],
                "correct": "A",
                "tip_rh": "Legibilidade e boas práticas: código limpo economiza tempo de toda a equipe de desenvolvimento."
            }
        ];

        let currentFilter = 'TODAS';
        let availablePool = [];
        let usedPool = [];
        let currentQuestion = null;
        let currentStep = 1;
        let candidateQuestionCount = 1;

        let timerSeconds = 180;
        let timerInterval = null;
        let isTimerRunning = false;

        window.addEventListener('DOMContentLoaded', () => {
            updateCounts();
            resetQuestionPool();
            drawNextQuestion(false);
        });

        function updateCounts() {
            document.getElementById('totalCount').innerText = QUESTIONS_DATA.length;
            document.getElementById('compCount').innerText = QUESTIONS_DATA.filter(q => q.category === 'Comportamental').length;
            document.getElementById('techCount').innerText = QUESTIONS_DATA.filter(q => q.category === 'Técnica Básica').length;
        }

        function resetQuestionPool() {
            const filtered = (currentFilter === 'TODAS') 
                ? QUESTIONS_DATA 
                : QUESTIONS_DATA.filter(q => q.category === currentFilter);
            
            availablePool = filtered.map(q => q.id);
            usedPool = [];
            updatePoolDisplay();
        }

        function updatePoolDisplay() {
            document.getElementById('availablePoolCount').innerText = availablePool.length;
        }

        function setCategoryFilter(category) {
            currentFilter = category;
            
            document.querySelectorAll('.tab-btn').forEach(btn => {
                if (btn.innerText.includes(category) || (category === 'TODAS' && btn.innerText.includes('Todas'))) {
                    btn.classList.add('active');
                } else {
                    btn.classList.remove('active');
                }
            });

            resetQuestionPool();
            drawNextQuestion(false);
        }

        function drawNextQuestion(incrementCount = true) {
            if (availablePool.length === 0) {
                alert('Todas as questões desta categoria já foram sorteadas! O banco será reiniciado automaticamente para novas rodadas.');
                resetQuestionPool();
            }

            const randomIndex = Math.floor(Math.random() * availablePool.length);
            const questionId = availablePool[randomIndex];

            availablePool.splice(randomIndex, 1);
            usedPool.push(questionId);
            updatePoolDisplay();

            currentQuestion = QUESTIONS_DATA.find(q => q.id === questionId);
            
            if (incrementCount) {
                candidateQuestionCount = (candidateQuestionCount % 3) + 1;
            }
            document.getElementById('candidateStat').innerText = `Q ${candidateQuestionCount} de 3`;

            setStep(1);
            renderCard();
        }

        function nextCandidate() {
            candidateQuestionCount = 1;
            document.getElementById('candidateStat').innerText = `Q 1 de 3`;
            resetTimer();
            drawNextQuestion(false);
        }

        function renderCard() {
            if (!currentQuestion) return;

            const badgeEl = document.getElementById('cardBadge');
            badgeEl.innerText = currentQuestion.category;
            if (currentQuestion.category === 'Técnica Básica') {
                badgeEl.classList.add('tech');
            } else {
                badgeEl.classList.remove('tech');
            }

            document.getElementById('cardSub').innerText = currentQuestion.sub;
            document.getElementById('cardIndexTracker').innerText = `ID #${currentQuestion.id}`;
            document.getElementById('cardTitle').innerText = currentQuestion.title;
            document.getElementById('cardQuestion').innerText = currentQuestion.question;

            const optionsContainer = document.getElementById('optionsContainer');
            optionsContainer.innerHTML = '';
            currentQuestion.options.forEach(opt => {
                const optLetter = opt.substring(0, 1);
                const optEl = document.createElement('div');
                optEl.className = 'option-card';
                optEl.id = `opt_${optLetter}`;
                optEl.innerHTML = `<strong>${optLetter})</strong> <span>${opt.substring(3)}</span>`;
                optionsContainer.appendChild(optEl);
            });

            const correctLetter = currentQuestion.correct;
            document.getElementById('correctOptionLetter').innerText = correctLetter;
            const fullCorrect = currentQuestion.options.find(o => o.startsWith(correctLetter));
            document.getElementById('correctOptionText').innerText = fullCorrect ? fullCorrect.substring(3) : '';
            document.getElementById('rhGuidanceText').innerText = currentQuestion.tip_rh;
        }

        function setStep(step) {
            currentStep = step;

            document.getElementById('stepIndicator1').className = (step === 1) ? 'step-item active' : (step > 1 ? 'step-item completed' : 'step-item');
            document.getElementById('stepIndicator2').className = (step === 2) ? 'step-item active' : (step > 2 ? 'step-item completed' : 'step-item');
            document.getElementById('stepIndicator3').className = (step === 3) ? 'step-item active' : 'step-item';

            const optionsContainer = document.getElementById('optionsContainer');
            const answerContainer = document.getElementById('answerContainer');
            const btnBack = document.getElementById('btnBackStep');
            const btnNext = document.getElementById('btnNextStep');
            const rhTipReader = document.getElementById('rhTipReader');

            if (step === 1) {
                optionsContainer.style.display = 'none';
                answerContainer.style.display = 'none';
                btnBack.style.display = 'none';
                btnNext.innerText = 'Ver Alternativas ➔';
                rhTipReader.style.display = 'flex';
                document.querySelectorAll('.option-card').forEach(el => el.classList.remove('correct-highlight'));
            } else if (step === 2) {
                optionsContainer.style.display = 'flex';
                answerContainer.style.display = 'none';
                btnBack.style.display = 'block';
                btnNext.innerText = 'Ver Gabarito & Guia RH ➔';
                rhTipReader.style.display = 'none';
                document.querySelectorAll('.option-card').forEach(el => el.classList.remove('correct-highlight'));
            } else if (step === 3) {
                optionsContainer.style.display = 'flex';
                answerContainer.style.display = 'flex';
                btnBack.style.display = 'block';
                btnNext.innerText = '🎲 Próxima Questão';
                rhTipReader.style.display = 'none';
                const correctEl = document.getElementById(`opt_${currentQuestion.correct}`);
                if (correctEl) correctEl.classList.add('correct-highlight');
            }
        }

        function nextStep() {
            if (currentStep === 1) {
                setStep(2);
            } else if (currentStep === 2) {
                setStep(3);
            } else if (currentStep === 3) {
                drawNextQuestion(true);
            }
        }

        function prevStep() {
            if (currentStep > 1) {
                setStep(currentStep - 1);
            }
        }

        function formatTime(seconds) {
            const m = Math.floor(seconds / 60);
            const s = seconds % 60;
            return `${m.toString().padStart(2, '0')}:${s.toString().padStart(2, '0')}`;
        }

        function updateTimerDisplay() {
            const display = document.getElementById('timerDisplay');
            display.innerText = formatTime(timerSeconds);
            if (timerSeconds <= 30 && timerSeconds > 0) {
                display.classList.add('warning');
            } else {
                display.classList.remove('warning');
            }
        }

        function toggleTimer() {
            const btn = document.getElementById('timerBtn');
            if (isTimerRunning) {
                clearInterval(timerInterval);
                isTimerRunning = false;
                btn.innerText = '▶ Continuar';
            } else {
                isTimerRunning = true;
                btn.innerText = '⏸ Pausar';
                timerInterval = setInterval(() => {
                    if (timerSeconds > 0) {
                        timerSeconds--;
                        updateTimerDisplay();
                    } else {
                        clearInterval(timerInterval);
                        isTimerRunning = false;
                        btn.innerText = '⏰ Tempo Esgotado';
                        alert('Tempo da entrevista (3 minutos) concluído! Hora do feedback rápido.');
                    }
                }, 1000);
            }
        }

        function resetTimer() {
            clearInterval(timerInterval);
            isTimerRunning = false;
            timerSeconds = 180;
            document.getElementById('timerBtn').innerText = '▶ Iniciar';
            updateTimerDisplay();
        }

        function openModal(id) {
            document.getElementById(id).classList.add('active');
        }

        function closeModal(id) {
            document.getElementById(id).classList.remove('active');
        }

        function rate(btn) {
            const parent = btn.parentElement;
            parent.querySelectorAll('.star-btn').forEach(b => b.classList.remove('selected'));
            btn.classList.add('selected');
        }
    </script>
</body>
</html>
