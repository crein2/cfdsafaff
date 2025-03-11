<!-- Тест "Проверь свои знания" -->
<section class="content-section">
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
            const correctAnswers = {
                q1: "b",
                q2: "b",
                q3: "a",
                q4: "b",
                q5: "b"
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

<!-- Футер -->
<footer class="footer">
    <p>МОУ "Средняя школа №99" • Ярославль 2025</p>
    <p>Руководитель: Белов В.Н. • Учитель обществознания</p>
</footer>

</body>
</html>
