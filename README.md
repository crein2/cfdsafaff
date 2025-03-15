<section class="content-section">
    <div class="container">
        <h1>Проверь свои знания прямо сейчас!</h1>
        
        <form id="quizForm">
            <!-- Вопрос 1 -->
            <div class="question">
                <p><strong>1. Что такое цифровой рубль?</strong></p>
                <div class="options">
                    <label><input type="radio" name="1" value="1"> Новая криптовалюта</label><br>
                    <label><input type="radio" name="1" value="2"> Электронные деньги от ЦБ РФ</label><br>
                    <label><input type="radio" name="1" value="3"> Программа для банков</label>
                </div>
            </div>

            <!-- Вопрос 2 -->
            <div class="question">
                <p><strong>2. В каком году начался пилотный проект цифрового рубля?</strong></p>
                <div class="options">
                    <label><input type="radio" name="2" value="1"> 2020</label><br>
                    <label><input type="radio" name="2" value="2"> 2023</label><br>
                    <label><input type="radio" name="2" value="3"> 2025</label>
                </div>
            </div>

            <!-- Вопрос 3 -->
            <div class="question">
                <p><strong>3. Какой закон легализовал цифровые активы в России?</strong></p>
                <div class="options">
                    <label><input type="radio" name="3" value="1"> Закон о ЦФА</label><br>
                    <label><input type="radio" name="3" value="2"> Закон о налогах</label><br>
                    <label><input type="radio" name="3" value="3"> Закон о банках</label>
                </div>
            </div>

            <!-- Вопрос 4 -->
            <div class="question">
                <p><strong>4. Сколько регионов участвует в пилоте цифрового рубля?</strong></p>
                <div class="options">
                    <label><input type="radio" name="4" value="1"> 5</label><br>
                    <label><input type="radio" name="4" value="2"> 12</label><br>
                    <label><input type="radio" name="4" value="3"> 20</label>
                </div>
            </div>

            <!-- Вопрос 5 -->
            <div class="question">
                <p><strong>5. Какая комиссия планируется за переводы через цифровой рубль?</strong></p>
                <div class="options">
                    <label><input type="radio" name="5" value="1"> 0%</label><br>
                    <label><input type="radio" name="5" value="2"> 0.05%</label><br>
                    <label><input type="radio" name="5" value="3"> 1%</label>
                </div>
            </div>

            <!-- Кнопка проверки -->
            <button type="button" onclick="checkAnswers()" style="margin-top: 20px;">Проверить ответы</button>
        </form>

        <!-- Результаты -->
        <div class="result" id="result" style="margin-top: 20px;"></div>
        <div class="feedback" id="feedback" style="margin-top: 10px;"></div>
    </div>

    <style>
        /* Общие стили */
        .question {
            margin-bottom: 20px; /* Отступ между вопросами */
        }

        .options label {
            display: block; /* Каждый вариант ответа на новой строке */
            margin-bottom: 5px; /* Отступ между вариантами ответов */
        }

        button {
            padding: 10px 20px;
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

        .correct {
            color: green;
        }

        .incorrect {
            color: red;
        }
    </style>

    <script>
        function checkAnswers() {
            const correctAnswers = {
                1: "2",
                2: "2",
                3: "1",
                4: "2",
                5: "2"
            };

            let score = 0;
            let feedback = "";

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

            const resultDiv = document.getElementById("result");
            resultDiv.textContent = `Вы ответили правильно на ${score} из 5 вопросов!`;

            const feedbackDiv = document.getElementById("feedback");
            feedbackDiv.innerHTML = feedback;
        }
    </script>
</section>
