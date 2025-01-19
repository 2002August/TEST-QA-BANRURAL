Plan de Ataque 

Objetivo

Solucionar los errores presentes en el archivo index.html del proyecto  Documentar los errores encontrados y las soluciones aplicadas.

Estrategia de Testeo

Preparación del entorno de pruebas:

Clonar el repositorio forkeado desde GitHub en el equipo local.

Abrir el archivo index.html en el navegador.

Abrir la consola del navegador para monitorear errores.

Identificación de errores:

Revisar los mensajes de error en la consola del navegador.

Probar la funcionalidad del juego con diferentes entradas, incluyendo:

Números válidos dentro del rango (1 a 100).

Números fuera del rango.

Entradas no numéricas (letras, caracteres especiales).

Documentación de errores:

Registrar cada error identificado con una breve descripción y su causa probable.

Corrección de errores:

Modificar el archivo index.html para solucionar los problemas.

Verificar los cambios en el navegador.

Pruebas de regresión:

Repetir las pruebas para asegurar que el archivo cumple con todos los requisitos funcionales y no se introdujeron nuevos errores.

Entrega final:

Subir el archivo index.html corregido al repositorio.

Documentar el plan de ataque y los errores encontrados en el archivo test-strategy.md.

Errores Encontrados y Soluciones

Error 1: Generación incorrecta del número aleatorio

Descripción: El número aleatorio generado no era entero y estaba fuera del rango especificado (1 a 100).

Causa: Uso incorrecto de Math.random() sin escalado y redondeo.

Solución: Reemplazar la línea:

let randomNumber = Math.random() * 10;

por:

let randomNumber = Math.floor(Math.random() * 100) + 1;

Error 2: Selector de clase mal definido

Descripción: El selector para el elemento lowOrHi no incluía el punto (.) necesario para seleccionar una clase.

Causa: Error en el uso de querySelector.

Solución: Reemplazar:

const lowOrHi = document.querySelector('lowOrHi');

por:

const lowOrHi = document.querySelector('.lowOrHi');

Error 3: Escritura incorrecta de addEventListener

Descripción: Los eventos de escucha estaban mal escritos como addeventListener.

Causa: Error tipográfico.

Solución: Corregir todas las instancias a:

element.addEventListener('click', callback);

Error 4: Comparación de tipos incorrecta

Descripción: La comparación entre userGuess (string) y randomNumber (número) siempre fallaba.

Causa: Falta de conversión de tipos.

Solución: Convertir userGuess a número:

let userGuess = Number(guessField.value);

Error 5: Mensajes finales invertidos

Descripción: Los mensajes para ganar o perder estaban mal implementados.

Causa: Lógica incorrecta en los condicionales.

Solución: Intercambiar los bloques correspondientes para mostrar el mensaje adecuado.

Error 6: Número de intentos incorrecto

Descripción: Los intentos estaban limitados a 5 en lugar de 10.

Causa: Valor incorrecto de la constante ATTEMPS.

Solución: Cambiar:

const ATTEMPS = 5;

por:

const ATTEMPS = 10;

Error 7: Falta de regeneración del número aleatorio al reiniciar

Descripción: El número aleatorio no se regeneraba correctamente al reiniciar el juego.

Causa: Uso incorrecto de Math.random().

Solución: Ajustar en la función resetGame:

randomNumber = Math.floor(Math.random() * 100) + 1;

Error 8: Color y mensajes no conformes

Descripción: Los colores y textos no cumplían con los requisitos.

Causa: Implementación incorrecta.

Solución: Ajustar los estilos y textos para cumplir con las especificaciones.

Conclusión

El archivo index.html fue corregido siguiendo la estrategia de testeo descrita. Ahora cumple con los requisitos funcionales y es completamente operativo. El código corregido se encuentra disponible en el repositorio de GitHub.

