<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Precio de Cerveza</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #1e1e2f;
            color: #ffffff;
        }
        .app-container {
            background: #2a2a3b;
            padding: 40px;
            border-radius: 16px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
            width: 100%;
            max-width: 600px;
        }
        h1 {
            font-size: 2.2rem;
            text-align: center;
            margin-bottom: 25px;
            color: #ffffff;
        }
        .input-container {
            display: flex;
            flex-direction: column;
            gap: 20px;
            margin-bottom: 20px;
        }
        .input-container label {
            font-weight: 600;
            color: #c5c5d2;
            font-size: 1.2rem;
            margin-bottom: 10px;
            display: block;
        }
        .input-box {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 100%;
        }
        input {
            padding: 20px;
            width: 100%;
            height: 100px;
            border: 1px solid #44475a;
            border-radius: 8px;
            box-sizing: border-box;
            font-size: 2rem;
            background-color: #3a3a4d;
            color: #ffffff;
            text-align: center;
        }
        button {
            margin-top: 30px;
            width: 100%;
            padding: 20px;
            background-color: #3b82f6;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 1.5rem;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #2563eb;
        }
        .result {
            margin-top: 30px;
            padding: 30px;
            border-radius: 8px;
            background-color: #2e2e40;
            color: #ffffff;
            font-weight: 600;
            text-align: center;
            font-size: 1.5rem;
        }
    </style>
</head>
<body>
    <div class="app-container">
        <h1>Calculadora de Precio de Cerveza</h1>
        <div class="input-container">
            <div class="input-box">
                <label for="ml1">Mililitros</label>
                <input type="number" id="ml1" min="1">
            </div>
            <div class="input-box">
                <label for="cantidad1">Cervezas</label>
                <input type="number" id="cantidad1" min="1">
            </div>
            <div class="input-box">
                <label for="precio1">Precio total ($):</label>
                <input type="number" id="precio1" min="0.01" step="0.01">
            </div>
        </div>
        <button onclick="calcularPrecioPorLitro()">Calcular el costo por litro</button>
        <div id="resultado" class="result"></div>
    </div>

    <script>
        function calcularPrecioPorLitro() {
            // Obtener los valores de la Opción 1
            const ml1 = parseFloat(document.getElementById('ml1').value);
            const cantidad1 = parseInt(document.getElementById('cantidad1').value);
            const precio1 = parseFloat(document.getElementById('precio1').value);

            if (ml1 > 0 && cantidad1 > 0 && precio1 > 0) {
                // Calcular el precio por litro
                const totalMl = ml1 * cantidad1;
                const totalLitros = totalMl / 1000;
                const precioPorLitro = precio1 / totalLitros;

                const resultadoText = `El costo por litro es de $${precioPorLitro.toFixed(2)}.\nCantidad total de cerveza: ${totalLitros.toFixed(2)} litros.`;
                alert(resultadoText);
            } else {
                alert('Por favor, completa todos los campos con valores válidos.');
            }
        }
    </script>
</body>
</html>
