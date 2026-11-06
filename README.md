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
    <img src="imagen1.jpg" class="active">
    <img src="imagen2.png">
    <img src="imagen3.jpg">

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
