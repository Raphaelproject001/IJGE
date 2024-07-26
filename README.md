<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Secretaria Municipal de Desenvolvimento Econômico e Inovação - Juazeiro do Norte</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }
        header {
            background-color: #003366;
            color: #fff;
            padding: 1rem;
            text-align: center;
        }
        nav ul {
            list-style: none;
            padding: 0;
        }
        nav ul li {
            display: inline;
            margin: 0 1rem;
        }
        nav ul li a {
            color: #fff;
            text-decoration: none;
        }
        .container {
            padding: 2rem;
        }
        .section {
            margin-bottom: 2rem;
            padding: 1rem;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        .chat-container {
            border: 1px solid #ddd;
            padding: 1rem;
            background-color: #fafafa;
            margin-top: 1rem;
        }
        .map {
            height: 400px;
            width: 100%;
            margin-top: 1rem;
        }
        footer {
            background-color: #003366;
            color: #fff;
            text-align: center;
            padding: 1rem;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
        .translator {
            margin: 1rem 0;
        }
        .portfolio-item {
            margin-bottom: 1rem;
        }
        .accessibility {
            margin-top: 1rem;
        }
    </style>
</head>
<body>
    <header>
        <h1>Secretaria Municipal de Desenvolvimento Econômico e Inovação - Juazeiro do Norte</h1>
        <nav>
            <ul>
                <li><a href="#announcements">Anúncios</a></li>
                <li><a href="#chat">Chat</a></li>
                <li><a href="#research">Pesquisa</a></li>
                <li><a href="#portfolio">Portfólio</a></li>
                <li><a href="#history">Histórico</a></li>
                <li><a href="#map">Mapa</a></li>
                <li><a href="#accessibility">LIBRAS</a></li>
            </ul>
        </nav>
    </header>
    <div class="container">
        <section id="announcements" class="section">
            <h2>Anúncios</h2>
            <p>Bem-vindo à página de anúncios da Secretaria Municipal de Desenvolvimento Econômico e Inovação.</p>
            <!-- Adicione os anúncios aqui -->
        </section>

        <section id="chat" class="section chat-container">
            <h2>Chat</h2>
            <p>Entre em contato conosco através do chat abaixo:</p>
            <!-- Exemplo de chat simples (requer backend para funcionar completamente) -->
            <div id="chatbox">
                <textarea id="chatInput" rows="4" cols="50" placeholder="Digite sua mensagem..."></textarea><br>
                <button onclick="sendMessage()">Enviar</button>
                <div id="chatOutput"></div>
            </div>
            <script>
                function sendMessage() {
                    var input = document.getElementById('chatInput').value;
                    var output = document.getElementById('chatOutput');
                    output.innerHTML += '<p><strong>Você:</strong> ' + input + '</p>';
                    document.getElementById('chatInput').value = '';
                    // Aqui você deve adicionar a lógica para enviar a mensagem ao backend
                }
            </script>
        </section>

        <section id="research" class="section">
            <h2>Pesquisador</h2>
            <form>
                <input type="text" placeholder="Digite sua pesquisa...">
                <button type="submit">Pesquisar</button>
            </form>
        </section>

        <section id="portfolio" class="section">
            <h2>Portfólio</h2>
            <div class="portfolio-item">
                <h3>Projeto 1</h3>
                <p>Descrição do projeto 1.</p>
            </div>
            <div class="portfolio-item">
                <h3>Projeto 2</h3>
                <p>Descrição do projeto 2.</p>
            </div>
            <!-- Adicione mais itens do portfólio aqui -->
        </section>

        <section id="history" class="section">
            <h2>Histórico</h2>
            <p>Histórico da Secretaria.</p>
            <!-- Adicione informações históricas aqui -->
        </section>

        <section id="map" class="section">
            <h2>Mapa</h2>
            <div id="map" class="map"></div>
            <script>
                function initMap() {
                    var juazeiroDoNorte = { lat: -7.2141, lng: -39.3206 };
                    var map = new google.maps.Map(document.getElementById('map'), {
                        zoom: 12,
                        center: juazeiroDoNorte
                    });
                    var marker = new google.maps.Marker({
                        position: juazeiroDoNorte,
                        map: map
                    });
                }
            </script>
            <script src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap" async defer></script>
        </section>

        <section id="accessibility" class="section">
            <h2>LIBRAS</h2>
            <p>Este é um exemplo básico de suporte para LIBRAS.</p>
            <!-- Adicione aqui vídeos ou recursos em LIBRAS -->
        </section>

        <section class="translator section">
            <h2>Tradutor de Idioma</h2>
            <div id="google_translate_element"></div>
            <script type="text/javascript">
                function googleTranslateElementInit() {
                    new google.translate.TranslateElement({pageLanguage: 'pt'}, 'google_translate_element');
                }
            </script>
            <script type="text/javascript" src="//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>
        </section>
    </div>

    <footer>
        <p>&copy; 2024 Secretaria Municipal de Desenvolvimento Econômico e Inovação - Juazeiro do Norte</p>
    </footer>
</body>
</html>
