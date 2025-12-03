<!DOCTYPE html>
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
            <a href="https://chat.whatsapp.com/B9srl3fqYhE21KbXJoSDOY" target="_blank" class="button-glow">Comunidade</a>
        </nav>
    </header>

    <main>
        <section id="home" class="hero-section">
            <h2>Bem-vindo à Arena!</h2>
            <p>Seu ponto de encontro diário para as últimas novidades do universo dos jogos.</p>
            <a href="https://chat.whatsapp.com/B9srl3fqYhE21KbXJoSDOY" target="_blank" class="action-button button-glow">Entrar na Comunidade</a>
        </section>

        <section id="games">
            <h2>🕹️ Arquivos da Arena: Jogos Populares</h2>
            <div class="game-grid">
                
                <div class="game-card">
                    <h4>Free Fire</h4>
                    <span class="genre">Battle Royale / Mobile</span>
                    <p>Famoso jogo de Battle Royale para celular, onde 50 jogadores caem em uma ilha e lutam pela sobrevivência. O objetivo é ser o último a permanecer vivo (BOOYAH!). Conhecido por partidas rápidas e requisitos leves.</p>
                    <a href="https://intl.garena.com/" target="_blank" class="game-card-link">Ver Guia Avançado</a>
                </div>

                <div class="game-card">
                    <h4>Valorant</h4>
                    <span class="genre">Tiro Tático / PC</span>
                    <p>Um shooter tático 5v5 da Riot Games que combina mecânicas de tiro precisas (como CS:GO) com habilidades únicas de personagens ("Agentes"). O jogo exige comunicação e estratégia de equipe para plantar ou desarmar a Spike.</p>
                    <a href="https://store.epicgames.com/pt-BR/p/valorant" target="_blank" class="game-card-link">Site Oficial</a>
                </div>

                <div class="game-card">
                    <h4>Call of Duty (CoD)</h4>
                    <span class="genre">FPS / Múltiplas Plataformas</span>
                    <p>Uma franquia lendária de tiro em primeira pessoa. O CoD atualiza seu Battle Royale (Warzone) e oferece modos clássicos de tiro frenético (Multiplayer) e campanhas cinematográficas. Popular tanto no PC/Console quanto no Mobile.</p>
                    <a href="https://callofdutyleague.com/fr-fr/" target="_blank" class="game-card-link">Ver Novidades da Temporada</a>
                </div>

                <div class="game-card">
                    <h4>Clash Royale</h4>
                    <span class="genre">Estratégia / Mobile</span>
                    <p>Um jogo de cartas colecionáveis e estratégia em tempo real da Supercell. O objetivo é destruir a Torre do Rei e as Torres da Princesa do oponente usando um deck de unidades, feitiços e defesas. Rápido e competitivo.</p>
                    <a href="https://store.supercell.com/pt/clashroyale" target="_blank" class="game-card-link">Ver Decks Meta</a>
                </div>

                <div class="game-card">
                    <h4>Brawl Stars</h4>
                    <span class="genre">Ação Arcade / Mobile</span>
                    <p>Também da Supercell, é um jogo de arena multiplayer com vários modos de jogo (Gemas, Fute-Brawl, Combate, etc.). Escolha seu "Brawler" com habilidades únicas e lute em partidas rápidas de 3v3 ou solo.</p>
                    <a href="https://supercell.com/en/games/brawlstars/" target="_blank" class="game-card-link">Ver Melhores Brawlers</a>
                </div>

                <div class="game-card">
                    <h4>eFootball</h4>
                    <span class="genre">Futebol / Simulação</span>
                    <p>O simulador de futebol da Konami (antigo Pro Evolution Soccer). Focado em jogabilidade realista e licenças de times e ligas importantes. É gratuito para jogar e muito popular no cenário competitivo de eSports.</p>
                    <a href="https://www.konami.com/efootball/pt/" target="_blank" class="game-card-link">Site Oficial</a>
                </div>

                <div class="game-card">
                    <h4>FC Mobile / EA Sports FC</h4>
                    <span class="genre">Futebol / Ultimate Team</span>
                    <p>Sucessor do FIFA, o EA Sports FC e o FC Mobile oferecem a experiência do futebol com foco no modo Ultimate Team. Colecione cartas de jogadores, monte seu time dos sonhos e compita em partidas online ou carreira.</p>
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
