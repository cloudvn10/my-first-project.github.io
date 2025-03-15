<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Музыкальный плеер</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .player {
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .play-button {
            width: 100px; /* Ширина кнопки */
            height: 100px; /* Высота кнопки */
            border: none;
            border-radius: 50%; /* Круглая форма */
            background-color: #007bff; /* Цвет фона кнопки */
            color: white; /* Цвет текста */
            font-size: 24px; /* Размер шрифта */
            cursor: pointer; /* Курсор в виде указателя */
            display: flex; /* Flexbox для центрирования текста */
            justify-content: center; /* Центрирование по горизонтали */
            align-items: center; /* Центрирование по вертикали */
            transition: background-color 0.3s; /* Плавный переход цвета */
        }
        .play-button:hover {
            background-color: #0056b3; /* Цвет кнопки при наведении */
        }
        .color-changing-text {
            font-size: 36px; /* Размер шрифта для текста */
            animation: colorChange 3s infinite; /* Анимация изменения цвета */
        }
        @keyframes colorChange {
            0% { color: red; }
            25% { color: yellow; }
            50% { color: green; }
            75% { color: blue; }
            100% { color: red; }
        }
    </style>
</head>
<body>

<div class="player">
    <h2 class="color-changing-text">лох</h2> <!-- Текст, который будет менять цвет -->
    <audio id="audio" src="C:\Users\18kon_kn9b95p\Downloads\mysong.mp3.mp3" preload="auto"></audio>
    <div>
        <button id="playBtn" class="play-button">►</button> <!-- Символ "play" -->
    </div>
</div>

<script>
    const audio = document.getElementById('audio');
    const playBtn = document.getElementById('playBtn');

    let isPlaying = false;

    playBtn.addEventListener('click', () => {
        if (isPlaying) {
            audio.pause(); // Приостановить воспроизведение
            playBtn.innerHTML = '►'; // Вернуть символ "play"
        } else {
            audio.play(); // Запустить воспроизведение
            playBtn.innerHTML = '❚❚'; // Изменить на символ "pause"
        }
        isPlaying = !isPlaying; // Переключить состояние
    });
</script>

</body>
</html>
