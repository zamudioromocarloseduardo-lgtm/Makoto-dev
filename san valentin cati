<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Para mi San Valentín ❤️</title>
    <style>
        :root {
            --color-sobre: #ff4d6d;
            --color-sobre-oscuro: #ff0e3b;
            --color-carta: #fff0f3;
            --color-fondo: #ffe5ec;
        }

        * {
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent; /* Quita el destello azul en móvil */
        }

        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: var(--color-fondo);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
            touch-action: manipulation;
        }

        /* --- PANTALLA PREGUNTA --- */
        #pantalla-pregunta {
            text-align: center;
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(255, 77, 109, 0.3);
            z-index: 10;
            width: 90%;
            max-width: 350px;
            transition: all 0.5s ease;
        }

        .oculto {
            opacity: 0;
            transform: scale(0);
            display: none !important;
        }

        h1 { color: #ff4d6d; font-size: 1.5rem; margin: 15px 0; }

        .btn-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            margin-top: 20px;
            min-height: 60px;
        }

        button {
            padding: 15px 30px;
            font-size: 1.2rem;
            border: none;
            border-radius: 15px;
            cursor: pointer;
            font-weight: bold;
            touch-action: none;
        }

        #btn-si {
            background: #ff4d6d;
            color: white;
            box-shadow: 0 4px 10px rgba(255, 77, 109, 0.4);
        }

        #btn-no {
            background: #adb5bd;
            color: white;
            position: relative; /* Cambia a absolute vía JS */
            transition: all 0.2s ease;
        }

        /* --- SOBRE ADAPTADO --- */
        .envelope-wrapper {
            position: relative;
            cursor: pointer;
            display: none;
            transform: scale(0.9); /* Un poco más pequeño para móviles */
        }

        .envelope {
            position: relative;
            width: 280px;
            height: 180px;
            background-color: var(--color-sobre);
            border-radius: 0 0 10px 10px;
        }

        .envelope::before {
            content: "";
            position: absolute;
            top: 0; z-index: 4;
            border-left: 140px solid transparent;
            border-right: 140px solid transparent;
            border-top: 100px solid var(--color-sobre-oscuro);
            transform-origin: top;
            transition: transform 0.5s ease 0.3s;
        }

        .envelope::after {
            content: ""; position: absolute; z-index: 2;
            width: 0; height: 0;
            border-top: 90px solid transparent;
            border-right: 140px solid #ff758f;
            border-bottom: 90px solid #ff758f;
            border-left: 140px solid #ff8fa3;
            border-radius: 0 0 10px 10px;
        }

        .letter {
            position: absolute; bottom: 5px; left: 10px;
            width: 260px; height: 160px;
            background-color: var(--color-carta);
            z-index: 1; transition: transform 0.6s ease;
            padding: 15px; text-align: center; border-radius: 5px;
        }

        .letter h2 { color: var(--color-sobre-oscuro); font-size: 1rem; margin: 5px 0; }
        .letter p { color: #555; font-size: 0.8rem; line-height: 1.3; }

        .heart-seal {
            position: absolute; top: 75px; left: 125px;
            width: 30px; height: 30px;
            background-color: white; z-index: 5;
            transform: rotate(-45deg); transition: 0.5s;
        }
        .heart-seal::before, .heart-seal::after {
            content: ""; position: absolute; width: 30px; height: 30px;
            background-color: white; border-radius: 50%;
        }
        .heart-seal::before { top: -15px; left: 0; }
        .heart-seal::after { left: 15px; top: 0; }

        .envelope-wrapper.open .envelope::before { transform: rotateX(180deg); z-index: 0; }
        .envelope-wrapper.open .letter { transform: translateY(-100px); z-index: 3; }
        .envelope-wrapper.open .heart-seal { opacity: 0; }

        /* Partículas */
        .particle { position: absolute; pointer-events: none; animation: float 3s linear forwards; z-index: 100; }
        @keyframes float {
            0% { transform: translateY(100vh) scale(1); opacity: 1; }
            100% { transform: translateY(-10vh) scale(0.5); opacity: 0; }
        }
    </style>
</head>
<body>

    <audio id="snd-pop" src="https://assets.mixkit.co/active_storage/sfx/2571/2571-preview.mp3" preload="auto"></audio>
    <audio id="snd-victory" src="https://assets.mixkit.co/active_storage/sfx/1435/1435-preview.mp3" preload="auto"></audio>

    <div id="pantalla-pregunta">
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHp1ZjR4N3V6OHZ0cWtzbXJ6cW84eXF4eXF4eXF4eXF4eXF4eCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/cLS1cfxvGOPVpf9g3y/giphy.gif" width="140">
        <h1>¿Quieres ser mi San Valentín? ❤️</h1>
        <div class="btn-container">
            <button id="btn-si">¡SÍ!</button>
            <button id="btn-no">No</button>
        </div>
    </div>

    <div id="pantalla-sobre" class="envelope-wrapper">
        <div class="envelope">
            <div class="letter">
                <h2>¡SABÍA QUE SÍ! 😍</h2>
                <p>Eres la persona más increíble del mundo. Gracias por aceptar ser mi San Valentín. ¡Te quiero muchísimo! ✨</p>
                <small style="color: #ff4d6d; font-size: 0.7rem;">(Toca el sobre para cerrar)</small>
            </div>
        </div>
        <div class="heart-seal"></div>
    </div>

    <script>
        const btnNo = document.getElementById('btn-no');
        const btnSi = document.getElementById('btn-si');
        const pantallaPregunta = document.getElementById('pantalla-pregunta');
        const pantallaSobre = document.getElementById('pantalla-sobre');
        const sndPop = document.getElementById('snd-pop');
        const sndVictory = document.getElementById('snd-victory');

        function moverBotonNo() {
            sndPop.currentTime = 0;
            sndPop.play();
            
            // Calculamos límites para que no se salga de la pantalla
            const padding = 50;
            const x = Math.random() * (window.innerWidth - btnNo.clientWidth - padding);
            const y = Math.random() * (window.innerHeight - btnNo.clientHeight - padding);
            
            btnNo.style.position = 'fixed';
            btnNo.style.left = Math.max(padding/2, x) + 'px';
            btnNo.style.top = Math.max(padding/2, y) + 'px';
        }

        // Eventos para el botón NO (Ratón y Toque)
        btnNo.addEventListener('mouseover', moverBotonNo);
        btnNo.addEventListener('touchstart', (e) => {
            e.preventDefault(); // Evita el clic real en móviles
            moverBotonNo();
        });

        // Evento para el botón SÍ
        btnSi.addEventListener('click', () => {
            sndVictory.play();
            pantallaPregunta.classList.add('oculto');
            
            setTimeout(() => {
                pantallaPregunta.style.display = 'none';
                pantallaSobre.style.display = 'block';
                createHearts(30);
            }, 500);
        });

        // Abrir/Cerrar sobre
        pantallaSobre.addEventListener('click', () => {
            pantallaSobre.classList.toggle('open');
            if(pantallaSobre.classList.contains('open')) {
                createHearts(10);
            }
        });

        function createHearts(cantidad) {
            for (let i = 0; i < cantidad; i++) {
                setTimeout(() => {
                    const p = document.createElement('div');
                    p.classList.add('particle');
                    p.innerHTML = ['❤️', '💖', '✨', '🌸'][Math.floor(Math.random() * 4)];
                    p.style.left = Math.random() * 100 + 'vw';
                    p.style.fontSize = (Math.random() * 25 + 15) + 'px';
                    p.style.animationDuration = (Math.random() * 2 + 2) + 's';
                    document.body.appendChild(p);
                    setTimeout(() => p.remove(), 3000);
                }, i * 100);
            }
        }

        // Lluvia constante de fondo
        setInterval(() => {
            if (pantallaSobre.style.display !== 'block') {
                const p = document.createElement('div');
                p.classList.add('particle');
                p.innerHTML = '❤️';
                p.style.left = Math.random() * 100 + 'vw';
                p.style.opacity = '0.3';
                document.body.appendChild(p);
                setTimeout(() => p.remove(), 3000);
            }
        }, 1500);
    </script>
</body>
</html>
