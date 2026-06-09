# projeto-site2<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jotapé Marketing | Líderes em Escala Digital</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* RESET E VARIÁVEIS DE DESIGN MULTI-AZUL */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            scroll-behavior: smooth;
        }

        :root {
            --bg-deep: #050c1a;       /* Azul Espacial Noturno (Fundo de alto padrão) */
            --bg-card: #0b1528;       /* Azul Escuro Sólido */
            --blue-main: #0052d4;     /* Azul Royal (Autoridade e Confiança) */
            --blue-electric: #00d2ff; /* Azul Ciano Neon (Chamar atenção imediata) */
            --blue-light: #f0f7ff;    /* Fundo claro para contrastar textos */
            --text-dark: #0f172a;
            --text-muted: #94a3b8;
            --white: #ffffff;
        }

        body {
            background-color: var(--bg-deep);
            color: var(--white);
            overflow-x: hidden;
        }

        a { text-decoration: none; color: inherit; }

        /* CABEÇALHO FLUTUANTE ULTRA-INTUITIVO */
        header {
            background-color: rgba(5, 12, 26, 0.95);
            backdrop-filter: blur(10px);
            padding: 20px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(0, 210, 255, 0.15);
        }

        .logo {
            font-size: 26px;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: -1px;
        }

        .logo span { color: var(--blue-electric); }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav ul li a {
            font-weight: 600;
            font-size: 15px;
            color: var(--white);
            transition: color 0.3s;
        }

        nav ul li a:hover { color: var(--blue-electric); }

        /* HERO SECTION: IMPACTO MÁXIMO EM TELA CHEIA (100vh) */
        .hero {
            min-height: 100vh;
            background: radial-gradient(circle at top right, #092047 0%, var(--bg-deep) 70%);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 120px 8% 60px 8%;
            text-align: center;
            position: relative;
        }

        .badge-chamativa {
            background: rgba(0, 210, 255, 0.1);
            border: 1px solid var(--blue-electric);
            color: var(--blue-electric);
            padding: 8px 20px;
            border-radius: 50px;
            font-size: 13px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            margin-bottom: 25px;
            animation: pulse 2s infinite;
        }

        .hero h1 {
            font-size: 56px;
            font-weight: 900;
            line-height: 1.1;
            max-width: 1000px;
            margin-bottom: 25px;
            letter-spacing: -1px;
        }

        .hero h1 span {
            background: linear-gradient(45deg, var(--blue-electric), #4364f7);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 20px;
            color: var(--text-muted);
            max-width: 750px;
            margin-bottom: 45px;
            line-height: 1.6;
        }

        /* BOTÕES DE CONVERSÃO RÁPIDA */
        .botoes-grupo {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn {
            padding: 16px 38px;
            border-radius: 8px;
            font-weight: 700;
            font-size: 16px;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
        }

        .btn-principal {
            background-color: #25d366; /* Verde comercial do WhatsApp */
            color: var(--white);
            box-shadow: 0 8px 24px rgba(37, 211, 102, 0.3);
        }

        .btn-principal:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(37, 211, 102, 0.5);
        }

        .btn-secundario {
            background: linear-gradient(135deg, var(--blue-main), #1e40af);
            color: var(--white);
            border: 1px solid rgba(0, 210, 255, 0.3);
            box-shadow: 0 8px 24px rgba(0, 82, 212, 0.3);
        }

        .btn-secundario:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(0, 82, 212, 0.5);
        }

        /* CONFIGURAÇÕES COLETIVAS DE SEÇÃO */
        section { padding: 100px 8%; }

        .header-secao {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 60px auto;
        }

        .header-secao h2 {
            font-size: 38px;
            font-weight: 800;
            color: var(--white);
            margin-bottom: 15px;
        }

        .header-secao h2 span { color: var(--blue-electric); }

        .header-secao p { font-size: 17px; color: var(--text-muted); }

        /* ABA: QUEM SOMOS NÓS? */
        .quem-somos { background-color: var(--bg-card); }

        .bloco-conteudo {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .texto-narrativo h3 {
            font-size: 26px;
            color: var(--white);
            margin-bottom: 20px;
            font-weight: 700;
        }

        .texto-narrativo p {
            font-size: 16px;
            color: #cbd5e1;
            margin-bottom: 20px;
            text-align: justify;
            line-height: 1.7;
        }

        .numeros-ajuda {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .box-metrica {
            background-color: var(--bg-deep);
            padding: 30px;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            text-align: center;
        }

        .box-metrica h4 { font-size: 36px; color: var(--blue-electric); font-weight: 800; }
        .box-metrica p { font-size: 14px; color: var(--text-muted); font-weight: 600; }

        /* ABA: COMO PODEMOS ALAVANCAR SUA EMPRESA (Baita Propaganda) */
        .alavancagem {
            background: linear-gradient(180deg, var(--bg-deep) 0%, #061329 100%);
        }

        .propaganda-impacto {
            background: linear-gradient(135deg, rgba(0, 82, 212, 0.2), rgba(11, 21, 40, 0.8));
            border: 1px solid rgba(0, 210, 255, 0.3);
            padding: 45px;
            border-radius: 16px;
            margin-bottom: 50px;
        }

        .propaganda-impacto h3 { font-size: 24px; margin-bottom: 15px; color: var(--white); }
        .propaganda-impacto p { color: #cbd5e1; font-size: 16px; line-height: 1.8; margin-bottom: 15px; }

        .lista-beneficios {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .card-beneficio {
            background-color: var(--bg-card);
            padding: 30px;
            border-radius: 12px;
            transition: all 0.3s;
            border-left: 4px solid var(--blue-electric);
        }

        .card-beneficio:hover { transform: translateY(-5px); background-color: #0e1e38; }
        .card-beneficio i { font-size: 28px; color: var(--blue-electric); margin-bottom: 15px; }
        .card-beneficio h4 { font-size: 18px; margin-bottom: 10px; }
        .card-beneficio p { font-size: 14px; color: var(--text-muted); }

        /* ABA: NOSSOS SERVIÇOS (Divulgação Completa Sem Lotes) */
        .nossos-servicos {
            background-color: var(--bg-card);
        }

        .vitrine-servicos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }

        .box-servico {
            background-color: var(--bg-deep);
            padding: 40px 30px;
            border-radius: 16px;
            border: 1px solid rgba(255,255,255,0.03);
            transition: all 0.3s ease;
        }

        .box-servico:hover {
            border-color: var(--blue-electric);
            box-shadow: 0 10px 30px rgba(0, 210, 255, 0.1);
            transform: translateY(-5px);
        }

        .box-servico .icon-wrapper {
            width: 60px;
            height: 60px;
            background: rgba(0, 82, 212, 0.2);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 25px;
            color: var(--blue-electric);
            font-size: 24px;
            border: 1px solid rgba(0, 210, 255, 0.2);
        }

        .box-servico h3 {
            font-size: 22px;
            margin-bottom: 15px;
            font-weight: 700;
        }

        .box-servico p {
            font-size: 15px;
            color: #cbd5e1;
            line-height: 1.7;
            margin-bottom: 20px;
        }

        .box-servico ul {
            list-style: none;
        }

        .box-servico ul li {
            font-size: 14px;
            color: var(--text-muted);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .box-servico ul li i {
            color: var(--blue-electric);
            font-size: 12px;
        }

        /* SEÇÃO FINAL: CALL TO ACTION */
        .cta-final {
            background: linear-gradient(135deg, var(--bg-deep) 0%, #06152d 100%);
            text-align: center;
            border-top: 1px solid rgba(0, 210, 255, 0.1);
        }

        .cta-box {
            max-width: 750px;
            margin: 0 auto;
        }

        .cta-box h3 {
            font-size: 36px;
            font-weight: 850;
            margin-bottom: 20px;
        }

        .cta-box p {
            color: #cbd5e1;
            font-size: 17px;
            line-height: 1.8;
            margin-bottom: 40px;
        }

        /* MODAL DE SELEÇÃO ULTRA-INTUITIVA DE WHATSAPP */
        .modal-whats {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(5, 12, 26, 0.85);
            backdrop-filter: blur(8px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }

        .modal-box {
            background-color: var(--bg-card);
            border: 2px solid var(--blue-electric);
            border-radius: 16px;
            padding: 40px 30px;
            max-width: 480px;
            width: 90%;
            text-align: center;
            position: relative;
            box-shadow: 0 20px 50px rgba(0, 210, 255, 0.2);
        }

        .modal-box h4 {
            font-size: 22px;
            margin-bottom: 10px;
            font-weight: 800;
        }

        .modal-box p {
            color: var(--text-muted);
            font-size: 15px;
            margin-bottom: 30px;
        }

        .modal-opcoes {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .btn-modal-whats {
            background-color: #25d366;
            color: var(--white);
            padding: 14px;
            border-radius: 8px;
            font-weight: 700;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: transform 0.2s, background-color 0.2s;
        }

        .btn-modal-whats:hover {
            transform: scale(1.02);
            background-color: #1ebd54;
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 22px;
            color: var(--text-muted);
            cursor: pointer;
            transition: color 0.2s;
        }

        .close-modal:hover { color: var(--white); }

        /* FOOTER */
        footer {
            background-color: #030712;
            padding: 40px 8%;
            text-align: center;
            font-size: 14px;
            color: var(--text-muted);
            border-top: 1px solid rgba(255,255,255,0.05);
        }

        /* INTERFACE RESPONSIVA */
        @media (max-width: 968px) {
            .bloco-conteudo { grid-template-columns: 1fr; gap: 40px; }
            .hero h1 { font-size: 36px; }
            .hero p { font-size: 16px; }
            header { padding: 20px 5%; }
            nav { display: none; } 
            section { padding: 70px 5%; }
            .btn { width: 100%; justify-content: center; }
            .header-secao h2 { font-size: 30px; }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">Jotapé<span>Marketing</span></div>
        <nav>
            <ul>
                <li><a href="#inicio">Início</a></li>
                <li><a href="#quem-somos">Quem Somos</a></li>
                <li><a href="#alavancar">Alavancagem</a></li>
                <li><a href="#servicos">Nossos Serviços</a></li>
            </ul>
        </nav>
    </header>

    <section class="hero" id="inicio">
        <div class="badge-chamativa"><i class="fas fa-fire"></i> Posicionamento de Elite</div>
        <h1>Não Seja Apenas Mais Um Perfil. Seja a <span>Marca Líder</span> do Seu Mercado.</h1>
        <p>A maioria das empresas joga dinheiro fora postando conteúdos sem estratégia e vazios de conversão. Nós assumimos a sua marca e geramos desejo real nos clientes que têm poder de compra.</p>
        
        <div class="botoes-grupo">
            <button onclick="abrirModal()" class="btn btn-principal">
                <i class="fab fa-whatsapp"></i> Garantir Minha Estratégia
            </button>
            <a href="https://www.instagram.com/jp.marketing.oficial?utm_source=qr" target="_blank" class="btn btn-secundario">
                <i class="fab fa-instagram"></i> Seguir no Instagram
            </a>
        </div>
    </section>

    <section class="quem-somos" id="quem-somos">
        <div class="header-secao">
            <h2>Quem Somos <span>Nós?</span></h2>
            <p>Conheça a mente por trás da escala do seu faturamento.</p>
        </div>

        <div class="bloco-conteudo">
            <div class="texto-narrativo">
                <h3>Uma Estrutura Altamente Qualificada Focada em Resultados Reais</h3>
                <p>A <strong>Jotapé Marketing</strong> não é apenas uma agência de "postagens bonitinhas". Somos uma operação de elite voltada para crescimento comercial, engenharia de tráfego e branding de alta percepção. Nosso time é composto por especialistas em Copywriting (escrita de conversão), Designers de Alto Impacto e Gestores de Tráfego qualificados para investir e multiplicar o seu capital através de anúncios.</p>
                <p>Nossa filosofia de trabalho rejeita métricas de vaidade como curtidas ou visualizações que não pagam contas. Trabalhamos exclusivamente para construir autoridade, atrair leads qualificados e estruturar funis que convertem visitas em dinheiro no seu caixa.</p>
            </div>
            
            <div class="numeros-ajuda">
                <div class="box-metrica">
                    <h4>+100%</h4>
                    <p>Foco em Escala Máxima</p>
                </div>
                <div class="box-metrica">
                    <h4>100%</h4>
                    <p>Time Altamente Qualificado</p>
                </div>
                <div class="box-metrica">
                    <h4>24/7</h4>
                    <p>Sua Marca Vendendo Sempre</p>
                </div>
                <div class="box-metrica">
                    <h4>0%</h4>
                    <p>Amadorismo ou Clichês</p>
                </div>
            </div>
        </div>
    </section>

    <section class="alavancagem" id="alavancar">
        <div class="header-secao">
            <h2>Como Vamos Alavancar Sua Empresa ao <span>Nível Máximo?</span></h2>
            <p>Descubra o plano tático que vai tirar o seu negócio do anonimato.</p>
        </div>

        <div class="propaganda-impacto">
            <h3>🔥 A Verdade que Ninguém te Conta Sobre o Mercado Digital:</h3>
            <p>Seus potenciais clientes estão no Instagram agora mesmo, mas eles estão comprando do concorrente que parece mais profissional que você. O mercado não perdoa o amadorismo. Para crescer de verdade e alcançar o faturamento máximo, você precisa de um ecossistema completo rodando de forma impecável.</p>
            <p>Nós não oferecemos apenas postagens: nós injetamos uma estratégia de guerra na sua empresa. Analisamos minuciosamente o mercado local, descobrimos as falhas dos seus concorrentes e blindamos as suas redes sociais com uma comunicação tão poderosa que torna impossível para o cliente escolher outra empresa.</p>
        </div>

        <div class="lista-beneficios">
            <div class="card-beneficio">
                <i class="fas fa-bullseye"></i>
                <h4>Atração de Clientes de Alto Padrão</h4>
                <p>Desenhamos conteúdos e criamos campanhas direcionadas especificamente para o público com poder aquisitivo real dentro do seu nicho.</p>
            </div>
            <div class="card-beneficio">
                <i class="fas fa-rocket"></i>
                <h4>Velocidade com Tráfego Pago</h4>
                <p>Colocamos seu produto ou serviço na frente de milhares de pessoas qualificadas na sua cidade todos os dias através de anúncios certeiros.</p>
            </div>
            <div class="card-beneficio">
                <i class="fas fa-crown"></i>
                <h4>Construção de Autoridade Absoluta</h4>
                <p>Transformamos o seu conhecimento em um visual de alto padrão, fazendo com que você cobre mais caro sem perder clientes.</p>
            </div>
        </div>
    </section>

    <section class="nossos-servicos" id="servicos">
        <div class="header-secao">
            <h2>Nossos <span>Serviços e Soluções</span></h2>
            <p>Uma linha de frente completa para dominar o mercado e estruturar suas vendas digitais de ponta a ponta.</p>
        </div>

        <div class="vitrine-servicos">
            <div class="box-servico">
                <div class="icon-wrapper"><i class="fas fa-palette"></i></div>
                <h3>Design & Branding Premium</h3>
                <p>O amadorismo visual afasta o cliente com dinheiro. Nós reconstruímos toda a identidade visual das suas redes para transmitir sofisticação, liderança e gerar desejo imediato pelo seu produto ou serviço.</p>
                <ul>
                    <li><i class="fas fa-arrow-right"></i> Identidade de feed exclusiva</li>
                    <li><i class="fas fa-arrow-right"></i> Carrosséis de altíssima conversão</li>
                    <li><i class="fas fa-arrow-right"></i> Capas de destaque personalizadas</li>
                </ul>
            </div>

            <div class="box-servico">
                <div class="icon-wrapper"><i class="fas fa-ad"></i></div>
                <h3>Tráfego Pago & Anúncios</h3>
                <p>Chega de depender apenas do algoritmo orgânico. Configuramos e otimizamos anúncios cirúrgicos no Meta Ads (Instagram/Facebook) e Google Ads para atrair compradores reais batendo no seu WhatsApp diariamente.</p>
                <ul>
                    <li><i class="fas fa-arrow-right"></i> Segmentação local avançada</li>
                    <li><i class="fas fa-arrow-right"></i> Testes contínuos de criativos</li>
                    <li><i class="fas fa-arrow-right"></i> Otimização focada em menor custo por lead</li>
                </ul>
            </div>

            <div class="box-servico">
                <div class="icon-wrapper"><i class="fas fa-video"></i></div>
                <h3>Roteirização & Edição de Reels</h3>
                <p>O formato de vídeo curto é o coração da tração orgânica. Entregamos roteiros profissionais com ganchos psicológicos que retêm a atenção e fazemos edições dinâmicas com cortes precisos e legendas magnéticas.</p>
                <ul>
                    <li><i class="fas fa-arrow-right"></i> Roteiros com ganchos magnéticos</li>
                    <li><i class="fas fa-arrow-right"></i> Edição dinâmica de alta retenção</li>
                    <li><i class="fas fa-arrow-right"></i> Uso estratégico de áudios em alta</li>
                </ul>
            </div>

            <div class="box-servico">
                <div class="icon-wrapper"><i class="fas fa-brain"></i></div>
                <h3>Estratégias de Copywriting</h3>
                <p>Palavras certas geram vendas. Desenvolvemos narrativas persuasivas para suas legendas, Stories e scripts de vendas, quebrando as principais objeções do seu cliente antes mesmo de ele falar com o seu comercial.</p>
                <ul>
                    <li><i class="fas fa-arrow-right"></i> Quebra de objeções em massa</li>
                    <li><i class="fas fa-arrow-right"></i> Chamadas para ação (CTA) impossíveis de ignorar</li>
                    <li><i class="fas fa-arrow-right"></i> Textos focados em urgência e desejo</li>
                </ul>
            </div>
        </div>
    </section>

    <section class="cta-final">
        <div class="cta-box">
            <h3>Pronto para Deixar o Amadorismo para Trás?</h3>
            <p>Se o seu objetivo é parar de brincar nas redes sociais e estruturar uma verdadeira máquina de captação de clientes para o seu negócio, nós temos o time qualificado para fazer acontecer. Sem pacotes prontos, criamos o plano tático focado na sua realidade.</p>
            
            <div class="botoes-grupo">
                <button onclick="abrirModal()" class="btn btn-principal">
                    <i class="fab fa-whatsapp"></i> Destravar o Meu Faturamento Máximo
                </button>
                <a href="https://www.instagram.com/jp.marketing.oficial?utm_source=qr" target="_blank" class="btn btn-secundario">
                    <i class="fab fa-instagram"></i> Acompanhar no Instagram
                </a>
            </div>
        </div>
    </section>

    <div id="modalWhats" class="modal-whats">
        <div class="modal-box">
            <span onclick="fecharModal()" class="close-modal">&times;</span>
            <h4>Fale Conosco via WhatsApp</h4>
            <p>Escolha um de nossos especialistas comerciais abaixo para dar início ao seu projeto de escala digital:</p>
            <div class="modal-opcoes">
                <a href="https://wa.me/558193774327?text=Olá! Estive no site da Jotapé Marketing e quero alavancar as vendas da minha marca." target="_blank" class="btn-modal-whats">
                    <i class="fab fa-whatsapp"></i> Consultor Comercial (Opção 01)
                </a>
                <a href="https://wa.me/558196572994?text=Olá! Estive no site da Jotapé Marketing e quero alinhar uma consultoria estratégica para meu negócio." target="_blank" class="btn-modal-whats">
                    <i class="fab fa-whatsapp"></i> Consultor Comercial (Opção 02)
                </a>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 Jotapé Marketing. Todos os direitos reservados. Projetando empresas rumo ao topo digital.</p>
    </footer>

    <script>
        function abrirModal() {
            document.getElementById('modalWhats').style.display = 'flex';
        }
        function fecharModal() {
            document.getElementById('modalWhats').style.display = 'none';
        }
        // Fecha o pop-up caso o cliente clique fora da caixa escura
        window.onclick = function(event) {
            let modal = document.getElementById('modalWhats');
            if (event.target == modal) {
                modal.style.display = 'none';
            }
        }
    </script>

</body>
</html>
