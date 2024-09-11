<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jeu de Devine le Nombre</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
        }

        .game-container {
            text-align: center;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        input {
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            width: 100px;
        }

        button {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            background-color: #007bff;
            color: white;
            cursor: pointer;
        }

        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="game-container">
        <h1>Devine le Nombre</h1>
        <p>Essaye de deviner le nombre entre 1 et 100.</p>
        <input type="number" id="guessInput" placeholder="Entrez un nombre">
        <button onclick="checkGuess()">Deviner</button>
        <p id="result"></p>
    </div>

    <script>
        // Génère un nombre aléatoire entre 1 et 100
        const secretNumber = Math.floor(Math.random() * 100) + 1;

        function checkGuess() {
            // Récupère la valeur de l'entrée
            const guess = parseInt(document.getElementById('guessInput').value);

            // Récupère l'élément où afficher le résultat
            const resultElement = document.getElementById('result');

            if (isNaN(guess) || guess < 1 || guess > 100) {
                resultElement.textContent = "Veuillez entrer un nombre entre 1 et 100.";
            } else if (guess === secretNumber) {
                resultElement.textContent = "Félicitations ! Vous avez deviné le nombre.";
            } else if (guess < secretNumber) {
                resultElement.textContent = "Trop bas ! Essayez encore.";
            } else {
                resultElement.textContent = "Trop haut ! Essayez encore.";
            }
        }
    </script>
</body>
</html>
