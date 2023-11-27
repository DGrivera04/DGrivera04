<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mapa Conceptual - Reflexión de la Luz</title>
  <script src="jsplumb.min.js"></script>
  <style>
    #mapa {
      width: 80%;
      height: 400px;
      margin: 20px auto;
      border: 1px solid #ddd;
      position: relative;
    }

    .concepto {
      width: 120px;
      padding: 10px;
      background-color: #f0f0f0;
      border: 1px solid #ccc;
      border-radius: 5px;
      position: absolute;
    }
  </style>
</head>
<body>
  <h1>Mapa Conceptual - Reflexión de la Luz</h1>
  
  <div id="mapa"></div>

  <script>
    document.addEventListener('DOMContentLoaded', function() {
      jsPlumb.ready(function() {
        // Configuración de JSPlumb
        jsPlumb.setContainer(document.getElementById('mapa'));

        // Agregar nodos
        var nodos = ['Luz', 'Superficie Reflectante', 'Ley de Reflexión', 'Espejos', 'Reflexión Difusa', 'Reflexión Especular', 'Color de los Objetos', 'Formación de Imágenes'];
        
        nodos.forEach(function(concepto, index) {
          var nodo = document.createElement('div');
          nodo.className = 'concepto';
          nodo.id = 'concepto' + index;
          nodo.innerHTML = concepto;
          document.getElementById('mapa').appendChild(nodo);

          // Hacer el nodo arrastrable
          jsPlumb.draggable(nodo.id, { containment: 'parent' });
        });

        // Conectar nodos
        jsPlumb.connect({ source: 'concepto0', target: 'concepto1' });
        jsPlumb.connect({ source: 'concepto1', target: 'concepto2' });
        jsPlumb.connect({ source: 'concepto1', target: 'concepto3' });
        jsPlumb.connect({ source: 'concepto3', target: 'concepto4' });
        jsPlumb.connect({ source: 'concepto3', target: 'concepto5' });
        jsPlumb.connect({ source: 'concepto5', target: 'concepto6' });
        jsPlumb.connect({ source: 'concepto3', target: 'concepto7' });
      });
    });
  </script>
</body>
</html>
