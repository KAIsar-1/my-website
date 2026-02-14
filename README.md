<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Love is...</title>
<style>
    /* Сброс отступов и полный экран */
    html, body {
        margin: 0;
        padding: 0;
        height: 100%;
        overflow: hidden;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        background: #000;
    }

    /* Видео-фон */
    #myVideo {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        z-index: -2;
    }

    /* Тёмный слой для контраста */
    .dark-layer {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0,0,0,0.4);
        z-index: -1;
    }

    /* Центральная карточка с фото и текстом */
    .overlay {
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        text-align: center;
        color: #fff;
    }

    /* Фото с анимацией появления */
    .overlay img {
        max-width: 90%;
        max-height: 60%;
        border-radius: 20px;
        box-shadow: 0 0 30px rgba(0,0,0,0.7);
        opacity: 0;
        transform: translateY(20px);
        animation: fadeInUp 2s forwards;
    }

    /* Текст сверху */
    .overlay h1 {
        font-family: 'Comic Sans MS', cursive, sans-serif;
        font-size: 3em;
        margin: 20px 0 10px;
        opacity: 0;
        transform: translateY(-20px);
        animation: fadeInText 2s forwards;
        animation-delay: 2s;
        color: #ffc0cb; /* светло-розовый */
    }

    /* Текст снизу */
    .overlay p {
        font-size: 1.8em;
        opacity: 0;
        transform: translateY(20px);
        animation: fadeInText 2s forwards;
        animation-delay: 2.5s;
        color: #ffe4e1; /* кремовый */
    }

    /* Анимации */
    @keyframes fadeInUp {
        from { opacity: 0; transform: translateY(20px); }
        to { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeInText {
        from { opacity: 0; transform: translateY(20px); }
        to { opacity: 1; transform: translateY(0); }
    }
</style>
</head>
<body>

    <!-- Видео-фон -->
    <video autoplay muted loop playsinline id="myVideo">
        <source src="your-video.mp4" type="video/mp4">
        Ваш браузер не поддерживает видео.
    </video>

    <!-- Тёмный слой для контраста -->
    <div class="dark-layer"></div>

    <!-- Фото + текст -->
    <div class="overlay">
        <h1>Love is...</h1>
        <img src="your-photo.jpg" alt="Моё фото">
        <p>выбрать быть вместе</p>
    </div>

</body>
</html>
