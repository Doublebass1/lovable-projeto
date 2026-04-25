```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Substituir Nome na Frase</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            background-color: #e9ecef;
            color: #343a40;
            text-align: center;
        }

        .container {
            background-color: #ffffff;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            width: 90%;
        }

        h1 {
            color: #007bff;
            margin-bottom: 25px;
            font-size: 2em;
        }

        p {
            font-size: 1.1em;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        #fraseOriginal {
            font-style: italic;
            color: #6c757d;
        }

        #fraseModificada {
            font-weight: bold;
            color: #28a745; /* Um verde vibrante para o texto modificado */
            min-height: 30px; /* Ajuda a evitar o "layout shift" quando o texto aparece */
            margin-top: 25px;
        }

        button {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.1em;
            transition: background-color 0.3s ease, transform 0.2s ease;
            box-shadow: 0 4px 8px rgba(0, 123, 255, 0.2);
        }

        button:hover {
            background-color: #0056b3;
            transform: translateY(-2px);
        }

        button:active {
            transform: translateY(0);
            box-shadow: 0 2px 4px rgba(0, 123, 255, 0.3);
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Transformar Nomes</h1>
        <p id="fraseOriginal">A antiga canção infantil era sobre "atirei o pau no gato".</p>
        <button id="botaoTrocarNome">Trocar para "Karlos"</button>
        <p id="fraseModificada">Clique no botão acima para ver a frase modificada.</p>
    </div>

    <script>
        // Obtém a referência para o elemento de parágrafo que contém a frase original
        const fraseOriginalElemento = document.getElementById('fraseOriginal');
        // Obtém a referência para o botão
        const botaoTrocarNome = document.getElementById('botaoTrocarNome');
        // Obtém a referência para o elemento onde a frase modificada será exibida
        const fraseModificadaElemento = document.getElementById('fraseModificada');

        // Armazena o texto original da frase
        const textoOriginal = fraseOriginalElemento.textContent; // Ex: "A antiga canção infantil era sobre "atirei o pau no gato"."

        // Adiciona um "ouvinte de evento" (event listener) ao botão
        botaoTrocarNome.addEventListener('click', () => {
            // Substitui "atirei o pau" (ignorando maiúsculas/minúsculas e globalmente se aparecer mais de uma vez)
            // pela palavra "Karlos".
            // O 'gi' na regex significa:
            // g = global (substitui todas as ocorrências, não apenas a primeira)
            // i = case-insensitive (não diferencia maiúsculas de minúsculas)
            const novoTexto = textoOriginal.replace(/atirei o pau/gi, 'Karlos');

            // Atualiza o conteúdo do parágrafo da frase modificada com o novo texto
            fraseModificadaElemento.textContent = novoTexto;
        });

        // Opcional: Você pode inicializar a frase modificada com o texto original
        // ou uma mensagem convidando o usuário a clicar.
        // Neste exemplo, já está com uma mensagem convidando o clique.
    </script>
</body>
</html>
```