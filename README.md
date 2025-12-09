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
        
        /* Estilo específico para o link do Instagram na Navbar */
        .navbar nav a.instagram-link {
            color: #FF4500; /* Laranja para destaque */
        }
        .navbar nav a.instagram-link:hover {
             text-shadow: 0 0 10px #FF4500;
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

        /* Botões e Links de Ação */
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
            text-decoration: none; 
            display: inline-block; 
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
            min-height: 40px; 
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

        /* Botão Secundário para Dicas (Laranja) */
        .tip-button {
            display: block; 
            width: 100%;
            margin-top: 10px;
            padding: 10px 20px;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            font-family: 'Orbitron', sans-serif;
            text-align: center;
            text-decoration: none; 
            background-color: #FF4500; /* Laranja Vívido */
            color: white;
            border: 1px solid #FF4500;
        }

        .tip-button:hover {
            background-color: #FF6347;
            transform: scale(1.03); 
        }

        /* ESTILOS DO LINK PADRÃO (Botão Verde) */
        .game-card-link {
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

        .game-card-link:hover {
            background-color: #4CAF50;
            transform: scale(1.03); 
        }

        /* --- Estilos do Modal (Pop-up de Dicas) --- */
        .modal {
            display: none; 
            position: fixed; 
            z-index: 100; 
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto; 
            background-color: rgba(0,0,0,0.8); 
        }

        .modal-content {
            background-color: #1A1A1A;
            margin: 5% auto; 
            padding: 30px;
            border: 3px solid #00FFFF;
            width: 80%;
            max-width: 800px; 
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
            position: relative;
        }

        .close {
            color: #FF4500;
            float: right;
            font-size: 36px;
            font-weight: bold;
            line-height: 1;
        }

        .close:hover,
        .close:focus {
            color: #fff;
            text-decoration: none;
            cursor: pointer;
        }
        
        .modal-content h3 {
            color: #FFD700;
            margin-top: 0;
            border-bottom: 1px solid #333;
            padding-bottom: 10px;
        }

        .modal-content ul {
            list-style-type: none;
            padding: 0;
        }

        .modal-content ul li {
            background: #222;
            margin-bottom: 10px;
            padding: 10px;
            border-left: 5px solid #FF4500;
            border-radius: 4px;
        }

        /* Estilos do Footer */
        footer {
             text-align: center; 
             padding: 20px; /* Aumentado para melhor visualização dos links */
             background-color: #1A1A1A; 
             margin-top: 40px;
             border-top: 3px solid #FF4500;
        }

        footer a {
            color: #00FFFF;
            text-decoration: none;
            margin: 0 10px;
            transition: color 0.3s;
        }
        footer a:hover {
            color: #FFD700;
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
            <a href="https://www.instagram.com/portal_gamer._?igsh=YTYwd2o2djFuaHhw&utm_source=qr" target="_blank" class="instagram-link">Instagram</a>
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
                    <p>Famoso jogo de Battle Royale para celular. O objetivo é ser o último a permanecer vivo (BOOYAH!).</p>
                    <button class="tip-button" onclick="openModal('Free Fire')">Ver Estratégias</button>
                    <a href="https://intl.garena.com/" target="_blank" class="game-card-link">Site Oficial Garena</a>
                </div>

                <div class="game-card">
                    <h4>Valorant</h4>
                    <span class="genre">Tiro Tático / PC</span>
                    <p>Shooter tático 5v5 da Riot Games que combina tiro preciso com habilidades únicas dos "Agentes".</p>
                    <button class="tip-button" onclick="openModal('Valorant')">Ver Estratégias</button>
                    <a href="https://store.epicgames.com/pt-BR/p/valorant" target="_blank" class="game-card-link">Site Oficial</a>
                </div>

                <div class="game-card">
                    <h4>Call of Duty (CoD)</h4>
                    <span class="genre">FPS / Múltiplas Plataformas</span>
                    <p>Franquia lendária de tiro em primeira pessoa, incluindo o modo Battle Royale (Warzone).</p>
                    <button class="tip-button" onclick="openModal('Call of Duty')">Ver Estratégias</button>
                    <a href="https://callofdutyleague.com/fr-fr/" target="_blank" class="game-card-link">Ver Novidades da Temporada</a>
                </div>

                <div class="game-card">
                    <h4>Clash Royale</h4>
                    <span class="genre">Estratégia / Mobile</span>
                    <p>Jogo de cartas colecionáveis e estratégia em tempo real. O objetivo é destruir a Torre do Rei.</p>
                    <button class="tip-button" onclick="openModal('Clash Royale')">Ver Estratégias</button>
                    <a href="https://store.supercell.com/pt/clashroyale" target="_blank" class="game-card-link">Ver Decks Meta</a>
                </div>

                <div class="game-card">
                    <h4>Brawl Stars</h4>
                    <span class="genre">Ação Arcade / Mobile</span>
                    <p>Jogo de arena multiplayer com vários modos de jogo. Escolha seu "Brawler" e lute em 3v3 ou solo.</p>
                    <button class="tip-button" onclick="openModal('Brawl Stars')">Ver Estratégias</button>
                    <a href="https://supercell.com/en/games/brawlstars/" target="_blank" class="game-card-link">Ver Melhores Brawlers</a>
                </div>

                <div class="game-card">
                    <h4>eFootball</h4>
                    <span class="genre">Futebol / Simulação</span>
                    <p>O simulador de futebol da Konami (antigo Pro Evolution Soccer). Gratuito para jogar e focado em realismo.</p>
                    <button class="tip-button" onclick="openModal('eFootball')">Ver Estratégias</button>
                    <a href="https://www.konami.com/efootball/pt/" target="_blank" class="game-card-link">Site Oficial</a>
                </div>

                <div class="game-card">
                    <h4>FC Mobile / EA Sports FC</h4>
                    <span class="genre">Futebol / Ultimate Team</span>
                    <p>Sucessor do FIFA, focado no modo Ultimate Team. Colecione cartas e monte seu time dos sonhos.</p>
                    <button class="tip-button" onclick="openModal('FC Mobile')">Ver Estratégias</button>
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
        <p>
            <a href="https://www.instagram.com/portal_gamer._?igsh=YTYwd2o2djFuaHhw&utm_source=qr" target="_blank">Instagram</a> | 
            <a href="https://chat.whatsapp.com/B9srl3fqYhE21KbXJoSDOY" target="_blank">Comunidade WhatsApp</a>
        </p>
    </footer>

    <div id="tipsModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal()">&times;</span>
            <h3 id="modalTitle"></h3>
            <div id="modalContent">
                </div>
        </div>
    </div>

    <script>
        // script.js - Lógica do Quiz e do Modal

        // --- Lógica do Quiz (Mantida) ---
        let totalScore = 0;
        let answeredQuestions = 0;
        const totalQuestions = 6; 

        function checkAnswer(buttonElement) {
            const isCorrect = buttonElement.getAttribute('data-correct') === 'true';
            const optionsDiv = buttonElement.parentNode;
            const questionGroup = optionsDiv.closest('.quiz-question-group');
            
            if (questionGroup.getAttribute('data-answered') === 'true') return; 
            questionGroup.setAttribute('data-answered', 'true'); 

            const buttons = optionsDiv.querySelectorAll('.quiz-button');
            const feedbackText = document.getElementById('quiz-feedback');

            buttons.forEach(btn => btn.disabled = true);
            
            answeredQuestions++;
            if (isCorrect) {
                buttonElement.classList.add('correct');
                totalScore++;
            } else {
                buttonElement.classList.add('incorrect');
                buttons.forEach(btn => {
                    if (btn.getAttribute('data-correct') === 'true') {
                        btn.classList.add('correct');
                    }
                });
            }

            if (answeredQuestions === totalQuestions) {
                feedbackText.textContent = `🎉 Fim do Quiz! Sua pontuação é: ${totalScore} de ${totalQuestions} acertos.`;
                feedbackText.style.color = totalScore === totalQuestions ? '#00FFFF' : '#FF4500';
            }
        }

        function resetQuiz() {
            totalScore = 0;
            answeredQuestions = 0;
            document.getElementById('quiz-feedback').textContent = '';

            const allQuestionGroups = document.querySelectorAll('.quiz-question-group');
            allQuestionGroups.forEach(questionGroup => {
                questionGroup.removeAttribute('data-answered'); 

                const buttons = questionGroup.querySelectorAll('.quiz-button');
                buttons.forEach(btn => {
                    btn.disabled = false;
                    btn.classList.remove('correct', 'incorrect');
                });
            });
        }
        
        // --- Lógica do Modal de Dicas (Nova) ---

        // Dicionário com as dicas detalhadas pesquisadas
        const detailedTips = {
            'Free Fire': {
                title: '🔫 Dicas Avançadas para o BOOYAH!',
                content: `
                    <ul>
                        <li>**Posicionamento no Gás:** No final do jogo, jogue próximo ao gás para evitar que inimigos venham por trás.</li>
                        <li>**Técnica do Capa:** Mire um pouco abaixo do pescoço do adversário e arraste o dedo para cima rapidamente ao disparar para maximizar o dano (tiro na cabeça).</li>
                        <li>**Uso Estratégico do Gelo:** Não use a *Gloo Wall* apenas para defesa. Use-a para bloquear rotas inimigas ou ganhar tempo para se curar/recarregar em campo aberto.</li>
                        <li>**Rotação Segura:** Evite correr pelo meio do mapa. Priorize as bordas da zona segura e use o minimapa para prever movimentos inimigos.</li>
                    </ul>
                `
            },
            'Valorant': {
                title: '🎯 Dicas Táticas para Dominar a Spike',
                content: `
                    <ul>
                        <li>**Treino de Recuo (Recoil):** Conheça o padrão de recuo da Vandal e Phantom (que geralmente formam um 'T'). Treinar esse controle é vital para subir de elo.</li>
                        <li>**Posicionamento de Retícula:** Mantenha a mira sempre na altura da cabeça do inimigo (Headshot Level) antes mesmo de ver o adversário.</li>
                        <li>**Comunicação Limpa:** Seja preciso no *Callout*. Diga onde está, o que ouviu e o que vai fazer. Evite poluir a comunicação durante o *clutch* (situações 1vX).</li>
                        <li>**Uso Criativo de Habilidades:** Aprenda *pixel spots* com Agentes como Sova (flechas) ou Omen (smokes 'one-way') para obter vantagem inesperada.</li>
                    </ul>
                `
            },
            'Call of Duty': {
                title: '💥 Estratégias Vencedoras no Warzone',
                content: `
                    <ul>
                        <li>**Pouso Estratégico:** Evite as áreas centrais no início. Pouse em locais menos agitados para lootear com calma e garantir um *Loadout Drop*.</li>
                        <li>**Posicionamento Elevado:** Controle os pontos altos do terreno (*High Ground*). Isso garante visão privilegiada e facilita a rotação da equipe.</li>
                        <li>**Rotação Antecipada:** Não espere o gás começar a empurrar. Rotacione para a próxima zona segura mais cedo para controlar o posicionamento.</li>
                        <li>**Gerenciamento de Vantagens (Perks):** Priorize Vantagens como *Tracker* (rastreia pegadas) ou *Spotter* (detecta armadilhas) nas fases avançadas.</li>
                    </ul>
                `
            },
            'Clash Royale': {
                title: '♟️ Dicas de Mestre para a Batalha de Cartas',
                content: `
                    <ul>
                        <li>**Contagem de Elixir e Rotação:** Acompanhe quantas cartas o adversário já usou (rotação) e tente contar o Elixir dele. Isso permite prever a próxima jogada.</li>
                        <li>**Defesa Eficiente:** Use a Defesa como arma. Defenda com unidades baratas e use as tropas sobreviventes (que viram Contra-Ataque) para forçar o inimigo a gastar Elixir.</li>
                        <li>**Posicionamento:** Não comprometa todo o seu Elixir na ponte. Esconda suas intenções e force o oponente a mostrar o jogo dele primeiro.</li>
                        <li>**Assista Replays:** Não tenha medo de ver os replays das derrotas. Identificar o ponto exato onde você errou é a forma mais rápida de melhorar.</li>
                    </ul>
                `
            },
            'Brawl Stars': {
                title: '⭐ Guia Rápido de Brawlers e Táticas',
                content: `
                    <ul>
                        <li>**Gerenciamento de Munição:** Não dispare todos os tiros à distância. Aprenda o tempo de recarga e o alcance do seu Brawler para não ficar vulnerável.</li>
                        <li>**Bush Checking:** Sempre atire nos arbustos (*Bush*) antes de entrar para evitar ser emboscado. Brawlers de ataque em área são ótimos para limpar mato.</li>
                        <li>**Domínio de Brawler:** Priorize subir o nível de domínio do seu Brawler principal. Os primeiros níveis de domínio rendem ótimas moedas e recursos.</li>
                        <li>**Aprenda com Stu:** O Brawler Stu é ótimo para iniciantes aprenderem a mecânica de esquiva, alcance e movimento rápido.</li>
                    </ul>
                `
            },
            'eFootball': {
                title: '⚽ Estratégias do Campo (Simulação)',
                content: `
                    <ul>
                        <li>**O Super Cancel:** Domine o comando 'Super Cancel' (R1/RB + R2/RT) para cancelar instantaneamente uma ação, essencial para controle e defesa.</li>
                        <li>**Posicionamento Defensivo:** Evite dar *tackles* desesperados. Priorize o bom posicionamento da zaga para bloquear chutes e passes (Defesa com paciência).</li>
                        <li>**Toque Incisivo:** Use o comando de 'Toque Incisivo' para dar um pique rápido e passar pelo primeiro marcador na lateral do campo.</li>
                        <li>**Instruções Avançadas:** Utilize as instruções avançadas (como 'Defesa Profunda') para adaptar a tática do time durante a partida.</li>
                    </ul>
                `
            },
            'FC Mobile': {
                title: '📱 Dicas para o Ultimate Team Móvel',
                content: `
                    <ul>
                        <li>**Priorize o OVR:** Aumente a Classificação Geral (OVR) do seu time para melhorar as estatísticas dos jogadores. Troque jogadores de OVR baixo.</li>
                        <li>**Defesa na Linha de Passe:** Em vez de correr atrás do portador da bola, posicione seus defensores para bloquear as linhas de passe, limitando as opções do adversário.</li>
                        <li>**Timing Ofensivo:** O 'timing' é tudo. Defenda com calma, mas ataque rapidamente quando estiver em posição de chute perto do gol.</li>
                        <li>**Formação Defensiva:** Formações como 4-4-2 plana, 4-3-2-1 estreita ou 4-1-4-1 são ótimas para conter o ataque adversário.</li>
                    </ul>
                `
            }
        };

        function openModal(gameName) {
            const modal = document.getElementById('tipsModal');
            const titleElement = document.getElementById('modalTitle');
            const contentElement = document.getElementById('modalContent');
            
            const tips = detailedTips[gameName];

            if (tips) {
                titleElement.textContent = tips.title;
                contentElement.innerHTML = tips.content;
                modal.style.display = 'block';
            } else {
                alert('Dicas não encontradas para este jogo.');
            }
        }

        function closeModal() {
            document.getElementById('tipsModal').style.display = 'none';
        }

        // Fechar o modal clicando fora dele
        window.onclick = function(event) {
            const modal = document.getElementById('tipsModal');
            if (event.target == modal) {
                modal.style.display = 'none';
            }
        }
    </script>
</body>
</html>

