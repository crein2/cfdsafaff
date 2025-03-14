<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Кроссворд: Перспективы цифрового рубля</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
        }

        .container {
            max-width: 800px;
            margin: 50px auto;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        h1 {
            text-align: center;
            color: #2962ff;
        }

        .crossword-grid {
            display: grid;
            grid-template-columns: repeat(15, 40px);
            grid-gap: 2px;
            justify-content: center;
            margin-bottom: 20px;
        }

        .crossword-grid input {
            width: 40px;
            height: 40px;
            text-align: center;
            font-size: 18px;
            font-weight: bold;
            text-transform: uppercase;
            border: 1px solid #ccc;
        }

        .clues {
            margin-top: 20px;
        }

        .clues h2 {
            color: #2962ff;
        }

        .clues ul {
            list-style-type: none;
            padding: 0;
        }

        .clues li {
            margin-bottom: 10px;
        }

        .clues span {
            font-weight: bold;
        }

        button {
            display: block;
            width: 100%;
            padding: 10px;
            background-color: #2962ff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            margin-top: 20px;
        }

        button:hover {
            background-color: #1e4db7;
        }

        .result {
            margin-top: 20px;
            font-size: 18px;
            text-align: center;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Кроссворд: Перспективы цифрового рубля</h1>

        <!-- Кроссвордная сетка -->
        <div class="crossword-grid">
            <!-- Строка 1 -->
            <input maxlength="1" data-answer="Ц"><input maxlength="1" data-answer="И"><input maxlength="1" data-answer="Ф"><input maxlength="1" data-answer="Р"><input maxlength="1" data-answer="О"><input maxlength="1" data-answer="В"><input maxlength="1" data-answer="А"><input maxlength="1" data-answer="Я"><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled>
            <!-- Строка 2 -->
            <input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input maxlength="1" data-answer="Б"><input maxlength="1" data-answer="Е"><input maxlength="1" data-answer="З"><input maxlength="1" data-answer="О"><input maxlength="1" data-answer="П"><input maxlength="1" data-answer="А"><input maxlength="1" data-answer="С">
            <!-- Строка 3 -->
            <input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input maxlength="1" data-answer="У"><input maxlength="1" data-answer="Д"><input maxlength="1" data-answer="О"><input maxlength="1" data-answer="Б"><input maxlength="1" data-answer="С">
            <!-- Строка 4 -->
            <input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input maxlength="1" data-answer="Т"><input maxlength="1" data-answer="Р"><input maxlength="1" data-answer="А">
            <!-- Строка 5 -->
            <input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input maxlength="1" data-answer="Н"><input maxlength="1" data-answer="С"><input maxlength="1" data-answer="А">
            <!-- Строка 6 -->
            <input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input maxlength="1" data-answer="З"><input maxlength="1" data-answer="А"><input maxlength="1" data-answer="К">
            <!-- Строка 7 -->
            <input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input disabled><input maxlength="1" data-answer="О"><input maxlength="1" data-answer="Н"><input maxlength="1" data-answer="А">
        </div>

        <!-- Подсказки -->
        <div class="clues">
            <h2>Подсказки:</h2>
            <ul>
                <li><span>По горизонтали:</span></li>
                <li>1. Цифровая валюта, выпускаемая Центральным банком России.</li>
                <li>2. Способность цифрового рубля уменьшить зависимость от иностранных платежных систем.</li>
                <li>3. Удобство использования цифрового рубля в повседневной жизни.</li>
                <li>4. Процесс перевода денег с одного счета на другой.</li>
                <li>5. Основное преимущество цифрового рубля, связанное с отсутствием мошенничества.</li>
                <li><span>По вертикали:</span></li>
                <li>6. Технология, лежащая в основе многих цифровых валют, обеспечивающая безопасность данных.</li>
                <li>7. Наука, изучающая производство, распределение и потребление товаров и услуг.</li>
                <li>8. Мера, которая может помочь снизить уровень коррупции в финансовой системе страны.</li>
                <li>9. Возможность улучшения финансовой грамотности населения через цифровой рубль.</li>
                <li>10. Будущее использование цифрового рубля всеми гражданами.</li>
            </ul>
        </div>

        <!-- Кнопка проверки -->
        <button onclick="checkAnswers()">Проверить ответы</button>

        <!-- Результат -->
        <div class="result" id="result"></div>
    </div>

    <script>
        function checkAnswers() {
            const inputs = document.querySelectorAll('.crossword-grid input');
            let correct = 0;

            inputs.forEach(input => {
                const userAnswer = input.value.toUpperCase();
                const correctAnswer = input.dataset.answer;

                if (userAnswer === correctAnswer) {
                    input.style.backgroundColor = "#d4edda";
                    input.style.borderColor = "#c3e6cb";
                    correct++;
                } else {
                    input.style.backgroundColor = "#f8d7da";
                    input.style.borderColor = "#f5c6cb";
                }
            });

            const resultDiv = document.getElementById("result");
            resultDiv.textContent = `Вы правильно ответили на ${correct} из 15 вопросов!`;
        }
    </script>
</body>
</html>
