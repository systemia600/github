<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Proyección de Imágenes</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            background-color: black;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }
        img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
            display: none;
        }
        img.active {
            display: block;
        }
    </style>
</head>
<body>

    <!-- ⚠️ REEMPLAZA LOS NOMBRES DE AQUÍ ABAJO POR TUS IMÁGENES -->
    <img src="https://github.com/systemia600/index.html/blob/main/Grabaci%C3%B3n%202026-11-04%20173740.mp4" class="active">
    <img src="https://github.com/systemia600/index.html/blob/main/Screenshot_20211130-092900_Chrome%20(1).jpg?raw=true">
    <img src="">

    <script>
        // Configuración del tiempo en milisegundos (5000 ms = 10 segundos)
        const TIEMPO_CAMBIO = 5000; 

        const imagenes = document.querySelectorAll('img');
        let indiceActual = 0;

        function cambiarImagen() {
            imagenes[indiceActual].classList.remove('active');
            indiceActual = (indiceActual + 1) % imagenes.length; // Hace el ciclo infinito
            imagenes[indiceActual].classList.add('active');
        }

        setInterval(cambiarImagen, TIEMPO_CAMBIO);
    </script>
</body>
</html>
