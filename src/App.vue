```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Melody Maker - Substituição de Texto</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
            color: #333;
        }

        .melody-maker-container {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        h1 {
            color: #2c3e50;
            margin-bottom: 20px;
        }

        p {
            font-size: 1.2em;
            font-weight: bold;
            color: #34495e;
        }

        #originalText {
            color: #7f8c8d;
            font-size: 0.9em;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="melody-maker-container">
        <h1>Projeto Melody Maker</h1>
        <p>Texto Atualizado:</p>
        <p id="phraseToModify">Atire o pau no gato</p>
        <p id="originalText">(Texto original era: "Atire o pau no gato")</p>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Localiza o elemento pelo ID
            const phraseElement = document.getElementById('phraseToModify');

            // Verifica se o elemento existe
            if (phraseElement) {
                // Pega o texto atual
                let currentText = phraseElement.textContent;

                // Define a palavra a ser substituída (case-insensitive) e a nova palavra
                const palavraAntiga = /pau/gi; // 'g' para global, 'i' para case-insensitive
                const palavraNova = 'Karlos';

                // Realiza a substituição
                let newText = currentText.replace(palavraAntiga, palavraNova);

                // Atualiza o texto do elemento
                phraseElement.textContent = newText;

                // Opcional: Atualiza o texto original para refletir a mudança no demo
                document.getElementById('originalText').textContent = `(Texto original: "${currentText}")`;
            } else {
                console.error('Elemento com ID "phraseToModify" não encontrado.');
            }
        });
    </script>
</body>
</html>
```