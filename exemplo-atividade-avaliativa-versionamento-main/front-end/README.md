# 💻 Desenvolvimento Front-end

## 📝 Descrição do Projeto/Atividade
Site para o monitoramento e conectar o arduino ao site

---

## 🧠 Reflexão de Aprendizado

### 1. O que aprendi?
Aprendi a fazer um site pelo terminal do vs code
---

## 🛠️ Tecnologias e Ferramentas Utilizadas
*   HTML5 / CSS3 (Vanilla)
*   JavaScript (ES6+)
*   [Outra biblioteca ou ferramenta, ex: React, TailwindCSS, Chart.js]

---

## 💻 Codigo Html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AgroSmart | Irrigação Automática Inteligente</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/@phosphor-icons/web"></script>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>

    <!-- Navegação Superior -->
    <nav class="top-nav">
        <div class="logo">
            <i class="ph ph-drop-half-bottom"></i>
            <span>AgroSmart</span>
        </div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#dashboard">Dashboard</a></li>
            <li><a href="#sobre">Quem Somos</a></li>
            <li><a href="#areas">Áreas</a></li>
            <li><a href="#sistema">Sistema</a></li>
            <li><a href="#tecnico">Técnico</a></li>
            <li><a href="#sustentabilidade">Sustentabilidade</a></li>
            <li><a href="#equipe">Equipe</a></li>
        </ul>
    </nav>

    <main>
        <!-- HERO SECTION COM SLIDER -->
        <section id="home" class="hero-section">
            <div class="hero-slider">
                <div class="slide active">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ4DPDseHVkw7njNJ-2auVhDP7WlFuMtuu7Gg&s" alt="Irrigação">
                    <div class="slide-overlay"></div>
                    <div class="slide-content">
                        <h1>Irrigação Inteligente</h1>
                        <p>Tecnologia que preserva o futuro do nosso planeta</p>
                    </div>
                </div>
                <div class="slide">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTAlhLxv7-_k1NSFj8yUY3ay4_e-mpZ1zOeDA&s" alt="Agricultura">
                    <div class="slide-overlay"></div>
                    <div class="slide-content">
                        <h1>Economia de Água</h1>
                        <p>Reduza até 50% no consumo com automação precisa</p>
                    </div>
                </div>
                <div class="slide">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTi-AD-bW_zgRd2W08_Vz4sV8l_tRqIl5tHSA&s" alt="Sustentabilidade">
                    <div class="slide-overlay"></div>
                    <div class="slide-content">
                        <h1>Sustentabilidade Real</h1>
                        <p>Aliando tecnologia e consciência ambiental</p>
                    </div>
                </div>
                <div class="slide">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTbd-_xyHSpbyjktLaJCBaDAgtJITdQw8TRbA&s" alt="Tecnologia">
                    <div class="slide-overlay"></div>
                    <div class="slide-content">
                        <h1>Controle Total</h1>
                        <p>Monitore e controle de qualquer lugar do mundo</p>
                    </div>
                </div>
            </div>
            
            <button class="slider-btn prev" onclick="changeSlide(-1)"><i class="ph ph-caret-left"></i></button>
            <button class="slider-btn next" onclick="changeSlide(1)"><i class="ph ph-caret-right"></i></button>
            
            <div class="slider-dots">
                <span class="dot active" onclick="currentSlide(1)"></span>
                <span class="dot" onclick="currentSlide(2)"></span>
                <span class="dot" onclick="currentSlide(3)"></span>
                <span class="dot" onclick="currentSlide(4)"></span>
            </div>
        </section>

        <!-- SEÇÃO: DASHBOARD -->
        <section id="dashboard" class="section">
            <div class="section-header">
                <div class="header-badge">
                    <i class="ph ph-chart-line-up"></i>
                    <span>MONITORAMENTO EM TEMPO REAL</span>
                </div>
                <h1>Painel de Controle Inteligente</h1>
                <p>Acompanhe todos os dados do seu sistema de irrigação</p>
            </div>
            
            <div class="cards-grid">
                <div class="card stat-card gradient-card-1">
                    <div class="card-icon-wrapper">
                        <i class="ph ph-plant"></i>
                    </div>
                    <h3>Umidade do Solo</h3>
                    <p class="value" id="umidade">--%</p>
                    <div class="card-footer">
                        <span class="status-indicator active"></span>
                        <span>Sensor Ativo</span>
                    </div>
                </div>
                <div class="card stat-card gradient-card-2">
                    <div class="card-icon-wrapper">
                        <i class="ph ph-thermometer"></i>
                    </div>
                    <h3>Temperatura</h3>
                    <p class="value" id="temperatura">--°C</p>
                    <div class="card-footer">
                        <span class="status-indicator active"></span>
                        <span>Monitorando</span>
                    </div>
                </div>
                <div class="card stat-card gradient-card-3">
                    <div class="card-icon-wrapper">
                        <i class="ph ph-drop"></i>
                    </div>
                    <h3>Consumo de Água</h3>
                    <p class="value" id="consumo">-- L</p>
                    <div class="card-footer">
                        <span class="status-indicator active"></span>
                        <span>Economizando</span>
                    </div>
                </div>
                <div class="card action-card gradient-card-4">
                    <div class="card-icon-wrapper">
                        <i class="ph ph-power"></i>
                    </div>
                    <h3>Irrigação Manual</h3>
                    <button id="btn-irrigar" class="btn-primary" onclick="toggleIrrigation()">
                        <i class="ph ph-play"></i> Ativar Agora
                    </button>
                </div>
            </div>
        </section>

        <!-- SEÇÃO: QUEM SOMOS -->
        <section id="sobre" class="section bg-gradient">
            <div class="section-header">
                <div class="header-badge">
                    <i class="ph ph-lightbulb"></i>
                    <span>QUEM SOMOS</span>
                </div>
                <h2>Por que estamos fazendo?</h2>
                <p>Aprofundado na realidade ambiental e tecnológica</p>
            </div>

            <div class="grid-2">
                <div class="info-card">
                    <div class="info-icon">
                        <i class="ph ph-globe"></i>
                    </div>
                    <h3>Escassez Hídrica Global</h3>
                    <p>A água potável representa menos de 1% de toda a água do planeta. Diante do crescimento populacional, gerenciar esse recurso não é mais uma escolha, mas uma obrigação.</p>
                </div>
                <div class="info-card">
                    <div class="info-icon">
                        <i class="ph ph-drop-slash"></i>
                    </div>
                    <h3>Desperdício Invisível</h3>
                    <p>Na irrigação comum, grande parte da água evapora antes de atingir as raízes ou penetra fundo demais no solo, carregando nutrientes embora (lixiviação).</p>
                </div>
                <div class="info-card">
                    <div class="info-icon">
                        <i class="ph ph-cloud-rain"></i>
                    </div>
                    <h3>Mudanças Climáticas</h3>
                    <p>O regime de chuvas mudou no mundo todo. Produtores rurais e gestores urbanos não podem mais depender do clima para planejar suas regas.</p>
                </div>
                <div class="info-card">
                    <div class="info-icon">
                        <i class="ph ph-database"></i>
                    </div>
                    <h3>Falta de Dados no Campo</h3>
                    <p>A maioria das pessoas irriga no "olhômetro". Sem dados exatos, gasta-se mais dinheiro, mais energia elétrica e mais água do que o necessário.</p>
                </div>
            </div>

            <div class="section-header" style="margin-top: 4rem;">
                <h2>Nosso Objetivo</h2>
            </div>
            <div class="grid-4">
                <div class="objective-card">
                    <div class="obj-icon">
                        <i class="ph ph-code"></i>
                    </div>
                    <h4>Desenvolver Tecnologia Nacional</h4>
                    <p>Criar um ecossistema inteligente, utilizando componentes acessíveis e software livre para baratear o custo final.</p>
                </div>
                <div class="objective-card">
                    <div class="obj-icon">
                        <i class="ph ph-leaf"></i>
                    </div>
                    <h4>Preservar Recursos Naturais</h4>
                    <p>Reduzir o consumo de água na agricultura, jardinagem e recuperação ambiental em larga escala.</p>
                </div>
                <div class="objective-card">
                    <div class="obj-icon">
                        <i class="ph ph-device-mobile"></i>
                    </div>
                    <h4>Acessibilidade Digital</h4>
                    <p>Entregar um painel web tão simples que qualquer pessoa, mesmo sem conhecimento técnico, consiga usar.</p>
                </div>
                <div class="objective-card">
                    <div class="obj-icon">
                        <i class="ph ph-recycle"></i>
                    </div>
                    <h4>Promover Sustentabilidade Ativa</h4>
                    <p>Transformar dados brutos em ações ecológicas práticas que geram impacto imediato no meio ambiente.</p>
                </div>
            </div>
        </section>

        <!-- SEÇÃO: ÁREAS DE ATUAÇÃO -->
        <section id="areas" class="section">
            <div class="section-header">
                <div class="header-badge">
                    <i class="ph ph-map-trifold"></i>
                    <span>APLICAÇÕES</span>
                </div>
                <h2>Áreas de Atuação e Aplicação Expandida</h2>
            </div>

            <div class="area-block">
                <h3 class="area-title">
                    <i class="ph ph-tree"></i>
                    <span>Áreas Verdes</span>
                    <span class="area-subtitle">Preservação, Produção e Paisagismo</span>
                </h3>

                <div class="image-gallery">
                    <div class="gallery-item">
                        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTi-AD-bW_zgRd2W08_Vz4sV8l_tRqIl5tHSA&s" alt="Agricultura">
                        <div class="gallery-overlay">
                            <h4>Agricultura de Precisão</h4>
                            <p>Adaptação a diferentes culturas</p>
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTbd-_xyHSpbyjktLaJCBaDAgtJITdQw8TRbA&s" alt="Paisagismo">
                        <div class="gallery-overlay">
                            <h4>Paisagismo Urbano Inteligente</h4>
                            <p>Paredes verdes e parques</p>
                        </div>
                    </div>
                    <div class="gallery-item">
                        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQf6Vuy2F1Yl_62pCsYXOu4gbt5_9yS3qjEIA&s" alt="Estufas">
                        <div class="gallery-overlay">
                            <h4>Estufas e Hidroponia</h4>
                            <p>Monitoramento milimétrico</p>
                        </div>
                    </div>
                </div>

                <div class="grid-3">
                    <div class="area-card">
                        <div class="area-icon">
                            <i class="ph ph-carrot"></i>
                        </div>
                        <h4>Agricultura de Precisão</h4>
                        <p>O sistema se adapta a diferentes culturas (hortaliças, grãos, frutas). Ele entende que um pé de alface precisa de uma umidade diferente de um pé de tomate, aplicando a gota exata.</p>
                    </div>
                    <div class="area-card">
                        <div class="area-icon">
                            <i class="ph ph-buildings"></i>
                        </div>
                        <h4>Paisagismo Urbano Inteligente</h4>
                        <p>Perfeito para "paredes verdes" de prédios modernos, canteiros centrais de avenidas e parques públicos. Evita que a água respingue nas calçadas ou evapore no asfalto quente.</p>
                    </div>
                    <div class="area-card">
                        <div class="area-icon">
                            <i class="ph ph-flower-lotus"></i>
                        </div>
                        <h4>Estufas e Hidroponia</h4>
                        <p>Monitoramento milimétrico para o cultivo de plantas sensíveis. O sistema cria um microclima ideal, regulando o fluxo de água de acordo com a umidade interna do ar.</p>
                    </div>
                </div>
            </div>

            <div class="area-block">
                <h3 class="area-title recovery">
                    <i class="ph ph-seedling"></i>
                    <span>Recuperação Ambiental</span>
                    <span class="area-subtitle">Recuperação e Regeneração</span>
                </h3>

                <div class="grid-3">
                    <div class="area-card">
                        <div class="area-icon">
                            <i class="ph ph-tree-structure"></i>
                        </div>
                        <h4>Reflorestamento de Precisão</h4>
                        <p>Áreas que sofreram queimadas perdem a cobertura vegetal protetora. As novas mudas morrem facilmente com o sol forte. O sistema garante o fornecimento crítico de água até que as raízes fiquem profundas.</p>
                    </div>
                    <div class="area-card">
                        <div class="area-icon">
                            <i class="ph ph-sparkle"></i>
                        </div>
                        <h4>Recuperação de Solos Degradados</h4>
                        <p>Solos compactados ou arenosos demais têm dificuldade para reter nutrientes. A irrigação suave e automatizada mantém a terra úmida o suficiente para que microrganismos benéficos voltem a habitar o local.</p>
                    </div>
                    <div class="area-card">
                        <div class="area-icon">
                            <i class="ph ph-shield-check"></i>
                        </div>
                        <h4>Controle da Desertificação</h4>
                        <p>Em regiões semiáridas, o sistema ajuda a fixar barreiras de vegetação nativa, impedindo que a areia e a seca avancem sobre terras produtivas.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- SEÇÃO: SISTEMA -->
        <section id="sistema" class="section bg-gradient">
            <div class="section-header">
                <div class="header-badge">
                    <i class="ph ph-cpu"></i>
                    <span>TECNOLOGIA</span>
                </div>
                <h2>O Sistema e Suas Funcionalidades Técnicas</h2>
            </div>

            <div class="section-header" style="margin-top: 3rem;">
                <h3 style="font-size: 2rem; margin-bottom: 1rem;">Funcionalidade do Site</h3>
            </div>
            <div class="grid-2">
                <div class="info-card">
                    <div class="info-icon">
                        <i class="ph ph-monitor"></i>
                    </div>
                    <h3>Dashboard em Tempo Real</h3>
                    <p>Telas limpas com gráficos de linha que mostram a umidade do solo, temperatura ambiente e previsão do tempo local.</p>
                </div>
                <div class="info-card">
                

