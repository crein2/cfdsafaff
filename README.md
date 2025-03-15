<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Галерея с анимацией</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background: #f0f0f0;
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
        }

        .gallery-item {
            cursor: pointer;
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s ease;
        }

        .gallery-item img {
            width: 100%;
            height: auto;
            display: block;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        /* Модальное окно */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        .modal-content {
            position: relative;
            max-width: 800px;
            max-height: 80vh;
            animation: zoomIn 0.5s ease;
        }

        .modal-img {
            width: 100%;
            height: auto;
            display: block;
        }

        .close {
            position: absolute;
            top: -20px;
            right: -20px;
            color: white;
            font-size: 30px;
            cursor: pointer;
            transition: color 0.3s;
        }

        .close:hover {
            color: #ff4444;
        }

        @keyframes zoomIn {
            from {
                transform: scale(0.8);
                opacity: 0;
            }
            to {
                transform: scale(1);
                opacity: 1;
            }
        }
    </style>
</head>
<body>

<div class="gallery" id="gallery">
    <div class="gallery-item" data-src="image1.jpg">
        <img src="thumbnail1.jpg" alt="Изображение 1">
    </div>
<div class="modal" id="modal">
    <span class="close">&times;</span>
    <img class="modal-img" id="modalImg">
</div>

<script>
    document.addEventListener('DOMContentLoaded', () => {
        const galleryItems = document.querySelectorAll('.gallery-item');
        const modal = document.getElementById('modal');
        const modalImg = document.getElementById('modalImg');
        const closeBtn = document.querySelector('.close');

        galleryItems.forEach(item => {
            item.addEventListener('click', () => {
                const src = item.getAttribute('data-src');
                modalImg.setAttribute('src', src);
                modal.style.display = 'flex';
                
                // Анимация появления
                setTimeout(() => {
                    modal.classList.add('active');
                }, 10);
            });
        });

        // Закрытие модального окна
        const closeModal = () => {
            modal.classList.remove('active');
            setTimeout(() => {
                modal.style.display = 'none';
            }, 500); // совпадает с длительностью анимации
        };

        closeBtn.addEventListener('click', closeModal);
        modal.addEventListener('click', (e) => {
            if (e.target === modal) closeModal();
        });
    });
</script>
