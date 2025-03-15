<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Загрузка и отображение картинки</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            text-align: center;
            color: #333;
        }

        h1 {
            margin-top: 20px;
        }

        .container {
            margin: 20px auto;
            max-width: 600px;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        .upload-section {
            margin-bottom: 20px;
        }

        .upload-section input[type="file"] {
            margin-top: 10px;
        }

        .image-preview img {
            max-width: 100%;
            height: auto;
            border-radius: 10px;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .image-preview img:hover {
            transform: scale(1.05);
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Загрузите свою картинку</h1>

        <!-- Раздел для загрузки изображения -->
        <div class="upload-section">
            <p>Выберите файл для загрузки:</p>
            <input type="file" id="imageUpload" accept="image/*">
        </div>

        <!-- Предварительный просмотр изображения -->
        <div class="image-preview hidden" id="imagePreview">
            <p>Ваша картинка:</p>
            <a id="imageLink" href="#" target="_blank">
                <img id="previewImage" src="" alt="Загруженное изображение">
            </a>
        </div>
    </div>

    <script>
        // Получаем элементы DOM
        const imageUpload = document.getElementById('imageUpload');
        const imagePreview = document.getElementById('imagePreview');
        const previewImage = document.getElementById('previewImage');
        const imageLink = document.getElementById('imageLink');

        // Добавляем обработчик события для загрузки файла
        imageUpload.addEventListener('change', function (event) {
            const file = event.target.files[0]; // Получаем выбранный файл

            if (file) {
                const reader = new FileReader(); // Создаем объект FileReader

                // Когда файл будет загружен
                reader.onload = function (e) {
                    previewImage.src = e.target.result; // Устанавливаем src изображения
                    imageLink.href = e.target.result; // Устанавливаем ссылку для клика
                    imagePreview.classList.remove('hidden'); // Показываем предпросмотр
                };

                reader.readAsDataURL(file); // Читаем файл как Data URL
            } else {
                imagePreview.classList.add('hidden'); // Скрываем предпросмотр, если файл не выбран
            }
        });
    </script>
</body>
</html>
