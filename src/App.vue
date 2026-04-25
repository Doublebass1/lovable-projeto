```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Controle de Velocidade BPM</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            background-color: #e0f2f7; /* Um azul claro de fundo */
            color: #333;
        }

        .container {
            background-color: #ffffff;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            text-align: center;
            max-width: 400px;
            width: 90%;
            border: 1px solid #cce7ee;
        }

        .title {
            color: blue; /* Cor azul */
            font-weight: bold; /* Negrito */
            margin-bottom: 30px;
            font-size: 2em; /* Tamanho maior para o título */
        }

        #bpmSlider {
            width: 100%;
            -webkit-appearance: none; /* Remove default styling */
            appearance: none;
            height: 10px;
            background: linear-gradient(to right, #4CAF50, #2196F3, #f44336); /* Gradiente de cor */
            outline: none;
            border-radius: 5px;
            margin-top: 20px;
            margin-bottom: 30px;
            cursor: pointer;
        }

        #bpmSlider::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 25px;
            height: 25px;
            background: #007bff; /* Azul vibrante para o "thumb" */
            border-radius: 50%;
            cursor: grab;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            border: 2px solid #fff; /* Borda branca para destaque */
        }

        #bpmSlider::-moz-range-thumb {
            width: 25px;
            height: 25px;
            background: #007bff;
            border-radius: 50%;
            cursor: grab;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            border: 2px solid #fff;
        }

        .bpm-display {
            font-size: 1.5em;
            margin-top: 20px;
            color: #555;
        }

        #bpmValue {
            font-weight: bold;
            color: #007bff; /* Destaca o valor do BPM */
            font-size: 1.8em;
            margin-left: 8px;
        }
    </style>
</head>
<body>

    <div class="container">
        <h2 class="title">Controle de Velocidade</h2>

        <input type="range" id="bpmSlider" min="60" max="240" value="120">

        <p class="bpm-display">BPM: <span id="bpmValue">120</span></p>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const bpmSlider = document.getElementById('bpmSlider');
            const bpmValueSpan = document.getElementById('bpmValue');

            // Define o valor inicial no display
            bpmValueSpan.textContent = bpmSlider.value;

            // Adiciona um listener para atualizar o valor do BPM conforme o slider é movido
            bpmSlider.addEventListener('input', () => {
                bpmValueSpan.textContent = bpmSlider.value;
                // Aqui você pode adicionar lógica para usar o valor do BPM,
                // como sincronizar com um metrônomo ou animação.
            });
        });
    </script>

</body>
</html>
```