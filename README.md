# WINDO-SCRIPTS
Loja onde tem Scripts pagos e grátis, completos e apenas uma base pra você completar, barato e fácil, com R$1,00 você pode comprar um script bom
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>W1ndo Scripts - Marketplace de Scripts Premium</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0a0f;
            color: #fff;
            min-height: 100vh;
        }

        /* Navegação */
        nav {
            background: #12121a;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #333;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #00d4ff;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: #aaa;
            text-decoration: none;
            cursor: pointer;
            transition: color 0.3s ease;
            font-weight: 500;
        }

        .nav-links a:hover, .nav-links a.active {
            color: #00d4ff;
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* Seções */
        .section {
            display: none;
            animation: fadeIn 0.3s ease;
        }

        .section.active {
            display: block;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        /* Produtos */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .product-card {
            background: #12121a;
            border-radius: 15px;
            overflow: hidden;
            border: 1px solid #333;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
            border-color: #00d4ff;
        }

        .product-video-container {
            width: 100%;
            height: 250px;
            background: #1a1a25;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #666;
            position: relative;
            overflow: hidden;
        }

        .product-video-container video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .product-video-placeholder {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #1a1a25 0%, #0a0a0f 100%);
            font-size: 3rem;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-title {
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
            color: #00d4ff;
            font-weight: bold;
        }

        .product-desc {
            color: #aaa;
            margin-bottom: 1rem;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        .product-desc-highlight {
            background: #1a1a25;
            padding: 0.8rem;
            border-left: 3px solid #00d4ff;
            border-radius: 5px;
            margin: 1rem 0;
            font-size: 0.9rem;
            color: #10b981;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 1.5rem;
            padding-top: 1rem;
            border-top: 1px solid #333;
        }

        .price {
            color: #10b981;
            font-size: 2rem;
            font-weight: bold;
        }

        .price-label {
            color: #666;
            font-size: 0.8rem;
            margin-bottom: 0.3rem;
        }

        button {
            background: #00d4ff;
            color: #000;
            border: none;
            padding: 0.8rem 1.8rem;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            transition: background 0.3s ease;
            font-size: 0.95rem;
        }

        button:hover {
            background: #00a8cc;
        }

        button.btn-secondary {
            background: #333;
            color: #fff;
            margin-left: 0.5rem;
        }

        button.btn-secondary:hover {
            background: #444;
        }

        button.btn-copy {
            background: #10b981;
            color: #fff;
            padding: 0.6rem 1.2rem;
            font-size: 0.9rem;
            margin-left: 0.5rem;
        }

        button.btn-copy:hover {
            background: #059669;
        }

        button.btn-copy.copied {
            background: #06b6d4;
        }

        /* Comprovante */
        .chat-box {
            background: #12121a;
            border-radius: 15px;
            padding: 2rem;
            max-width: 700px;
            margin: 2rem auto;
            border: 1px solid #333;
        }

        .chat-title {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: #00d4ff;
        }

        .empty-state {
            text-align: center;
            padding: 3rem 2rem;
            color: #666;
        }

        .empty-state h3 {
            color: #aaa;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .empty-state p {
            margin-bottom: 2rem;
            font-size: 1rem;
        }

        .empty-state button {
            background: #00d4ff;
            color: #000;
            padding: 0.8rem 2rem;
        }

        .product-summary {
            background: #1a1a25;
            padding: 1.5rem;
            border-radius: 10px;
            margin-bottom: 2rem;
            border: 1px solid #333;
        }

        .product-summary h4 {
            color: #00d4ff;
            margin-bottom: 1rem;
        }

        .summary-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.8rem;
            font-size: 0.95rem;
        }

        .summary-item strong {
            color: #fff;
        }

        .summary-item .value {
            color: #10b981;
            font-weight: bold;
        }

        #chat-messages {
            max-height: 400px;
            overflow-y: auto;
            margin-bottom: 1.5rem;
            padding: 1rem;
            background: #0a0a0f;
            border-radius: 10px;
        }

        .message {
            background: #1a1a25;
            padding: 1rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            border-left: 3px solid #00d4ff;
            animation: slideIn 0.3s ease;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .input-area {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        input {
            flex: 1;
            padding: 1rem;
            background: #0a0a0f;
            border: 1px solid #333;
            border-radius: 8px;
            color: #fff;
            font-size: 0.95rem;
            transition: border-color 0.3s ease;
        }

        input:focus {
            outline: none;
            border-color: #00d4ff;
        }

        .pix-section {
            background: #1a1a25;
            padding: 1.5rem;
            border-radius: 10px;
            border: 1px solid #333;
        }

        .pix-section h3 {
            color: #00d4ff;
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .pix-info {
            background: #0a0a0f;
            padding: 1rem;
            border-radius: 8px;
            margin-bottom: 1rem;
            font-family: monospace;
            font-size: 0.9rem;
            color: #10b981;
            word-break: break-all;
            border: 1px solid #333;
        }

        .pix-details {
            font-family: 'Segoe UI', sans-serif;
            font-size: 0.95rem;
            color: #aaa;
            margin-bottom: 0.5rem;
        }

        .pix-details strong {
            color: #fff;
        }

        .copy-button-container {
            display: flex;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        /* Admin */
        .admin-panel {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #0a0a0f;
            z-index: 1000;
            overflow-y: auto;
        }

        .admin-panel.active {
            display: block;
        }

        .admin-header {
            background: #12121a;
            padding: 1.5rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #333;
            position: sticky;
            top: 0;
        }

        .order-item {
            background: #12121a;
            padding: 1.5rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            border: 1px solid #333;
        }

        .order-item strong {
            color: #00d4ff;
            font-size: 1.1rem;
        }

        .order-item small {
            color: #666;
            display: block;
            margin: 0.5rem 0;
        }

        .order-item code {
            color: #10b981;
            display: block;
            margin: 0.8rem 0;
            padding: 0.8rem;
            background: #0a0a0f;
            border-radius: 5px;
            word-break: break-all;
        }

        .btn-approve {
            background: #10b981;
            color: #fff;
            margin-right: 0.5rem;
        }

        .btn-approve:hover {
            background: #059669;
        }

        .btn-reject {
            background: #ef4444;
            color: #fff;
        }

        .btn-reject:hover {
            background: #dc2626;
        }

        /* Responsivo */
        @media (max-width: 768px) {
            .product-grid {
                grid-template-columns: 1fr;
            }

            .nav-links {
                gap: 1rem;
                font-size: 0.9rem;
            }

            .product-footer {
                flex-direction: column;
                gap: 1rem;
                align-items: stretch;
            }

            button {
                width: 100%;
            }

            .copy-button-container {
                flex-direction: column;
            }

            .copy-button-container button {
                margin-left: 0 !important;
            }
        }
    </style>
</head>
<body>
    <!-- Navegação -->
    <nav>
        <div class="logo">⚡ W1ndo Scripts</div>
        <div class="nav-links">
            <a href="#" onclick="showSection('home')" id="nav-home" class="active">Início</a>
            <a href="#" onclick="showSection('produtos')" id="nav-produtos">Loja</a>
            <a href="#" onclick="showSection('comprovante')" id="nav-comprovante">Comprovante</a>
        </div>
    </nav>

    <!-- HOME -->
    <div id="home" class="section active">
        <div class="container">
            <h1 style="text-align: center; margin-bottom: 1rem; font-size: 2.5rem;">Scripts Premium para Roblox</h1>
            <p style="text-align: center; color: #aaa; margin-bottom: 3rem; font-size: 1.1rem;">Interfaces profissionais e otimizadas • Modelos prontos para customizar</p>
            
            <div class="product-grid">
                <div class="product-card" onclick="selectProduct({id: 1, name: 'W1nd0ws X v1.5', price: 1.00, description: 'Interface 3D draggable com animações de massinha, sistema de minimizar com puff jump e efeitos de inclinação ao arrastar.'})">
                    <div class="product-video-container">
                        <video controls autoplay muted loop>
                            <source src="product_video.mp4" type="video/mp4">
                            <div class="product-video-placeholder">🎬</div>
                        </video>
                    </div>
                    <div class="product-info">
                        <div class="product-title">W1nd0ws X v1.5</div>
                        <div class="product-desc">Interface 3D draggable com animações de massinha, sistema de minimizar com puff jump e efeitos de inclinação ao arrastar.</div>
                        <div class="product-desc-highlight">
                            <strong>📦 O que você recebe:</strong><br>
                            Não é um script completo, é apenas um pedaço para que você construa o seu próprio. Um modelo e uma carcaça bonita, própria que você pode completar e customizar.
                        </div>
                        <div class="product-footer">
                            <div>
                                <div class="price-label">Preço</div>
                                <div class="price">R$ 1,00</div>
                            </div>
                            <button onclick="selectProduct({id: 1, name: 'W1nd0ws X v1.5', price: 1.00, description: 'Interface 3D draggable com animações de massinha, sistema de minimizar com puff jump e efeitos de inclinação ao arrastar.'}); event.stopPropagation();">Comprar</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- LOJA -->
    <div id="produtos" class="section">
        <div class="container">
            <h2 style="font-size: 2rem; margin-bottom: 2rem;">🛍️ Loja de Scripts</h2>
            <div class="product-grid">
                <div class="product-card" onclick="selectProduct({id: 1, name: 'W1nd0ws X v1.5', price: 1.00, description: 'Interface 3D draggable com animações de massinha, sistema de minimizar com puff jump e efeitos de inclinação ao arrastar.'})">
                    <div class="product-video-container">
                        <video controls autoplay muted loop>
                            <source src="product_video.mp4" type="video/mp4">
                            <div class="product-video-placeholder">🎬</div>
                        </video>
                    </div>
                    <div class="product-info">
                        <div class="product-title">W1nd0ws X v1.5</div>
                        <div class="product-desc">Interface draggable em 3D com animações suaves, sistema de minimizar com puff jump, efeitos de inclinação ao arrastar e muito mais.</div>
                        <div class="product-desc-highlight">
                            <strong>📦 O que você recebe:</strong><br>
                            Não é um script completo, é apenas um pedaço para que você construa o seu próprio. Um modelo e uma carcaça bonita, própria que você pode completar e customizar.
                        </div>
                        <div class="product-footer">
                            <div>
                                <div class="price-label">Preço</div>
                                <div class="price">R$ 1,00</div>
                            </div>
                            <button onclick="selectProduct({id: 1, name: 'W1nd0ws X v1.5', price: 1.00, description: 'Interface 3D draggable com animações de massinha, sistema de minimizar com puff jump e efeitos de inclinação ao arrastar.'}); event.stopPropagation();">Comprar</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- COMPROVANTE -->
    <div id="comprovante" class="section">
        <div class="container">
            <div class="chat-box">
                <div class="chat-title">💳 Comprovante de Compra</div>
                
                <div id="empty-state" class="empty-state">
                    <h3>📦 Nenhum Produto Selecionado</h3>
                    <p>Você ainda não escolheu nenhum script. Visite a loja e selecione um produto para gerar seu comprovante de pagamento.</p>
                    <button onclick="showSection('produtos')">Ir para a Loja</button>
                </div>

                <div id="checkout-content" style="display: none;">
                    <div class="product-summary">
                        <h4>📋 Resumo do Pedido</h4>
                        <div class="summary-item">
                            <strong>Produto:</strong>
                            <span id="summary-product" class="value">-</span>
                        </div>
                        <div class="summary-item">
                            <strong>Preço:</strong>
                            <span id="summary-price" class="value">-</span>
                        </div>
                        <div style="border-top: 1px solid #333; margin-top: 1rem; padding-top: 1rem;">
                            <div class="summary-item">
                                <strong style="font-size: 1.1rem;">Total:</strong>
                                <span id="summary-total" class="value" style="font-size: 1.1rem;">-</span>
                            </div>
                        </div>
                    </div>

                    <div id="chat-messages">
                        <div class="message">
                            <strong>Bot:</strong><br>
                            Olá! Envie seu email e o ID da transação PIX (32 caracteres) para verificação.
                        </div>
                    </div>

                    <div class="input-area">
                        <input type="text" id="user-input" placeholder="Digite aqui...">
                        <button onclick="sendMessage()">Enviar</button>
                    </div>

                    <div class="pix-section">
                        <h3>📱 Chave PIX para Pagamento</h3>
                        
                        <div class="pix-info" id="pix-key">00020126820014BR.GOV.BCB.PIX013697af36ab-22fd-44b3-8717-111eaecf93d80220obrigado por comprar52040000530398654041.005802BR5924Bruno Otavio Ferreira de6009SAO PAULO62140510mXnOVDVNy963048511</div>
                        
                        <div class="copy-button-container">
                            <button class="btn-copy" onclick="copyPixKey()">📋 Copiar Chave PIX</button>
                        </div>

                        <div style="margin-top: 1.5rem; padding-top: 1rem; border-top: 1px solid #333;">
                            <div class="pix-details">
                                <strong>👤 Beneficiário:</strong> Bruno Otavio Ferreira de Lima
                            </div>
                            <div class="pix-details">
                                <strong>💰 Valor:</strong> <span id="pix-value">R$ 1,00</span>
                            </div>
                            <div class="pix-details">
                                <strong>📝 Tipo:</strong> Copia e Cola
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- ADMIN -->
    <div id="admin" class="admin-panel">
        <div class
