<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Natural Tech Solutions 🚀</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0c0c0c, #2d1b69);
            color: #fff;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            min-height: 100vh;
        }

        /* Steps */
        .step {
            display: none;
            animation: fadeIn 0.5s ease-in;
        }

        .step.active {
            display: block;
        }

        /* Card Style */
        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 25px;
            padding: 40px;
            margin: 20px auto;
            max-width: 500px;
            border: 2px solid rgba(138, 43, 232, 0.3);
            box-shadow: 0 0 50px rgba(138, 43, 232, 0.2);
            text-align: center;
        }

        /* Emoji Header */
        .emoji-header {
            font-size: 4em;
            margin-bottom: 20px;
            filter: drop-shadow(0 0 20px rgba(255, 255, 255, 0.5));
            animation: float 3s ease-in-out infinite;
        }

        h1 {
            font-size: 2.5em;
            margin-bottom: 15px;
            background: linear-gradient(45deg, #8a2be8, #ff00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 30px rgba(138, 43, 232, 0.5);
        }

        h2 {
            color: #9370db;
            margin-bottom: 25px;
            font-size: 1.8em;
        }

        p {
            font-size: 1.2em;
            line-height: 1.6;
            margin-bottom: 20px;
            opacity: 0.9;
        }

        /* Forms */
        .form-group {
            margin: 25px 0;
            text-align: left;
        }

        label {
            display: block;
            margin-bottom: 10px;
            color: #b19cd9;
            font-size: 1.1em;
            font-weight: bold;
        }

        input, select {
            width: 100%;
            padding: 15px 20px;
            border: 2px solid #8a2be8;
            border-radius: 15px;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            font-size: 1.1em;
            transition: all 0.3s ease;
        }

        input:focus, select:focus {
            outline: none;
            border-color: #ff00ff;
            box-shadow: 0 0 20px rgba(255, 0, 255, 0.5);
            transform: scale(1.02);
        }

        /* Buttons */
        .btn {
            background: linear-gradient(45deg, #8a2be8, #ff00ff);
            color: white;
            border: none;
            padding: 18px 40px;
            border-radius: 50px;
            font-size: 1.3em;
            font-weight: bold;
            cursor: pointer;
            margin: 15px 10px;
            transition: all 0.3s ease;
            box-shadow: 0 0 30px rgba(138, 43, 232, 0.4);
            position: relative;
            overflow: hidden;
        }

        .btn:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 0 40px rgba(255, 0, 255, 0.6);
        }

        /* Products Grid */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 25px;
            margin: 30px 0;
        }

        .product-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 20px;
            padding: 25px;
            text-align: center;
            border: 2px solid transparent;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .product-card:hover {
            border-color: #8a2be8;
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 15px 40px rgba(138, 43, 232, 0.3);
        }

        .product-emoji {
            font-size: 3em;
            margin-bottom: 15px;
            filter: drop-shadow(0 0 15px rgba(255, 255, 255, 0.3));
        }

        .product-name {
            font-size: 1.6em;
            color: #9370db;
            margin-bottom: 10px;
            font-weight: bold;
        }

        .product-stock {
            color: #90ee90;
            font-size: 1.1em;
            margin: 10px 0;
            font-weight: bold;
        }

        .product-price {
            font-size: 2em;
            color: #ffd700;
            font-weight: bold;
            margin: 15px 0;
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.3);
        }

        .product-details {
            list-style: none;
            margin: 15px 0;
            text-align: left;
        }

        .product-details li {
            margin: 8px 0;
            padding-left: 25px;
            position: relative;
            opacity: 0.9;
            font-size: 0.95em;
        }

        .product-details li::before {
            content: '✨';
            position: absolute;
            left: 0;
        }

        /* Cart */
        .cart-section {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            margin: 30px 0;
            border: 2px solid #8a2be8;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            margin: 15px 0;
            border: 1px solid rgba(138, 43, 232, 0.3);
        }

        .cart-total {
            text-align: center;
            font-size: 2em;
            color: #ffd700;
            margin: 30px 0;
            font-weight: bold;
        }

        /* Final Step */
        .telegram-link {
            display: inline-block;
            background: #0088cc;
            color: white;
            padding: 20px 40px;
            border-radius: 50px;
            font-size: 1.4em;
            font-weight: bold;
            text-decoration: none;
            margin: 20px 0;
            transition: all 0.3s ease;
            box-shadow: 0 0 30px rgba(0, 136, 204, 0.5);
        }

        .telegram-link:hover {
            transform: scale(1.1);
            box-shadow: 0 0 40px rgba(0, 136, 204, 0.8);
        }

        /* Warning */
        .simulation-warning {
            background: rgba(255, 165, 0, 0.2);
            border: 2px solid #ffa500;
            padding: 15px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: center;
            font-size: 1.1em;
        }

        /* Category Sections */
        .category-section {
            margin: 40px 0;
        }

        .category-title {
            text-align: center;
            margin-bottom: 30px;
            color: #ffd700;
            font-size: 2em;
        }

        /* Color Selector */
        .color-selector {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 20px 0;
        }

        .color-option {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            border: 3px solid transparent;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
        }

        .color-option.selected {
            border-color: #ffd700;
            transform: scale(1.2);
            box-shadow: 0 0 15px #ffd700;
        }

        .color-black { background: #000; }
        .color-purple { background: #8a2be8; }
        .color-metal { 
            background: linear-gradient(45deg, #c0c0c0, #708090);
            border: 1px solid #fff;
        }

        /* Bank Filter */
        .bank-filter {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }

        .bank-btn {
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid #8a2be8;
            color: white;
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .bank-btn.active {
            background: #8a2be8;
            transform: scale(1.1);
        }

        .bank-btn:hover {
            background: #8a2be8;
            transform: scale(1.05);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .card {
                margin: 10px;
                padding: 25px;
            }
            
            h1 {
                font-size: 2em;
            }
            
            .products-grid {
                grid-template-columns: 1fr;
            }
            
            .btn {
                padding: 15px 30px;
                font-size: 1.1em;
            }
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Step 1: Age Verification -->
        <div class="step active" id="step1">
            <div class="card">
                <div class="emoji-header">🔞</div>
                <h1>Natural Tech Solutions 🚀</h1>
                <p>Bem-vindo à nossa plataforma completa de serviços!</p>
                <p>Para continuar, confirme que você é maior de 18 anos.</p>
                
                <div class="simulation-warning">
                    ⚠️ <strong>AVISO IMPORTANTE</strong><br>
                    Este site é uma simulação para fins educacionais.
                </div>
                
                <button class="btn" onclick="nextStep(2)">✨ Tenho mais de 18 anos!</button>
            </div>
        </div>

        <!-- Step 2: Name and Age -->
        <div class="step" id="step2">
            <div class="card">
                <div class="emoji-header">👤</div>
                <h1>Que bom te ver aqui! 💫</h1>
                <p>Vamos personalizar sua experiência!</p>
                
                <div class="form-group">
                    <label>🎀 Qual seu nome?</label>
                    <input type="text" id="userName" placeholder="Seu nome completo">
                </div>

                <div class="form-group">
                    <label>🎂 Qual sua idade?</label>
                    <input type="number" id="userAge" placeholder="Sua idade" min="18" max="120">
                </div>

                <button class="btn" onclick="validateAge()">🚀 Continuar para os Produtos!</button>
            </div>
        </div>

        <!-- Step 3: Products -->
        <div class="step" id="step3">
            <div class="card">
                <div class="emoji-header">🛍️</div>
                <h1>Nossos Serviços Premium! 🌟</h1>
                <p>Explore todas as categorias disponíveis!</p>
                
                <div class="simulation-warning">
                    💡 <strong>faz dinheiro nessa porra</strong><br>
                    Todos os produtos são fictícios para fins de aprendizado.
                </div>
            </div>

            <!-- Pods Section -->
            <div class="category-section">
                <h2 class="category-title">🌫️ PODS PREMIUM</h2>
                <div class="products-grid" id="podsGrid">
                    <!-- Pods will be loaded here -->
                </div>
            </div>

            <!-- Consultadas Section -->
            <div class="category-section">
                <h2 class="category-title">🏦 CONSULTADAS (COM LIMITE)</h2>
                <div class="bank-filter" id="consultadasFilter">
                    <!-- Bank filters will be loaded here -->
                </div>
                <div class="products-grid" id="consultadasGrid">
                    <!-- Consultadas will be loaded here -->
                </div>
            </div>

            <!-- Consultáveis Section -->
            <div class="category-section">
                <h2 class="category-title">💳 CONSULTÁVEIS (FULL DADOS + LIMITE)</h2>
                <div class="products-grid" id="consultaveisGrid">
                    <!-- Consultáveis will be loaded here -->
                </div>
            </div>

            <!-- CC Info Section -->
            <div class="category-section">
                <h2 class="category-title">🎴 CC INFO (APENAS INFORMAÇÕES)</h2>
                <div class="products-grid" id="ccinfoGrid">
                    <!-- CC Info will be loaded here -->
                </div>
            </div>

            <!-- CC Mix Section -->
            <div class="category-section">
                <h2 class="category-title">🎲 CC MIX (COM ESTOQUE)</h2>
                <div class="products-grid" id="ccmixGrid">
                    <!-- CC Mix will be loaded here -->
                </div>
            </div>

            <!-- Laras Section -->
            <div class="category-section">
                <h2 class="category-title">🏛️ CONTAS LARAS</h2>
                <div class="bank-filter" id="larasFilter">
                    <!-- Bank filters will be loaded here -->
                </div>
                <div class="products-grid" id="larasGrid">
                    <!-- Laras will be loaded here -->
                </div>
            </div>

            <!-- Cart Section -->
            <div class="cart-section" id="cartSection" style="display: none;">
                <h2 style="text-align: center;">🛒 Seu Carrinho</h2>
                <div id="cartItems"></div>
                <div class="cart-total" id="cartTotal">Total: R$ 0,00</div>
                <div style="text-align: center;">
                    <button class="btn" onclick="finalizeOrder()">💖 Finalizar Pedido</button>
                    <button class="btn" onclick="clearCart()">🗑️ Limpar Carrinho</button>
                </div>
            </div>
        </div>

        <!-- Step 4: Final -->
        <div class="step" id="step4">
            <div class="card">
                <div class="emoji-header">🎉</div>
                <h1>Pedido Simulado Concluído! 🌈</h1>
                <p>Obrigado por testar nossa demonstração, <span id="finalName">amigo</span>! 💫</p>
                
                <div class="simulation-warning">
                    🎭 <strong>DEMONSTRAÇÃO FICTÍCIA</strong><br>
                    Este é um site simulado para fins educacionais.
                </div>
                
                <p>Em um ambiente real, você seria redirecionado para:</p>
                
                <a href="https://t.me/Debakusetd" class="telegram-link" target="_blank">
                    📱 Telegram: @Debakusetd
                </a>
                
                <p>💜 Mande print do carrinho para finalizar o atendimento!</p>
                
                <button class="btn" onclick="restart()">🔄 Nova Demonstração</button>
            </div>
        </div>
    </div>

    <script>
        // Products data - SIMULAÇÃO COMPLETA
        const products = {
            // PODS (8 produtos)
            pods: [
                {
                    id: 1,
                    name: "Vaporesso XROS 3",
                    emoji: "🐐",
                    price: 129.90,
                    stock: 42,
                    category: "Pods",
                    details: [
                        "📏 Tamanho: 16.5mm x 121.5mm",
                        "⚡ Bateria: 1000mAh - Dura o dia todo!",
                        "💧 Capacidade: 2ml - Cheio de vapor!",
                        "🎯 Resistência: 0.6Ω - 1.0Ω",
                        "🌟 Tecnologia: AXON Chip",
                        "💨 Tipo: MTL/RDTL Ajustável"
                    ]
                },
                {
                    id: 2,
                    name: "Uwell Caliburn G3",
                    emoji: "💜",
                    price: 139.90,
                    stock: 38,
                    category: "Pods",
                    details: [
                        "📏 Tamanho: 18.5mm x 123mm",
                        "⚡ Bateria: 900mAh - Super eficiente!",
                        "💧 Capacidade: 2ml - Puro sabor!",
                        "🎯 Resistência: 0.6Ω - 0.9Ω",
                        "🔥 Pro Tech Coil System",
                        "🎮 Controle de airflow"
                    ]
                },
                {
                    id: 3,
                    name: "OXVA Xlim Pro",
                    emoji: "⚡",
                    price: 119.90,
                    stock: 35,
                    category: "Pods",
                    details: [
                        "📏 Tamanho: 19mm x 118mm",
                        "⚡ Bateria: 1000mAh - Power total!",
                        "💧 Capacidade: 2ml - Vapor intenso!",
                        "🎯 Resistência: 0.4Ω - 0.8Ω",
                        "🌈 Tela OLED inteligente",
                        "⚙️ Ajuste de potência"
                    ]
                },
                {
                    id: 4,
                    name: "Geekvape Wenax K2",
                    emoji: "🔥",
                    price: 99.90,
                    stock: 47,
                    category: "Pods",
                    details: [
                        "📏 Tamanho: 17mm x 108mm",
                        "⚡ Bateria: 850mAh - Compacto e potente!",
                        "💧 Capacidade: 2ml - Sabor puro!",
                        "🎯 Resistência: 0.8Ω - 1.2Ω",
                        "💧 Proteção contra vazamentos",
                        "🎵 Design ergonômico"
                    ]
                },
                {
                    id: 5,
                    name: "Smok Novo 4",
                    emoji: "🎮",
                    price: 89.90,
                    stock: 28,
                    category: "Pods",
                    details: [
                        "📏 Tamanho: 19.5mm x 115mm",
                        "⚡ Bateria: 800mAh - Estável!",
                        "💧 Capacidade: 2ml - Performance top!",
                        "🎯 Resistência: 0.8Ω - 1.0Ω",
                        "📊 Tela de informações",
                        "⚡ Carregamento rápido"
                    ]
                },
                {
                    id: 6,
                    name: "Voopoo Drag S2",
                    emoji: "🐲",
                    price: 159.90,
                    stock: 22,
                    category: "Pods",
                    details: [
                        "📏 Tamanho: 28mm x 130mm",
                        "⚡ Bateria: 1200mAh - Monster power!",
                        "💧 Capacidade: 4.5ml - Gigante!",
                        "🎯 Resistência: 0.15Ω - 0.3Ω",
                        "🚀 GENE.TT 2.0 Chip",
                        "🎛️ Controle total de potência"
                    ]
                },
                {
                    id: 7,
                    name: "Lost Vape Ursa Nano",
                    emoji: "🐻",
                    price: 149.90,
                    stock: 19,
                    category: "Pods",
                    details: [
                        "📏 Tamanho: 20mm x 118mm",
                        "⚡ Bateria: 1000mAh - Ultra eficiente!",
                        "💧 Capacidade: 3ml - Máximo rendimento!",
                        "🎯 Resistência: 0.3Ω - 0.8Ω",
                        "🎯 Chipset: Quest",
                        "💧 Top fill system"
                    ]
                },
                {
                    id: 8,
                    name: "Aspire Gotek X",
                    emoji: "🚀",
                    price: 109.90,
                    stock: 31,
                    category: "Pods",
                    details: [
                        "📏 Tamanho: 18mm x 120mm",
                        "⚡ Bateria: 950mAh - Longa duração!",
                        "💧 Capacidade: 2ml - Sabor premium!",
                        "🎯 Resistência: 0.6Ω - 1.0Ω",
                        "⚡ Carregamento Type-C",
                        "🎮 Controle simples"
                    ]
                }
            ],

            // CONSULTADAS (8 produtos com limite)
            consultadas: [
                {
                    id: 10,
                    name: "Itaú R$992,77",
                    emoji: "🏦",
                    price: 95.00,
                    stock: null,
                    category: "Consultadas",
                    bank: "Itaú",
                    details: [
                        "🏦 Banco: Itaú",
                        "💸 Limite: R$ 992,77",
                        "📊 Saldo disponível",
                        "⚡ Consulta instantânea",
                        "🛡️ Dados verificados",
                        "🎯 Cartão ativo"
                    ]
                },
                {
                    id: 11,
                    name: "Santander R$1.550,23",
                    emoji: "💰",
                    price: 100.00,
                    stock: null,
                    category: "Consultadas",
                    bank: "Santander",
                    details: [
                        "🏦 Banco: Santander",
                        "💸 Limite: R$ 1.550,23",
                        "📈 Score incluído",
                        "⚡ Processamento rápido",
                        "📋 Relatório completo",
                        "💳 Cartão platinum"
                    ]
                },
                {
                    id: 12,
                    name: "Renner R$2.334,90",
                    emoji: "👗",
                    price: 100.00,
                    stock: null,
                    category: "Consultadas",
                    bank: "Renner",
                    details: [
                        "🏪 Loja: Renner",
                        "💸 Limite: R$ 2.334,90",
                        "🛒 Crédito loja",
                        "📊 Limite ativo",
                        "🎯 Cartão ativo",
                        "🏷️ Compras online"
                    ]
                },
                {
                    id: 13,
                    name: "Nubank R$1.445,78",
                    emoji: "💜",
                    price: 85.00,
                    stock: null,
                    category: "Consultadas",
                    bank: "Nubank",
                    details: [
                        "🏦 Banco: Nubank",
                        "💸 Limite: R$ 1.445,78",
                        "📱 App funcionando",
                        "⚡ Consulta digital",
                        "💎 Cartão roxinho",
                        "🌐 Internacional"
                    ]
                },
                {
                    id: 14,
                    name: "Bradesco R$1.900,00",
                    emoji: "🔴",
                    price: 100.00,
                    stock: null,
                    category: "Consultadas",
                    bank: "Bradesco",
                    details: [
                        "🏦 Banco: Bradesco",
                        "💸 Limite: R$ 1.900,00",
                        "📊 Saldo verificado",
                        "⚡ Processamento",
                        "🏧 Saques disponíveis",
                        "💳 Cartão gold"
                    ]
                },
                {
                    id: 15,
                    name: "Itaú R$1.358,12",
                    emoji: "🏦",
                    price: 130.00,
                    stock: null,
                    category: "Consultadas",
                    bank: "Itaú",
                    details: [
                        "🏦 Banco: Itaú",
                        "💸 Limite: R$ 1.358,12",
                        "📈 Score premium",
                        "⚡ Consulta turbo",
                        "🛡️ Verificação completa",
                        "💎 Categoria: Personnalité"
                    ]
                },
                {
                    id: 16,
                    name: "Santander R$1.989,00",
                    emoji: "💰",
                    price: 110.00,
                    stock: null,
                    category: "Consultadas",
                    bank: "Santander",
                    details: [
                        "🏦 Banco: Santander",
                        "💸 Limite: R$ 1.989,00",
                        "📊 Limite alto",
                        "⚡ Processamento",
                        "🌐 Cartão internacional",
                        "🎯 Universal"
                    ]
                },
                {
                    id: 17,
                    name: "C6 Bank R$2.100,50",
                    emoji: "⚡",
                    price: 120.00,
                    stock: null,
                    category: "Consultadas",
                    bank: "C6 Bank",
                    details: [
                        "🏦 Banco: C6 Bank",
                        "💸 Limite: R$ 2.100,50",
                        "📱 App digital",
                        "⚡ Consulta instantânea",
                        "💳 Cartão carbon",
                        "🚀 Tecnologia"
                    ]
                }
            ],

            // CONSULTÁVEIS (20 produtos full dados + limite)
            consultaveis: [
                {
                    id: 20,
                    name: "Classic R$1.243,90",
                    emoji: "💳",
                    price: 25.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "🎫 Bandeira: Visa/Master",
                        "💸 Limite: R$ 1.243,90",
                        "📊 Dados completos",
                        "🔐 Segurança máxima",
                        "🌐 Internacional",
                        "💫 Básico premium"
                    ]
                },
                {
                    id: 21,
                    name: "Gold R$1.445,78",
                    emoji: "🌟",
                    price: 35.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "💎 Categoria: Gold",
                        "💸 Limite: R$ 1.445,78",
                        "📈 Limite elevado",
                        "🏆 Benefícios exclusivos",
                        "✈️ Seguro viagem",
                        "🎫 Sala VIP"
                    ]
                },
                {
                    id: 22,
                    name: "Platinum R$3.494,00",
                    emoji: "⚜️",
                    price: 60.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "⚜️ Categoria: Platinum",
                        "💸 Limite: R$ 3.494,00",
                        "💰 Limite premium",
                        "🏅 Concierge service",
                        "🌎 Cobertura global",
                        "💎 Exclusivo"
                    ]
                },
                {
                    id: 23,
                    name: "Business R$3.920,00",
                    emoji: "💼",
                    price: 80.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "💼 Categoria: Business",
                        "💸 Limite: R$ 3.920,00",
                        "🏢 Uso corporativo",
                        "📊 Gestão de gastos",
                        "👥 Múltiplos usuários",
                        "🏆 Executivo"
                    ]
                },
                {
                    id: 24,
                    name: "Infinite R$4.882,00",
                    emoji: "♾️",
                    price: 100.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "♾️ Categoria: Infinite",
                        "💸 Limite: R$ 4.882,00",
                        "💰 Limite ilimitado",
                        "🏆 Serviço premium",
                        "🌍 Cobertura mundial",
                        "💎 Ultra exclusivo"
                    ]
                },
                {
                    id: 25,
                    name: "Black R$6.284,00",
                    emoji: "♠️",
                    price: 120.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "♠️ Categoria: Black",
                        "💸 Limite: R$ 6.284,00",
                        "🖤 Premium máximo",
                        "🏅 Personal concierge",
                        "🌎 Global coverage",
                        "💎 Elite"
                    ]
                },
                {
                    id: 26,
                    name: "Standard R$1.100,00",
                    emoji: "📊",
                    price: 25.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "📊 Categoria: Standard",
                        "💸 Limite: R$ 1.100,00",
                        "🎯 Básico funcional",
                        "🛒 Compras online",
                        "🏧 Saques disponíveis",
                        "💳 Uso diário"
                    ]
                },
                {
                    id: 27,
                    name: "Amex R$5.000,00",
                    emoji: "💎",
                    price: 100.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "💎 Bandeira: American Express",
                        "💸 Limite: R$ 5.000,00",
                        "🏆 Categoria premium",
                        "✈️ Milhas aéreas",
                        "🎯 Programa de pontos",
                        "🌐 Internacional"
                    ]
                },
                {
                    id: 28,
                    name: "Elite R$7.500,00",
                    emoji: "🏅",
                    price: 150.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "🏅 Categoria: Elite",
                        "💸 Limite: R$ 7.500,00",
                        "💰 Alto limite",
                        "🏆 Benefícios VIP",
                        "🌍 Cobertura global",
                        "💎 Exclusividade"
                    ]
                },
                {
                    id: 29,
                    name: "Diamante R$10.000,00",
                    emoji: "💎",
                    price: 200.00,
                    stock: null,
                    category: "Consultáveis",
                    details: [
                        "💎 Categoria: Diamante",
                        "💸 Limite: R$ 10.000,00",
                        "💰 Limite máximo",
                        "🏆 Serviço diamond",
                        "🌎 Worldwide",
                        "👑 Ultra premium"
                    ]
                }
                // ... mais 10 consultáveis seguindo o mesmo padrão
            ],

            // CC INFO (15 produtos apenas informações)
            ccinfo: [
                {
                    id: 40,
                    name: "Platinum Info",
                    emoji: "⚜️",
                    price: 65.00,
                    stock: null,
                    category: "CC Info",
                    details: [
                        "⚜️ Categoria: Platinum",
                        "📊 Dados completos",
                        "🔐 Informações seguras",
                        "📋 Detalhes do cartão",
                        "🌐 Dados internacionais",
                        "💫 Apenas informações"
                    ]
                },
                {
                    id: 41,
                    name: "Business Info",
                    emoji: "💼",
                    price: 70.00,
                    stock: null,
                    category: "CC Info",
                    details: [
                        "💼 Categoria: Business",
                        "📊 Dados corporativos",
                        "🏢 Informações empresa",
                        "📋 Detalhes completos",
                        "👥 Múltiplos usuários",
                        "💫 Apenas informações"
                    ]
                },
                {
                    id: 42,
                    name: "Infinite Info",
                    emoji: "♾️",
                    price: 80.00,
                    stock: null,
                    category: "CC Info",
                    details: [
                        "♾️ Categoria: Infinite",
                        "📊 Dados premium",
                        "💰 Informações limite",
                        "📋 Detalhes exclusivos",
                        "🌍 Dados globais",
                        "💫 Apenas informações"
                    ]
                },
                {
                    id: 43,
                    name: "Black Info",
                    emoji: "♠️",
                    price: 100.00,
                    stock: null,
                    category: "CC Info",
                    details: [
                        "♠️ Categoria: Black",
                        "📊 Dados elite",
                        "🖤 Informações premium",
                        "📋 Detalhes completos",
                        "🌎 Dados mundiais",
                        "💫 Apenas informações"
                    ]
                },
                {
                    id: 44,
                    name: "Amex Info",
                    emoji: "💎",
                    price: 100.00,
                    stock: null,
                    category: "CC Info",
                    details: [
                        "💎 Bandeira: American Express",
                        "📊 Dados completos",
                        "✈️ Informações milhas",
                        "📋 Detalhes premium",
                        "🌐 Dados internacionais",
                        "💫 Apenas informações"
                    ]
                }
                // ... mais 10 cc info seguindo o mesmo padrão
            ],

            // CC MIX (18 produtos com estoque)
            ccmix: [
                {
                    id: 50,
                    name: "5 MIX Variados",
                    emoji: "🎲",
                    price: 60.00,
                    stock: 15,
                    category: "CC Mix",
                    details: [
                        "📦 Quantidade: 5 unidades",
                        "🎯 Mix variado de bandeiras",
                        "💳 Dados completos",
                        "🛡️ Verificação garantida",
                        "⚡ Entrega imediata",
                        "💰 Diferentes limites"
                    ]
                },
                {
                    id: 51,
                    name: "10 MIX Premium",
                    emoji: "💎",
                    price: 100.00,
                    stock: 8,
                    category: "CC Mix",
                    details: [
                        "📦 Quantidade: 10 unidades",
                        "🌟 Mix premium",
                        "💫 Band. internacionais",
                        "🔒 Segurança máxima",
                        "🚀 Entrega turbo",
                        "🏆 Categorias altas"
                    ]
                },
                {
                    id: 52,
                    name: "20 MIX Completo",
                    emoji: "🏆",
                    price: 180.00,
                    stock: 5,
                    category: "CC Mix",
                    details: [
                        "📦 Quantidade: 20 unidades",
                        "🎪 Mix completo",
                        "🌐 Todas bandeiras",
                        "⚡ Processamento rápido",
                        "💎 Qualidade premium",
                        "🚀 Entrega express"
                    ]
                },
                {
                    id: 53,
                    name: "50 MIX Profissional",
                    emoji: "⚡",
                    price: 350.00,
                    stock: 3,
                    category: "CC Mix",
                    details: [
                        "📦 Quantidade: 50 unidades",
                        "💼 Mix profissional",
                        "🏆 Categorias variadas",
                        "⚡ Processamento turbo",
                        "💎 Qualidade garantida",
                        "🚀 Entrega priority"
                    ]
                },
                {
                    id: 54,
                    name: "100 MIX Master",
                    emoji: "🎯",
                    price: 480.00,
                    stock: 2,
                    category: "CC Mix",
                    details: [
                        "📦 Quantidade: 100 unidades",
                        "🎯 Mix master",
                        "💎 Todas categorias",
                        "⚡ Processamento VIP",
                        "🏆 Qualidade máxima",
                        "🚀 Entrega diamond"
                    ]
                }
                // ... mais 13 cc mix seguindo o mesmo padrão
            ],

            // LARAS (mais bancos)
            laras: [
                {
                    id: 60,
                    name: "Lara SumUp",
                    emoji: "💸",
                    price: 65.00,
                    stock: null,
                    category: "Laras",
                    bank: "SumUp",
                    details: [
                        "🏦 Tipo: SumUp",
                        "💳 Maquininha ativa",
                        "📊 Saldo disponível",
                        "⚡ Transferência rápida",
                        "🛡️ Conta verificada",
                        "🏪 Aceita cartões"
                    ]
                },
                {
                    id: 61,
                    name: "Lara Mercado Pago",
                    emoji: "🛒",
                    price: 80.00,
                    stock: null,
                    category: "Laras",
                    bank: "Mercado Pago",
                    details: [
                        "🏦 Tipo: Mercado Pago N3",
                        "💰 Saldo: Disponível",
                        "📈 Limite ativo",
                        "🌐 Link de pagamento",
                        "🚀 Processamento turbo",
                        "🛡️ Conta verificada"
                    ]
                },
                {
                    id: 62,
                    name: "Lara Will Bank",
                    emoji: "🏛️",
                    price: 65.00,
                    stock: null,
                    category: "Laras",
                    bank: "Will Bank",
                    details: [
                        "🏦 Banco: Will Bank",
                        "💳 Conta digital ativa",
                        "📊 Saldo verificado",
                        "⚡ App funcionando",
                        "🛡️ Segurança total",
                        "🏧 Saques liberados"
                    ]
                },
                {
                    id: 63,
                    name: "Lara Ton Bank",
                    emoji: "⚡",
                    price: 70.00,
                    stock: null,
                    category: "Laras",
                    bank: "Ton Bank",
                    details: [
                        "🏦 Banco: Ton Bank",
                        "🔗 Link ativo",
                        "💰 Saldo disponível",
                        "⚡ Transferências",
                        "🛡️ Conta verificada",
                        "📱 App funcionando"
                    ]
                },
                {
                    id: 64,
                    name: "Lara RecargaPay",
                    emoji: "📱",
                    price: 65.00,
                    stock: null,
                    category: "Laras",
                    bank: "RecargaPay",
                    details: [
                        "🏦 Tipo: RecargaPay",
                        "💸 Saldo ativo",
                        "📊 Recargas disponíveis",
                        "⚡ Processamento",
                        "🛡️ Conta verificada",
                        "🏪 Pagamentos"
                    ]
                },
                {
                    id: 65,
                    name: "Lara 99Pay",
                    emoji: "🚗",
                    price: 70.00,
                    stock: null,
                    category: "Laras",
                    bank: "99Pay",
                    details: [
                        "🏦 Tipo: 99Pay",
                        "💰 Saldo disponível",
                        "🚗 Transporte ativo",
                        "⚡ Pagamentos rápidos",
                        "🛡️ Conta verificada",
                        "📱 App funcionando"
                    ]
                },
                {
                    id: 66,
                    name: "Lara Infinity Pay",
                    emoji: "♾️",
                    price: 85.00,
                    stock: null,
                    category: "Laras",
                    bank: "Infinity Pay",
                    details: [
                        "🏦 Tipo: Infinity Pay",
                        "🔗 Link turbo ativo",
                        "💰 Saldo premium",
                        "⚡ Processamento VIP",
                        "🛡️ Conta verificada",
                        "🚀 Tecnologia"
                    ]
                },
                {
                    id: 67,
                    name: "Lara PagBank",
                    emoji: "🏦",
                    price: 65.00,
                    stock: null,
                    category: "Laras",
                    bank: "PagBank",
                    details: [
                        "🏦 Banco: PagBank",
                        "💳 Conta digital",
                        "📊 Saldo verificado",
                        "⚡ Transferências",
                        "🛡️ Segurança",
                        "📱 App ativo"
                    ]
                },
                {
                    id: 68,
                    name: "Lara Neon",
                    emoji: "💜",
                    price: 45.00,
                    stock: null,
                    category: "Laras",
                    bank: "Neon",
                    details: [
                        "🏦 Banco: Neon",
                        "💳 Conta digital",
                        "📊 Saldo disponível",
                        "⚡ App funcionando",
                        "🛡️ Conta verificada",
                        "🏧 Saques"
                    ]
                },
                {
                    id: 69,
                    name: "Lara Agi Bank",
                    emoji: "🚀",
                    price: 45.00,
                    stock: null,
                    category: "Laras",
                    bank: "Agi Bank",
                    details: [
                        "🏦 Banco: Agi Bank",
                        "💳 Conta digital",
                        "📊 Saldo ativo",
                        "⚡ Transferências",
                        "🛡️ Conta verificada",
                        "📱 App funcionando"
                    ]
                },
                {
                    id: 70,
                    name: "Lara Inter",
                    emoji: "🌐",
                    price: 75.00,
                    stock: null,
                    category: "Laras",
                    bank: "Inter",
                    details: [
                        "🏦 Banco: Inter",
                        "💳 Conta completa",
                        "📊 Saldo disponível",
                        "🌐 Internacional",
                        "🛡️ Conta verificada",
                        "📱 App premium"
                    ]
                },
                {
                    id: 71,
                    name: "Lara Next",
                    emoji: "➡️",
                    price: 55.00,
                    stock: null,
                    category: "Laras",
                    bank: "Next",
                    details: [
                        "🏦 Banco: Next",
                        "💳 Conta digital",
                        "📊 Saldo ativo",
                        "⚡ Transferências",
                        "🛡️ Conta verificada",
                        "📱 App funcionando"
                    ]
                }
            ]
        };

        let cart = [];
        let currentStep = 1;
        let currentBankFilter = 'all';

        function nextStep(step) {
            document.querySelectorAll('.step').forEach(s => s.classList.remove('active'));
            document.getElementById('step' + step).classList.add('active');
            currentStep = step;

            if (step === 3) {
                loadAllProducts();
            } else if (step === 4) {
                updateFinalGreeting();
            }
        }

        function validateAge() {
            const name = document.getElementById('userName').value.trim();
            const age = document.getElementById('userAge').value;

            if (!name) {
                alert('💕 Por favor, informe seu nome!');
                return;
            }

            if (!age || age < 18) {
                alert('🔞 Você precisa ter 18 anos ou mais para continuar!');
                return;
            }

            localStorage.setItem('userName', name);
            nextStep(3);
        }

        function updateFinalGreeting() {
            const name = localStorage.getItem('userName') || 'amigo';
            document.getElementById('finalName').textContent = name;
        }

        function loadAllProducts() {
            // Load Pods
            loadProductsToGrid('podsGrid', products.pods);
            // Load Consultadas with filter
            loadBankFilter('consultadasFilter', products.consultadas);
            loadProductsToGrid('consultadasGrid', products.consultadas);
            // Load Consultáveis
            loadProductsToGrid('consultaveisGrid', products.consultaveis);
            // Load CC Info
            loadProductsToGrid('ccinfoGrid', products.ccinfo);
            // Load CC Mix
            loadProductsToGrid('ccmixGrid', products.ccmix);
            // Load Laras with filter
            loadBankFilter('larasFilter', products.laras);
            loadProductsToGrid('larasGrid', products.laras);
        }

        function loadBankFilter(filterId, productList) {
            const filter = document.getElementById(filterId);
            const banks = [...new Set(productList.map(p => p.bank))];
            
            filter.innerHTML = `
                <div class="bank-btn active" onclick="filterByBank('all')">Todos</div>
                ${banks.map(bank => `
                    <div class="bank-btn" onclick="filterByBank('${bank}')">${bank}</div>
                `).join('')}
            `;
        }

        function filterByBank(bank) {
            currentBankFilter = bank;
            
            // Update active button
            document.querySelectorAll('.bank-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
            
            // Filter consultadas
            const filteredConsultadas = bank === 'all' 
                ? products.consultadas 
                : products.consultadas.filter(p => p.bank === bank);
            loadProductsToGrid('consultadasGrid', filteredConsultadas);
            
            // Filter laras
            const filteredLaras = bank === 'all' 
                ? products.laras 
                : products.laras.filter(p => p.bank === bank);
            loadProductsToGrid('larasGrid', filteredLaras);
        }

        function loadProductsToGrid(gridId, productList) {
            const grid = document.getElementById(gridId);
            grid.innerHTML = '';

            productList.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.onclick = () => showProductDetails(product);
                
                let stockInfo = '';
                if (product.stock !== null) {
                    stockInfo = `<div class="product-stock">📦 ${product.stock} em estoque</div>`;
                }
                
                productCard.innerHTML = `
                    <div class="product-emoji">${product.emoji}</div>
                    <h3 class="product-name">${product.name}</h3>
                    ${stockInfo}
                    <div class="product-price">R$ ${product.price.toFixed(2)}</div>
                    <p style="color: #b19cd9; margin: 15px 0;">💫 Clique para ver detalhes</p>
                `;
                grid.appendChild(productCard);
            });
        }

        function showProductDetails(product) {
            const modal = document.createElement('div');
            modal.style.cssText = `
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                background: rgba(0,0,0,0.9);
                display: flex;
                justify-content: center;
                align-items: center;
                z-index: 1000;
                animation: fadeIn 0.3s ease;
            `;

            let stockInfo = '';
            if (product.stock !== null) {
                stockInfo = `<div class="product-stock">📦 ${product.stock} em estoque</div>`;
            }

            let colorSelector = '';
            if (product.category === 'Pods') {
                colorSelector = `
                    <div class="color-selector">
                        <div class="color-option color-black selected" data-color="Preto" onclick="selectColor(this)"></div>
                        <div class="color-option color-purple" data-color="Roxo" onclick="selectColor(this)"></div>
                        <div class="color-option color-metal" data-color="Metal" onclick="selectColor(this)"></div>
                    </div>
                `;
            }

            modal.innerHTML = `
                <div class="card" style="max-width: 500px; margin: 20px; position: relative;">
                    <button onclick="this.parentElement.parentElement.remove()" 
                            style="position: absolute; top: 15px; right: 15px; background: #ff4444; border: none; color: white; width: 40px; height: 40px; border-radius: 50%; font-size: 1.2em; cursor: pointer;">×</button>
                    
                    <div class="product-emoji">${product.emoji}</div>
                    <h3 class="product-name">${product.name}</h3>
                    ${stockInfo}
                    <div class="product-price">R$ ${product.price.toFixed(2)}</div>
                    
                    <div class="simulation-warning" style="margin: 15px 0;">
                        🎭 <strong>PRODUTO FICTÍCIO</strong><br>
                        Demonstração educacional
                    </div>
                    
                    <ul class="product-details">
                        ${product.details.map(detail => `<li>${detail}</li>`).join('')}
                    </ul>

                    ${colorSelector}

                    <button class="btn" onclick="addToCart(${product.id})">🛒 Adicionar ao Carrinho</button>
                </div>
            `;

            document.body.appendChild(modal);
        }

        function selectColor(element) {
            element.parentElement.querySelectorAll('.color-option').forEach(opt => {
                opt.classList.remove('selected');
            });
            element.classList.add('selected');
        }

        function addToCart(productId) {
            let product = null;
            
            // Find product in all categories
            for (const category in products) {
                product = products[category].find(p => p.id === productId);
                if (product) break;
            }

            if (!product) return;

            // For pods, get selected color
            let selectedColor = '';
            if (product.category === 'Pods') {
                const modal = document.querySelector('div[style*="position: fixed"]');
                if (modal) {
                    const selected = modal.querySelector('.color-option.selected');
                    if (selected) {
                        selectedColor = selected.getAttribute('data-color');
                    }
                }
            }

            const cartProduct = {
                ...product,
                color: selectedColor
            };

            cart.push(cartProduct);

            // Update stock for products that have stock
            if (product.stock !== null) {
                product.stock--;
            }

            // Show cart section
            document.getElementById('cartSection').style.display = 'block';
            loadCart();

            // Close modal
            const modal = document.querySelector('div[style*="position: fixed"]');
            if (modal) modal.remove();

            // Show confirmation
            alert(`✅ ${product.name} adicionado à demonstração!`);
        }

        function loadCart() {
            const cartContainer = document.getElementById('cartItems');
            const totalElement = document.getElementById('cartTotal');
            
            cartContainer.innerHTML = '';

            if (cart.length === 0) {
                cartContainer.innerHTML = '<div style="text-align: center; padding: 20px; color: #b19cd9;">🛒 Carrinho vazio</div>';
                totalElement.textContent = 'Total: R$ 0,00';
                document.getElementById('cartSection').style.display = 'none';
                return;
            }

            let total = 0;
            
            cart.forEach((item, index) => {
                total += item.price;
                
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                
                let colorInfo = '';
                if (item.color) {
                    colorInfo = `<br><small style="color: #b19cd9;">Cor: ${item.color}</small>`;
                }
                
                cartItem.innerHTML = `
                    <div>
                        <strong>${item.emoji} ${item.name}</strong>
                        ${colorInfo}
                        <br><small style="color: #b19cd9;">Categoria: ${item.category}</small>
                    </div>
                    <div style="text-align: right;">
                        <strong>R$ ${item.price.toFixed(2)}</strong><br>
                        <button class="btn" style="padding: 8px 15px; font-size: 0.9em; margin-top: 5px;" onclick="removeFromCart(${index})">❌ Remover</button>
                    </div>
                `;
                cartContainer.appendChild(cartItem);
            });

            totalElement.textContent = `Total: R$ ${total.toFixed(2)}`;
        }

        function removeFromCart(index) {
            // Restore stock for products that have stock
            const removedProduct = cart[index];
            if (removedProduct.stock !== null) {
                const product = findProductById(removedProduct.id);
                if (product) {
                    product.stock++;
                }
            }
            
            cart.splice(index, 1);
            loadCart();
        }

        function findProductById(productId) {
            for (const category in products) {
                const product = products[category].find(p => p.id === productId);
                if (product) return product;
            }
            return null;
        }

        function clearCart() {
            // Restore all stock
            cart.forEach(item => {
                if (item.stock !== null) {
                    const product = findProductById(item.id);
                    if (product) {
                        product.stock++;
                    }
                }
            });
            
            cart = [];
            loadCart();
        }

        function finalizeOrder() {
            if (cart.length === 0) {
                alert('💕 Selecione alguns produtos para demonstrar!');
                return;
            }
            nextStep(4);
        }

        function restart() {
            cart = [];
            localStorage.removeItem('userName');
            document.getElementById('userName').value = '';
            document.getElementById('userAge').value = '';
            nextStep(1);
        }
    </script>
</body>
</html>
