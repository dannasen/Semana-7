# Semana-7

*preguntas-semana7.txt*
Pregunta 1:
Respuesta: B. Una estructura que permite almacenar varios datos en una lista

Pregunta 2:
Respuesta: B. GET

Pregunta 3:
Respuesta: B. POST

Pregunta 4:
Respuesta: B. Permitir que diferentes sistemas o aplicaciones intercambien información
*server.js* - Código completo del servidor
const express = require('express');
const app = express();

app.use(express.json());

let reportes = [];

// Ruta GET para consultar reportes
app.get('/reportes', (req, res) => {
  res.json(reportes);
});

// Ruta POST para agregar reportes
app.post('/reportes', (req, res) => {
  const nuevoReporte = {
    id: reportes.length + 1,
    tipo: req.body.tipo,
    descripcion: req.body.descripcion
  };
  reportes.push(nuevoReporte);
  res.json(nuevoReporte);
});

app.listen(3000, () => {
  console.log('Servidor ejecutándose en puerto 3000');
});
*ejemplos-reportes.txt*
Ejemplo 1:
{
  "tipo": "Infraestructura",
  "descripcion": "Daño en alumbrado público en la calle principal"
}

Ejemplo 2:
{
  "tipo": "Ambiente",
  "descripcion": "Acumulación de basuras en el parque central"
}
*prueba-reportes.txt*
Prueba de la ruta POST:
URL: http://localhost:3000/reportes
Método: POST
JSON enviado: {"tipo": "Infraestructura", "descripcion": "Daño en alumbrado público"}

Prueba de la ruta GET:
URL: http://localhost:3000/reportes
Método: GET
Resultado: Se obtuvo la lista de reportes registrados
*reflexion-semana7.txt*
Reflexión Semana 7

Aprendí a crear un servidor básico con Express y Node.js para registrar y consultar reportes. 
Entendí la diferencia entre los métodos GET y POST y cómo usar un array para guardar datos en memoria.
Es importante que las comunidades puedan registrar y consultar reportes en una plataforma porque así tienen evidencia de los problemas, pueden hacer seguimiento y exigir soluciones a las entidades de forma organizada y transparente.
La tecnología ayuda a que la participación ciudadana sea más rápida y visible.
