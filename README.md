<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>josé carpinteiro</title>
    <style>
        body {
            background-color: #1a1a40;
            color: #ffffff;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        header {
            text-align: center;
            padding: 20px;
            background-color: #333366;
            border-bottom: 3px solid #444488;
        }

        main {
            padding: 20px;
            text-align: center;
        }

        .item {
            margin: 20px;
            padding: 15px;
            background-color: #444488;
            border-radius: 10px;
            display: inline-block;
            cursor: pointer;
        }

        .item:hover {
            background-color: #5555aa;
        }

        .details {
            display: none;
            margin-top: 20px;
            padding: 20px;
            background-color: #333366;
            border-radius: 10px;
        }

        .details.active {
            display: block;
        }

        footer {
            text-align: center;
            padding: 10px;
            background-color: #333366;
            border-top: 3px solid #444488;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>josé carpinteiro</h1>
    </header>
    <main>
        <!-- ITEM DA PÁ COM BOTÃO SOBRE A IMAGEM -->
        <div class="item" onclick="showDetails('pa')">
            <div style="position: relative; display: inline-block;">
                <img src="https://upload.wikimedia.org/wikipedia/commons/7/7f/Skovl.jpg" alt="Foto da Pá" style="width: 150px; height: auto; border-radius: 10px;">
                <!-- BOTÃO SOBRE A IMAGEM -->
                <button onclick="testarProduto('video-pa'); event.stopPropagation();" style="position: absolute; top: 5px; left: 5px; background-color: #ffcc00; border: none; padding: 5px 10px; border-radius: 5px; cursor: pointer;">
                    Testar produto
                </button>
            </div>
            <h2>Pá - R$20</h2>
            <p>Clique para comprar</p>
        </div>

        <!-- ITEM DO MARTELO (SEM ALTERAÇÕES) -->
        <div class="item" onclick="showDetails('martelo')">
            <button onclick="alert('Testando o Martelo!'); event.stopPropagation();">Testando os produtos</button>
            <h2>Martelo - R$30</h2>
            <img src="https://thumbs.dreamstime.com/b/martelo-sujo-isolado-75049700.jpg" alt="Foto do Martelo" style="width: 150px; height: auto; border-radius: 10px;">
            <p>Clique para comprar</p>
        </div>

        <!-- DETALHES DA PÁ -->
        <div id="pa" class="details">
            <h2>Detalhes da Pá</h2>
            <p>Preço: R$20</p>
            <p>Descrição: Pá de alta qualidade para carpinteiros.</p>
             <!-- BOTÃO DE COMPRA -->
<button onclick="abrirCompraZoada()" style="
background-color: #ffcc00;
color: #000;
font-weight: bold;
border: none;
padding: 10px 20px;
margin-top: 10px;
border-radius: 8px;
cursor: pointer;
">
Comprar via Pix
</button>



            <!-- VÍDEO ESCONDIDO (YouTube) -->
<div id="video-pa" style="display: none; margin-top: 15px;">
    <iframe width="320" height="240" 
            src="https://www.youtube.com/embed/oLziHcjvHBI" 
            title="Vídeo engraçado com pá" 
            frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
            allowfullscreen>
    </iframe>
</div>


            <button onclick="hideDetails()">Fechar</button>
        </div>

        <!-- DETALHES DO MARTELO -->
        <div id="martelo" class="details">
            <h2>Detalhes do Martelo</h2>
            <p>Preço: R$30</p>
            <p>Descrição: Martelo resistente para trabalhos pesados.</p>
            <p>pix do pai: 140.250.699-62</p>
            <button onclick="hideDetails()">Fechar</button>
        </div>
    </main>
    <footer>
        <p>&copy; site do josé brabo car<b>pinto</b>eiro</p>
    </footer>

    <!-- SCRIPTS -->
    <script>
        function showDetails(itemId) {
            const details = document.querySelectorAll('.details');
            details.forEach(detail => detail.classList.remove('active'));

            document.getElementById(itemId).classList.add('active');
        }

        function hideDetails() {
            const details = document.querySelectorAll('.details');
            details.forEach(detail => detail.classList.remove('active'));

            // Esconde e reseta vídeos também
            const videos = document.querySelectorAll('.details video');
            videos.forEach(video => {
                video.pause();
                video.currentTime = 0;
                video.parentElement.style.display = 'none';
            });
        }

        function testarProduto(videoId) {
            const video = document.getElementById(videoId);
            if (video) {
                video.style.display = 'block';
            }
        }

        function abrirCompraZoada() {
    window.open("https://www.youtube.com/watch?v=L8OesNa-pkA", "_blank");
}



    </script>
</body>
</html>
