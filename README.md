<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulario de Evento</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            height: 100vh;
            background: linear-gradient(45deg, #ff9a9e 0%, #fad0c4 50%, #fecfef 100%);
            background-size: 400% 400%;
            animation: gradientBG 10s ease infinite;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        form {
            width: 90%;
            max-width: 500px;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            position: relative;
            z-index: 1;
        }

        label, input, textarea {
            display: block;
            width: 100%;
            margin-bottom: 10px;
        }

        input[type="radio"] {
            display: inline-block;
            width: auto;
        }

        input[type="submit"] {
            width: auto;
            padding: 10px 20px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #fff;
            border-radius: 50%;
            animation: confettiFall 5s linear infinite;
            opacity: 0.7;
        }

        @keyframes confettiFall {
            0% { transform: translateY(-100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
        }
    </style>
</head>
<body>
    <form>
        <label for="nombre">Nombre y apellido:</label><br>
        <input type="text" id="nombre" name="nombre"><br><br>

        <label for="mensaje">¿Quieres dejar un mensaje al cumpleañero?</label><br>
        <textarea id="mensaje" name="mensaje"></textarea><br><br>

        <label>Confirma tu asistencia:</label><br>
        <input type="radio" id="asistir_si" name="asistencia" value="si">
        <label for="asistir_si">Sí</label><br>
        <input type="radio" id="asistir_no" name="asistencia" value="no">
        <label for="asistir_no">No</label><br><br>

        <label>Irás caracterizado/disfrazado:</label><br>
        <input type="radio" id="disfraz_si" name="disfraz" value="si">
        <label for="disfraz_si">Sí</label><br>
        <input type="radio" id="disfraz_no" name="disfraz" value="no">
        <label for="disfraz_no">No</label><br>
        <p>(en caso de marcar No, nosotros nos ofrecemos pintarte el cabello con pintura en aerosol vegetal)</p><br>

        <label>Llevarás una bebida para compartir:</label><br>
        <input type="radio" id="bebida_si" name="bebida" value="si">
        <label for="bebida_si">Sí</label><br>
        <input type="radio" id="bebida_no" name="bebida" value="no">
        <label for="bebida_no">No</label><br>
        <p>(en caso de marcar No, no te preocupes, esto nos sirve para ver el recuento de bebidas)</p><br>

        <input type="submit" value="Enviar">
    </form>

    <script>
        function createConfetti() {
            const confetti = document.createElement('div');
            confetti.classList.add('confetti');
            confetti.style.left = Math.random() * 100 + 'vw';
            confetti.style.backgroundColor = '#' + Math.floor(Math.random()*16777215).toString(16);
            confetti.style.animationDuration = Math.random() * 3 + 2 + 's';
            document.body.appendChild(confetti);

            setTimeout(() => {
                confetti.remove();
            }, 5000);
        }

        setInterval(createConfetti, 300);
    </script>
</body>
</html>
# Cumple-de-Gaston
Muy feliz cumpleaños Gaston!!!
