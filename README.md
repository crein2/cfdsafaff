<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>'Arial'</title>
    <style>
        /* Подключение локального шрифта */
        @font-face {
            font-family: 'CustomFont';
            src: url('fonts/CustomFont.ttf') format('truetype');
        }

        /* Применение шрифта */
        body {
            font-family: 'CustomFont', sans-serif;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <h1>Заголовок с локальным шрифтом</h1>
    <p>Это текст с использованием локального шрифта.</p>
</body>
</html>
