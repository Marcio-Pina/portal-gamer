
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal Gamer Interativo | Arena</title>

    <style>
        /* style.css - INÍCIO */

        /* Importa a fonte gamer */
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap');

        /* Estilos Gerais */
        body {
            font-family: 'Orbitron', sans-serif;
            background-color: #121212;
            color: #E0E0E0;
            margin: 0;
            padding: 0;
        }

        /* Navbar e Header */
        .navbar {
            background-color: #1A1A1A;
            padding: 15px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 3px solid #00FFFF;
        }

        .navbar h1 {
            color: #FF4500;
            text-shadow: 0 0 5px #FF4500;
            font-size: 1.8em;
        }

        .navbar nav a {
            color: #00FFFF;
            text-decoration: none;
            margin-left: 20px;
            padding: 8px 12px;
            transition: color 0.3s, text-shadow 0.3s;
            text-transform: uppercase;
        }

        .navbar nav a:hover {
            color: #FFFFFF;
            text-shadow: 0 0 10px #00FFFF;
        }

        /* Seções */
        main {
            padding: 20px 50px;
        }

        /* Seção de Destaque */
        .hero-section {
            text-align: center;
            padding: 100px 0;
            /* Placeholder para imagem de fundo */
            background: linear-gradient(rgba(18, 18, 18, 0.7), rgba(18, 18, 18, 0.7)), url('http://googleusercontent.com/image_collection/image_retrieval/some_id_string') center center/cover;
            border-radius: 10px;
            margin-bottom: 40px;
            box-shadow: inset 0 0 50px rgba(0, 255, 255, 0.2);
        }

        /* Botões e Links de Ação (Ajustado para aceitar <a> e <button>) */
        .action-button, .quiz-button, a.action-button { 
            padding: 12px 25px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            font-family: 'Orbitron', sans-serif;
            text-decoration: none; /* Para links que agem como botões */
            display: inline-block; /* Para links que agem como botões */
        }

        .button-glow {
            background-color: #4CAF50;
            box-shadow: 0 0 10px #4CAF50, 0 0 20px #4CAF50;
            color: white;
            border: 2px solid #388E3C;
        }

        .button-glow:hover {
            background-color: #66BB6A;
            box-shadow: 0 0 15px #00FFFF, 0 0 30px #00FFFF;
            transform: scale(1.05);
        }
        
        /* NOVO ESTILO: Botão Instagram */
        .button-instagram {
            background-color: #E1306C; /* Cor do Instagram (Rosa/Roxo) */
            box-shadow: 0 0 10px #E1306C, 0 0 20px rgba(225, 48, 108, 0.5);
            color: white;
            border: 2px solid #C13584;
        }

        .button-instagram:hover {
            background-color: #C13584;
            box-shadow: 0 0 15px #C13584, 0 0 30px #E1306C;
            transform: scale(1.05);
        }


        /* Estilos do Quiz */
        .quiz-section {
            background-color: #1A1A1A;
            padding: 30px;
            border-radius: 8px;
            border: 1px solid #FF4500;
            text-align: center;
            margin-bottom: 40px;
        }
        
        .quiz-section h3 {
            color: #FFD700;
            text-shadow: 0 0 5px #FFD700;
        }

        .quiz-button {
            background-color: #333;
            color: #FF4500;
            border: 2px solid #FF4500;
            box-shadow: 0 0 5px rgba(255, 69, 0, 0.5);
        }

        /* Estilos para Feedback do Quiz */
        .correct { background-color: #28a745 !important; box-shadow: 0 0 10px #28a745 !important; border-color: #28a745 !important; color: white; }
        .incorrect { background-color: #dc3545 !important; box-shadow: 0 0 10px #dc3545 !important; border-color: #dc3545 !important; color: white; }

        /* --- Seção de Cards de Jogos --- */
        #games {
            margin-top: 40px;
        }

        #games h2 {
            text-align: center;
            color: #00FFFF;
            text-shadow: 0 0 10px #00FFFF;
            margin-bottom: 30px;
        }

        .game-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        .game-card {
            background-color: #1A1A1A;
            border: 1px solid #333;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s, border-color 0.3s;
        }

        .game-card:hover {
            transform: translateY(-5px);
            border-color: #FF4500;
        }

        .game-card h4 {
            color: #FFD700;
            border-bottom: 2px solid #444;
            padding-bottom: 5px;
            margin-top: 0;
        }

        .game-card p {
            font-size: 0.9em;
            color: #CCCCCC;
            line-height: 1.4;
        }

        .game-card .genre {
            display: inline-block;
            background-color: #333;
            color: #00FFFF;
            padding: 5px 10px;
            border-radius: 4px;
            margin-bottom: 10px;
            font-size: 0.8em;
        }
        
        /* ESTILO PARA A SEÇÃO DE DICAS */
        .tip-box {
            margin-top: 10px;
            padding: 10px;
            background-color: #2a2a2a;
            border-left: 4px solid #FFD700;
            border-radius: 0 4px 4px 0;
            font-style: italic;
            font-size: 0.85em;
        }
        .tip-box strong {
            color: #FFD700;
            font-weight: 700;
        }


        /* ESTILOS DO LINK PARA PARECER UM BOTÃO */
        .game-card a.game-card-link {
            display: block; 
            width: 100%;
            margin-top: 15px;
            padding: 12px 25px;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            font-family: 'Orbitron', sans-serif;
            text-align: center;
            text-decoration: none; 
            
            background-color: #388E3C;
            color: white;
            border: 1px solid #388E3C;
        }

        .game-card a.game-card-link:hover {
            background-color: #4CAF50;
            transform: scale(1.03); 
        }
        
        /* Footer */
        footer {
             text-align: center; 
             padding: 10px; 
             background-color: #1A1A1A; 
             margin-top: 40px;
             border-top: 3px solid #FF4500;
        }

        /* Estilos para separar as perguntas e aumentar a legibilidade */
        .quiz-question-group {
            margin-bottom: 40px;
            padding-bottom: 20px;
            border-bottom: 1px dashed #333; 
        }

        .quiz-question-group:last-child {
            border-bottom: none;
        }

        /* style.css - FIM */
    </style>
</head>
<body>
    <header class="navbar">
        <h1>PORTAL **GAMER**</h1>
        <nav>
            <a href="#home">Início</a>
            <a href="#games">Arquivos</a>
            <a href="#quiz">Quiz Interativo</a>
            
            <a href="https://www.instagram.com/portal_gamer._?igsh=YTYwd2o2djFuaHhw&utm_source=qr" 
               target="_blank" 
               class="action-button button-instagram">Instagram</a>

            <a href="https://chat.whatsapp.com/B9srl3fqYhE21KbXJoSDOY" 
               target="_blank" 
               class="button-glow">Comunidade</a>
        </nav>
    </header>

    <main>
        <section id="home" class="hero-section">
            <h2>Bem-vindo à Arena!</h2>
            <p>Seu ponto de encontro diário para as últimas novidades do universo dos jogos.</p>
            <a href="https://chat.whatsapp.com/B9srl3fqYhE21KbXJoSDOY" target="_blank" class="action-button button-glow">Entrar na Comunidade</a>
        </section>

        <section id="games">
            <h2>🕹️ Arquivos da Arena: Dicas e Estratégias</h2>
            <div class="game-grid">
                
                <div class="game-card">
                    <h4>Free Fire</h4>
                    <span class="genre">Battle Royale / Mobile</span>
                    <div class="tip-box">
                        <strong>Dica Rápida:</strong> Priorize o uso do **Capa e Gelo** para defesa instantânea em combates de curta distância. Mantenha-se nas bordas da zona segura para evitar confrontos triplos.
                    </div>
                    <a href="https://intl.garena.com/" target="_blank" class="game-card-link">Ver Guia Avançado</a>
                </div>

                <div class="game-card">
                    <h4>Valorant</h4>
                    <span class="genre">Tiro Tático / PC</span>
                    <div class="tip-box">
                        <strong>Dica Rápida:</strong> A comunicação é chave! Use suas habilidades (ultimates) sempre em coordenação com o time. Em rodadas econômicas, prefira armas baratas como a **Spectre** ou a **Sheriff**.
                    </div>
                    <a href="https://store.epicgames.com/pt-BR/p/valorant" target="_blank" class="game-card-link">Site Oficial</a>
                </div>

                <div class="game-card">
                    <h4>Call of Duty (CoD)</h4>
                    <span class="genre">FPS / Múltiplas Plataformas</span>
                    <div class="tip-box">
                        <strong>Dica Rápida:</strong> Em **Warzone**, sempre use o **Contrato de Procurado** no início da partida para obter dinheiro rápido e localizar inimigos próximos. Mude sua rotação antes do fechamento do gás.
                    </div>
                    <a href="https://callofdutyleague.com/fr-fr/" target="_blank" class="game-card-link">Ver Novidades da Temporada</a>
                </div>

                <div class="game-card">
                    <h4>Clash Royale</h4>
                    <span class="genre">Estratégia / Mobile</span>
                    <div class="tip-box">
                        <strong>Dica Rápida:</strong> Nunca gaste todo o seu Elixir de uma vez. Mantenha pelo menos 3 ou 4 de Elixir na reserva para defender um contra-ataque rápido do oponente, especialmente se ele tiver o **Corredor**.
                    </div>
                    <a href="https://store.supercell.com/pt/clashroyale" target="_blank" class="game-card-link">Ver Decks Meta</a>
                </div>

                <div class="game-card">
                    <h4>Brawl Stars</h4>
                    <span class="genre">Ação Arcade / Mobile</span>
                    <div class="tip-box">
                        <strong>Dica Rápida:</strong> Evite jogar de forma muito agressiva no início. Use os arbustos para recarregar sua vida e suas habilidades. Em Fute-Brawl, o controle do meio é mais importante que o gol.
                    </div>
                    <a href="https://supercell.com/en/games/brawlstars/" target="_blank" class="game-card-link">Ver Melhores Brawlers</a>
                </div>

                <div class="game-card">
                    <h4>eFootball</h4>
                    <span class="genre">Futebol / Simulação</span>
                    <div class="tip-box">
                        <strong>Dica Rápida:</strong> Não confie apenas no botão de Pique. Use o **toque de bola rápido** e passes curtos para abrir espaços e utilize o **drible manual** para tirar a marcação na área.
                    </div>
                    <a href="https://www.konami.com/efootball/pt/" target="_blank" class="game-card-link">Site Oficial</a>
                </div>

                <div class="game-card">
                    <h4>FC Mobile / EA Sports FC</h4>
                    <span class="genre">Futebol / Ultimate Team</span>
                    <div class="tip-box">
                        <strong>Dica Rápida:</strong> Domine a finalização de trivela (Power Shot)! Ela é extremamente forte fora da área e pega o goleiro de surpresa. Use L1 + R1 (ou similar) + Chute.
                    </div>
                    <a href="https://www.ea.com/pt-br/games/ea-sports-fc/fc-mobile" target="_blank" class="game-card-link">Ver Cartas em Destaque</a>
                </div>
            </div>
        </section>


        <section id="quiz" class="quiz-section">
            <h3>🔥 Quiz: Teste seu Conhecimento na Arena! 🔥</h3>
            <div id="quiz-container">
                
                <div class="quiz-question-group" data-question-id="1">
                    <p>Em **Valorant**, qual é o nome dado aos personagens jogáveis com habilidades únicas?</p>
                    <div class="options">
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Brawlers</button>
                        <button class="quiz-button" data-correct="true" onclick="checkAnswer(this)">Agentes</button>
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Lendas</button>
                    </div>
                </div>
                
                <div class="quiz-question-group" data-question-id="2">
                    <p>No **Free Fire**, qual é o grito de vitória que simboliza o último sobrevivente?</p>
                    <div class="options">
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Vitória Royale</button>
                        <button class="quiz-button" data-correct="true" onclick="checkAnswer(this)">BOOYAH!</button>
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Chiken Dinner</button>
                    </div>
                </div>
                
                <div class="quiz-question-group" data-question-id="3">
                    <p>Em **Clash Royale**, qual é a estrutura principal que você deve destruir para garantir a vitória?</p>
                    <div class="options">
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Torre de Defesa</button>
                        <button class="quiz-button" data-correct="true" onclick="checkAnswer(this)">Torre do Rei</button>
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Barril de Elixir</button>
                    </div>
                </div>

                <div class="quiz-question-group" data-question-id="4">
                    <p>Qual empresa de jogos é a desenvolvedora de **Brawl Stars** (e também de Clash Royale)?</p>
                    <div class="options">
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Riot Games</button>
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Garena</button>
                        <button class="quiz-button" data-correct="true" onclick="checkAnswer(this)">Supercell</button>
                    </div>
                </div>

                <div class="quiz-question-group" data-question-id="5">
                    <p>O jogo **eFootball** era anteriormente conhecido por qual nome?</p>
                    <div class="options">
                        <button class="quiz-button" data-correct="true" onclick="checkAnswer(this)">Pro Evolution Soccer (PES)</button>
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">FIFA</button>
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Football Manager</button>
                    </div>
                </div>

                <div class="quiz-question-group" data-question-id="6">
                    <p>O modo de jogo **Warzone** de **Call of Duty** pertence a qual gênero principal?</p>
                    <div class="options">
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">Estratégia em Tempo Real</button>
                        <button class="quiz-button" data-correct="true" onclick="checkAnswer(this)">Battle Royale</button>
                        <button class="quiz-button" data-correct="false" onclick="checkAnswer(this)">MMORPG</button>
                    </div>
                </div>
                
                <p id="quiz-feedback" style="margin-top: 30px; font-weight: bold; min-height: 20px; font-size: 1.2em;"></p>
                <button class="action-button button-glow" onclick="resetQuiz()">Tentar Novamente</button>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Portal Gamer. Todos os direitos reservados.</p>
    </footer>

    <script>
        // script.js - Lógica do Quiz

        // Variáveis globais para rastrear o estado do quiz
        let totalScore = 0;
        let answeredQuestions = 0;
        const totalQuestions = 6; 

        function checkAnswer(buttonElement) {
            const isCorrect = buttonElement.getAttribute('data-correct') === 'true';
            const optionsDiv = buttonElement.parentNode;
            const questionGroup = optionsDiv.closest('.quiz-question-group');
            
            // Verifica se esta pergunta já foi respondida (usando um atributo de dados)
            if (questionGroup.getAttribute('data-answered') === 'true') {
                return; 
            }
            questionGroup.setAttribute('data-answered', 'true'); // Marca a pergunta como respondida

            const buttons = optionsDiv.querySelectorAll('.quiz-button');
            const feedbackText = document.getElementById('quiz-feedback');

            // 1. Desabilita todos os botões daquela pergunta
            buttons.forEach(btn => btn.disabled = true);
            
            // 2. Atualiza a pontuação
            answeredQuestions++;
            if (isCorrect) {
                buttonElement.classList.add('correct');
                totalScore++;
            } else {
                buttonElement.classList.add('incorrect');
                // Destaca a resposta correta para aprendizado
                buttons.forEach(btn => {
                    if (btn.getAttribute('data-correct') === 'true') {
                        btn.classList.add('correct');
                    }
                });
            }

            // 3. Atualiza o feedback final se todas as perguntas forem respondidas
            if (answeredQuestions === totalQuestions) {
                feedbackText.textContent = `🎉 Fim do Quiz! Sua pontuação é: ${totalScore} de ${totalQuestions} acertos.`;
                feedbackText.style.color = totalScore === totalQuestions ? '#00FFFF' : '#FF4500';
            }
        }

        function resetQuiz() {
            // Reinicia as variáveis
            totalScore = 0;
            answeredQuestions = 0;
            document.getElementById('quiz-feedback').textContent = '';

            const allQuestionGroups = document.querySelectorAll('.quiz-question-group');
            allQuestionGroups.forEach(questionGroup => {
                questionGroup.removeAttribute('data-answered'); // Remove a marca de respondido

                const buttons = questionGroup.querySelectorAll('.quiz-button');
                buttons.forEach(btn => {
                    btn.disabled = false;
                    btn.classList.remove('correct', 'incorrect');
                });
            });
        }
    </script>
</body>
</html>
