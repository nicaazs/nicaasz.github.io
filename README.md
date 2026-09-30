<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfólio — Nicoly Ferreira</title>
    <!-- Fonte do Google Fonts para dar um visual mais moderno e tech -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            /* Paleta de Cores Tech / Dark Mode */
            --bg-color: #0b0f19;
            --card-bg: #151b2b;
            --text-main: #e2e8f0;
            --text-muted: #94a3b8;
            --accent-cyan: #00e5ff;
            --accent-purple: #b300ff;
            --border-color: #2a3441;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            -webkit-font-smoothing: antialiased;
        }

        /* Fontes Mono para elementos de código e tags */
        h1, h2, h3, .tag, .code-font {
            font-family: 'Fira Code', monospace;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            text-align: center;
            padding: 100px 20px 60px;
            border-bottom: 1px solid var(--border-color);
            background: radial-gradient(circle at 50% -20%, rgba(0, 229, 255, 0.1), transparent 50%);
        }

        header h1 {
            font-size: 2.8rem;
            margin-bottom: 15px;
            color: var(--text-main);
            text-shadow: 0 0 10px rgba(0, 229, 255, 0.3);
        }

        header h2 {
            font-size: 1.1rem;
            font-weight: 400;
            color: var(--text-muted);
            margin-bottom: 25px;
            font-family: 'Inter', sans-serif;
        }

        .quote {
            font-style: italic;
            font-size: 1.1rem;
            margin-bottom: 40px;
            color: var(--accent-cyan);
        }

        /* Botões */
        .btn {
            display: inline-block;
            padding: 10px 24px;
            margin: 5px;
            background-color: transparent;
            color: var(--text-main);
            text-decoration: none;
            border-radius: 5px;
            font-family: 'Fira Code', monospace;
            font-size: 0.9rem;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .btn-cyan {
            border-color: var(--accent-cyan);
            color: var(--accent-cyan);
            box-shadow: 0 0 10px rgba(0, 229, 255, 0.1);
        }

        .btn-cyan:hover {
            background-color: var(--accent-cyan);
            color: var(--bg-color);
            box-shadow: 0 0 20px rgba(0, 229, 255, 0.4);
        }

        .btn:hover:not(.btn-cyan) {
            border-color: var(--text-main);
            background-color: rgba(255, 255, 255, 0.05);
        }

        /* Seções */
        section {
            padding: 80px 0;
            border-bottom: 1px dashed var(--border-color);
        }

        section:last-of-type {
            border-bottom: none;
        }

        section h2 {
            font-size: 1.8rem;
            margin-bottom: 40px;
            color: var(--accent-purple);
            display: inline-block;
            border-bottom: 2px solid var(--accent-purple);
            padding-bottom: 5px;
        }

        /* Cartões */
        .card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            margin-bottom: 20px;
            transition: all 0.3s ease;
        }

        /* Efeito Neon nos cartões ao passar o mouse */
        .card:hover {
            border-color: var(--accent-cyan);
            box-shadow: 0 0 20px rgba(0, 229, 255, 0.15);
            transform: translateY(-3px);
        }

        .card.purple-hover:hover {
            border-color: var(--accent-purple);
            box-shadow: 0 0 20px rgba(179, 0, 255, 0.15);
        }

        .card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: var(--text-main);
        }

        /* Tags */
        .tags {
            margin-top: 20px;
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tag {
            background: rgba(0, 229, 255, 0.1);
            color: var(--accent-cyan);
            padding: 5px 12px;
            border-radius: 4px;
            font-size: 0.8rem;
            border: 1px solid rgba(0, 229, 255, 0.2);
        }

        /* Grid Layouts */
        .grid-2 {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
        }

        .grid-3 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        /* Listas */
        ul {
            list-style-type: none;
            margin-top: 15px;
        }

        ul li {
            margin-bottom: 10px;
            padding-left: 20px;
            position: relative;
            color: var(--text-muted);
        }

        ul li::before {
            content: "▹";
            position: absolute;
            left: 0;
            color: var(--accent-purple);
            font-family: monospace;
        }

        /* Links */
        .project-link {
            display: inline-flex;
            align-items: center;
            margin-top: 20px;
            color: var(--accent-cyan);
            text-decoration: none;
            font-weight: 600;
            font-size: 0.9rem;
            transition: 0.3s;
        }

        .project-link:hover {
            color: #fff;
            text-shadow: 0 0 8px var(--accent-cyan);
        }

        .project-link::after {
            content: " →";
            margin-left: 5px;
            transition: transform 0.3s;
        }

        .project-link:hover::after {
            transform: translateX(5px);
        }

        /* Footer */
        footer {
            background: #070a12;
            padding: 60px 20px;
            text-align: center;
            border-top: 1px solid var(--border-color);
        }

        .contact-links {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .contact-links a {
            color: var(--text-muted);
            text-decoration: none;
            font-size: 1rem;
            font-family: 'Fira Code', monospace;
            transition: color 0.3s;
            border: 1px solid var(--border-color);
            padding: 8px 16px;
            border-radius: 5px;
            background: var(--card-bg);
        }

        .contact-links a:hover {
            color: var(--accent-cyan);
            border-color: var(--accent-cyan);
        }

        .status-badge {
            display: inline-block;
            background: rgba(179, 0, 255, 0.1);
            color: var(--accent-purple);
            font-size: 0.75rem;
            padding: 3px 8px;
            border-radius: 12px;
            margin-bottom: 10px;
            border: 1px solid rgba(179, 0, 255, 0.3);
        }

        @media (max-width: 768px) {
            .grid-2 {
                grid-template-columns: 1fr;
            }
            header h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>

    <!-- Header / Início -->
    <header id="inicio">
        <h1>&lt;Nicoly Ferreira /&gt;</h1>
        <h2>Estudante de Análise e Desenvolvimento de Sistemas<br><span style="color: var(--text-muted);">Desenvolvimento • Dados • Banco de Dados • Tecnologia</span></h2>
        <p class="quote">"Transformando conhecimento em projetos e experiências reais."</p>
        <div>
            <a href="#projetos" class="btn btn-cyan">Ver projetos</a>
            <a href="#sobre" class="btn">Sobre mim</a>
            <a href="#contato" class="btn">Contato</a>
        </div>
    </header>

    <div class="container">
        <!-- Sobre mim -->
        <section id="sobre">
            <h2>01. Sobre mim</h2>
            <div class="card purple-hover">
                <p style="color: var(--text-muted);">Sou estudante de Análise e Desenvolvimento de Sistemas na PUCPR e estou construindo minha carreira na área de tecnologia. Tenho interesse em desenvolvimento, análise de sistemas, dados e banco de dados. Gosto de aprender colocando a mão na massa e transformar o que estudo em projetos práticos.</p>
                <div style="margin-top: 25px;">
                    <p class="code-font" style="margin-bottom: 10px; color: var(--text-main);">// Tecnologias que estou estudando:</p>
                    <div class="tags">
                        <span class="tag">Python</span>
                        <span class="tag">SQL</span>
                        <span class="tag">MySQL</span>
                        <span class="tag">HTML/CSS</span>
                        <span class="tag">Git/GitHub</span>
                        <span class="tag">UI/UX Design</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projetos -->
        <section id="projetos">
            <h2>02. Projetos</h2>
            <div class="grid-2">
                <div class="card">
                    <span class="status-badge">Em desenvolvimento</span>
                    <h3>📊 Dashboard de Vendas</h3>
                    <p style="color: var(--text-muted);">Projeto de análise de dados para visualizar faturamento, vendas, produtos e desempenho por período.</p>
                    <div class="tags">
                        <span class="tag">Power BI</span>
                        <span class="tag">SQL</span>
                        <span class="tag">Excel</span>
                    </div>
                </div>

                <div class="card purple-hover">
                    <h3>🗄️ Sistema de Banco de Dados</h3>
                    <p style="color: var(--text-muted);">Projeto acadêmico envolvendo modelagem de banco de dados, relacionamentos entre entidades e consultas SQL.</p>
                    <div class="tags">
                        <span class="tag">SQL</span>
                        <span class="tag">MySQL</span>
                        <span class="tag">Modelagem</span>
                    </div>
                    <a href="#" class="project-link">Ver projeto</a>
                </div>

                <div class="card purple-hover">
                    <h3>🌡️ Monitoramento IoT</h3>
                    <p style="color: var(--text-muted);">Sistema desenvolvido para coletar temperatura e umidade e enviar os dados para uma plataforma de monitoramento.</p>
                    <div class="tags">
                        <span class="tag">ESP32</span>
                        <span class="tag">MicroPython</span>
                        <span class="tag">DHT11</span>
                        <span class="tag">ThingSpeak</span>
                    </div>
                    <a href="#" class="project-link">Ver projeto</a>
                </div>

                <div class="card">
                    <h3>🍎 Projeto Scratch</h3>
                    <p style="color: var(--text-muted);">Pequena experiência interativa desenvolvida para praticar lógica, eventos, variáveis e interação entre objetos.</p>
                    <div class="tags">
                        <span class="tag">Scratch</span>
                        <span class="tag">Lógica de programação</span>
                    </div>
                    <a href="#" class="project-link">Ver projeto</a>
                </div>
            </div>
        </section>

        <!-- Habilidades -->
        <section id="habilidades">
            <h2>03. Habilidades</h2>
            <div class="grid-3">
                <div class="card purple-hover">
                    <h3>📊 Dados</h3>
                    <ul>
                        <li>SQL</li>
                        <li>Banco de Dados</li>
                        <li>Modelagem de dados</li>
                        <li>Excel</li>
                        <li>Power BI (em aprendizado)</li>
                    </ul>
                </div>
                <div class="card">
                    <h3>💻 Desenvolvimento</h3>
                    <ul>
                        <li>Python</li>
                        <li>HTML/CSS</li>
                        <li>Lógica de programação</li>
                        <li>Git/GitHub</li>
                    </ul>
                </div>
                <div class="card purple-hover">
                    <h3>⚙️ Outros</h3>
                    <ul>
                        <li>ESP32</li>
                        <li>MicroPython</li>
                        <li>IoT</li>
                        <li>ThingSpeak</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Formação e Experiência -->
        <section id="trajetoria">
            <h2>04. Trajetória</h2>
            <div class="grid-2">
                <div class="card">
                    <h3 style="color: var(--accent-cyan);">📚 Formação</h3>
                    <p class="code-font" style="margin: 10px 0; color: var(--text-main);">PUCPR — Análise e Desenvolvimento de Sistemas</p>
                    <p style="color: var(--text-muted); font-size: 0.9rem; margin-bottom: 15px;">3º semestre • Em andamento</p>
                    <p style="color: var(--text-muted); font-size: 0.95rem;"><strong>Áreas de interesse:</strong> desenvolvimento, dados, banco de dados, análise de sistemas e tecnologia.</p>
                </div>

                <div class="card purple-hover">
                    <h3 style="color: var(--accent-purple);">💼 Experiência</h3>
                    <p class="code-font" style="margin: 10px 0; color: var(--text-main);">QuintoAndar — Analista de Atendimento</p>
                    <ul>
                        <li>Atendimento e suporte ao cliente</li>
                        <li>Análise de demandas</li>
                        <li>Acompanhamento de processos</li>
                        <li>Resolução de problemas</li>
                        <li>Organização de informações</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Currículo -->
        <section id="curriculo" style="text-align: center; border-bottom: none;">
            <h2>05. Currículo</h2>
            <p style="margin-bottom: 30px; color: var(--text-muted);">Faça o download do meu currículo completo em PDF para conferir mais detalhes.</p>
            <a href="file:///C:/Users/eilis/Downloads/apple%20academy%20project/Curriculo_Nicoly_Ferreira_Ricardo_%20(1).pdf" target="_blank" class="btn btn-cyan">Baixar Currículo.pdf</a>
        </section>
    </div>

    <!-- Contato -->
    <footer id="contato">
        <h2 class="code-font" style="color: var(--text-main); font-size: 1.5rem; margin-bottom: 10px;">Buscando novas oportunidades?</h2>
        <p style="color: var(--text-muted); margin-bottom: 30px;">Minha caixa de entrada está sempre aberta para bate-papos sobre tecnologia e novos desafios.</p>
        
        <div class="contact-links">
            <a href="mailto:nicolyferreira.dev@gmail.com">📧 Email</a>
            <a href="tel:+5541998538742">📱 WhatsApp</a>
            <a href="https://www.linkedin.com/in/nicoly-ferreira-b357a6299/?isSelfProfile=true" target="_blank">💼 LinkedIn</a>
            <a href="https://github.com/Tokyow1tch" target="_blank">💻 GitHub</a>
        </div>
        
        <p style="color: var(--text-muted); font-size: 0.8rem; margin-top: 50px; font-family: 'Fira Code', monospace;">
            Nicoly Ferreira &copy; 2026
        </p>
    </footer>

</body>
</html>
