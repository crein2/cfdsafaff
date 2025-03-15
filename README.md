<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Загрузка аватара</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            text-align: center;
            color: #333;
        }

        h1 {
            margin-top: 20px;
        }

        .avatar-container {
            margin: 20px auto;
            max-width: 300px;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        .avatar-preview img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid #ddd;
            margin-bottom: 20px;
        }

        .upload-section input[type="file"] {
            margin-top: 10px;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="avatar-container">
        <h1>Загрузите свою аватарку</h1>

        <!-- Предварительный просмотр аватара -->
        <div class="avatar-preview">
            <img id="previewImage" src="https://steamuserimages-a.akamaihd.net/ugc/2490006266246798416/5913C16B147216E0FC3ACED79489086079169C59/" alt="Аватар">
        </div>

        <!-- Раздел для загрузки изображения -->
        <div class="upload-section">
            <p>Выберите файл для загрузки:</p>
            <input type="file" id="avatarUpload" accept="image/*">
        </div>
    </div>

    <script>
        // Получаем элементы DOM
        const avatarUpload = document.getElementById('avatarUpload');
        const previewImage = document.getElementById('previewImage');

        // Добавляем обработчик события для загрузки файла
        avatarUpload.addEventListener('change', function (event) {
            const file = event.target.files[0]; // Получаем выбранный файл

            if (file) {
                const reader = new FileReader(); // Создаем объект FileReader

                // Когда файл будет загружен
                reader.onload = function (e) {
                    previewImage.src = e.target.result; // Устанавливаем src изображения
                };

                reader.readAsDataURL(file); // Читаем файл как Data URL
            } else {
                // Если файл не выбран, возвращаем placeholder
                previewImage.src = "https://steamuserimages-a.akamaihd.net/ugc/2490006266246798416/5913C16B147216E0FC3ACED79489086079169C59/";
            }
        });
    </script>
</body>
</html>
