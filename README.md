<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jogo de Aventura</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            text-align: center;
        }
        .container {
            max-width: 800px;
            margin: 20px auto;
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            font-size: 24px;
            color: #333;
        }
        img {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
        }
        .button {
            display: inline-block;
            margin: 10px;
            padding: 10px 20px;
            font-size: 16px;
            color: #fff;
            background-color: #007bff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .button:hover {
            background-color: #0056b3;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Bem-vindo à Aventura!</h1>
        <div id="start">
            <img src="https://via.placeholder.com/800x400" alt="Imagem Inicial">
            <p>Escolha qual cidade ou estado visitar:</p>
            <button class="button" onclick="showSection('rio')">Rio de Janeiro</button>
            <button class="button" onclick="showSection('sao')">São Paulo</button>
        </div>
        
        <div id="rio" class="hidden">
            <p>Você começa sua jornada no Rio de Janeiro, subindo o Pico da Tijuca ao amanhecer para encontrar a primeira pista.</p>
            <button class="button" onclick="showSection('pico')">Procurar a pista no topo do pico</button>
            <button class="button" onclick="showSection('fim')">Desistir e voltar para casa</button>
        </div>
        
        <div id="pico" class="hidden">
            <p>No topo do Pico da Tijuca, você encontra uma antiga inscrição apontando que a próxima pista está localizada no Amazonas.</p>
            <button class="button" onclick="showSection('amazonas')">Seguir para o Amazonas</button>
        </div>
        
        <div id="amazonas" class="hidden">
            <p>No Amazonas, a busca pela cidade perdida se intensifica. Você se depara com um rio bifurcado.</p>
            <button class="button" onclick="showSection('direita')">Seguir pelo rio à direita</button>
            <button class="button" onclick="showSection('esquerda')">Seguir pelo rio à esquerda</button>
        </div>
        
        <div id="direita" class="hidden">
            <p>O rio à direita termina em uma área pantanosa. Apesar de belas vistas, não há sinais da cidade perdida aqui.</p>
            <button class="button" onclick="showSection('esquerda')">Retornar e tentar o outro rio</button>
        </div>
        
        <div id="esquerda" class="hidden">
            <p>Retornando e escolhendo o rio à esquerda, você finalmente encontra a cachoeira escondida e as inscrições que levam à cidade perdida.</p>
            <button class="button" onclick="showSection('fim')">Explorar a cidade perdida</button>
        </div>
        
        <div id="fim" class="hidden">
            <h2>Parabéns!</h2>
            <p>Você encontrou a cidade perdida e completou sua jornada!</p>
            <button class="button" onclick="showSection('start')">Iniciar Novamente</button>
        </div>
    </div>

    <script>
        function showSection(id) {
            const sections = document.querySelectorAll('.container > div');
            sections.forEach(section => section.classList.add('hidden'));
            document.getElementById(id).classList.remove('hidden');
        }

        // Inicialmente exibe a página de início
        showSection('start');
    </script>
</body>
</html>

