<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Тест: Цифровой рубль</title>
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
            max-width: 600px;
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

        .question {
            margin-bottom: 20px;
        }

        .options label {
            display: block;
            margin: 5px 0;
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

        .feedback {
            margin-top: 20px;
            font-size: 16px;
        }

        .correct {
            color: green;
        }

        .incorrect {
            color: red;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Тест: Цифровой рубль</h1>

        <form id="quizForm">
            <!-- Вопрос 1 -->
            <div class="question">
                <p><strong>1. Что такое цифровой рубль?</strong></p>
                <div class="options">
                    <label><input type="radio" name="q1" value="a"> Новая криптовалюта</label>
                    <label><input type="radio" name="q1" value="b"> Электронные деньги от ЦБ РФ</label>
                    <label><input type="radio" name="q1" value="c"> Программа для банков</label>
                </div>
            </div>

            <!-- Вопрос 2 -->
            <div class="question">
                <p><strong>2. В каком году начался пилотный проект цифрового рубля?</strong></p>
                <div class="options">
                    <label><input type="radio" name="q2" value="a"> 2020</label>
                    <label><input type="radio" name="q2" value="b"> 2023</label>
                    <label><input type="radio" name="q2" value="c"> 2025</label>
                </div>
            </div>

            <!-- Вопрос 3 -->
            <div class="question">
                <p><strong>3. Какой закон легализовал цифровые активы в России?</strong></p>
                <div class="options">
                    <label><input type="radio" name="q3" value="a"> Закон о ЦФА</label>
                    <label><input type="radio" name="q3" value="b"> Закон о налогах</label>
                    <label><input type="radio" name="q3" value="c"> Закон о банках</label>
                </div>
            </div>

            <!-- Вопрос 4 -->
            <div class="question">
                <p><strong>4. Сколько регионов участвует в пилоте цифрового рубля?</strong></p>
                <div class="options">
                    <label><input type="radio" name="q4" value="a"> 5</label>
                    <label><input type="radio" name="q4" value="b"> 12</label>
                    <label><input type="radio" name="q4" value="c"> 20</label>
                </div>
            </div>

            <!-- Вопрос 5 -->
            <div class="question">
                <p><strong>5. Какая комиссия планируется за переводы через цифровой рубль?</strong></p>
                <div class="options">
                    <label><input type="radio" name="q5" value="a"> 0%</label>
                    <label><input type="radio" name="q5" value="b"> 0.05%</label>
                    <label><input type="radio" name="q5" value="c"> 1%</label>
                </div>
            </div>

            <button type="button" onclick="checkAnswers()">Проверить ответы</button>
        </form>

        <div class="result" id="result"></div>
        <div class="feedback" id="feedback"></div>
    </div>

    <script>
        function checkAnswers() {
            // Правильные ответы
            const correctAnswers = {
                1: "2",
                2: "2",
                3: "1",
                4: "2",
                5: "2"
            };

            let score = 0;
            let feedback = "";

            // Проверка ответов
            for (let question in correctAnswers) {
                const selected = document.querySelector(`input[name="${question}"]:checked`);
                const userAnswer = selected ? selected.value : null;

                if (userAnswer === correctAnswers[question]) {
                    score++;
                    feedback += `<p class="correct">Вопрос ${question}: Правильно!</p>`;
                } else {
                    feedback += `<p class="incorrect">Вопрос ${question}: Неправильно. Верный ответ: ${correctAnswers[question]}</p>`;
                }
            }

            // Вывод результата
            const resultDiv = document.getElementById("result");
            resultDiv.textContent = `Вы ответили правильно на ${score} из 5 вопросов!`;

            const feedbackDiv = document.getElementById("feedback");
            feedbackDiv.innerHTML = feedback;
        }
    </script>
</body>
</html>
