plan de ataque test-strategy.md
 Objetivo
Solucionar los errores presentes en el archivo `index.html` del proyecto "Juego Adivina tu número" para garantizar que cumpla con la lógica de negocio establecida. Documentar los errores encontrados y las soluciones aplicadas.

Estrategia de Testeo

1. Preparación del entorno de pruebas:**
   - Clonar el repositorio forkeado desde GitHub en el equipo local.
   - Abrir el archivo `index.html` en el navegador.
   - Abrir la consola del navegador para monitorear errores.

2. Identificación de errores:
   - Revisar los mensajes de error en la consola del navegador.
   - Probar la funcionalidad del juego con diferentes entradas, incluyendo:
     - Números válidos dentro del rango (1 a 100).
     - Números fuera del rango.
     - Entradas no numéricas (letras, caracteres especiales).

3. Documentación de errores:
   - Registrar cada error identificado con una breve descripción y su causa probable.

4. Corrección de errores:
   - Modificar el archivo `index.html` para solucionar los problemas.
   - Verificar los cambios en el navegador.

5. Pruebas de regresión:
   - Repetir las pruebas para asegurar que el archivo cumple con todos los requisitos funcionales y no se introdujeron nuevos errores.

6. Entrega final:
   - Subir el archivo `index.html` corregido al repositorio.
   - Documentar el plan de ataque y los errores encontrados en el archivo `test-strategy.md`.

Errores Encontrados y Soluciones
Error 1: Generación incorrecta del número aleatorio
- El número aleatorio generado no era entero y estaba fuera del rango especificado (1 a 100).
- Uso incorrecto de `Math.random()` sin escalado y redondeo.
- Solución:** Reemplazar la línea:
  javascript
  let randomNumber = Math.random() * 10;
  
  por:
  javascript
  let randomNumber = Math.floor(Math.random() * 100) + 1;
  

Error 2: Selector de clase mal definido
- Descripción:** El selector para el elemento `lowOrHi` no incluía el punto (`.`) necesario para seleccionar una clase.
- Causa:** Error en el uso de `querySelector`.
- Solución:** Reemplazar:
  javascript
  const lowOrHi = document.querySelector('lowOrHi');
  
  por:
  javascript
  const lowOrHi = document.querySelector('.lowOrHi');
  

Error 3: Escritura incorrecta de `addEventListener`
- Los eventos de escucha estaban mal escritos como `addeventListener`.
- Error tipográfico.
- Corregir todas las instancias a:
  javascript
  element.addEventListener('click', callback);
  

Error 4: Comparación de tipos incorrecta
- La comparación entre `userGuess` (string) y `randomNumber` (número) siempre fallaba.
- Falta de conversión de tipos.
- Convertir `userGuess` a número:
  javascript  let userGuess = Number(guessField.value);
  

Error 5: Mensajes finales invertidos
- Los mensajes para ganar o perder estaban mal implementados.
-  Lógica incorrecta en los condicionales.
- Intercambiar los bloques correspondientes para mostrar el mensaje adecuado.

Error 6: Número de intentos incorrecto
- Los intentos estaban limitados a 5 en lugar de 10.
- Valor incorrecto de la constante `ATTEMPS`.
- Cambiar:
  javascript
  const ATTEMPS = 5;
  
  por:
  javascript
  const ATTEMPS = 10;
  

Error 7: Falta de regeneración del número aleatorio al reiniciar
- El número aleatorio no se regeneraba correctamente al reiniciar el juego.
- Uso incorrecto de `Math.random()`.
- Ajustar en la función `resetGame`:
  javascript
  randomNumber = Math.floor(Math.random() * 100) + 1;
  

Error 8: Color y mensajes no conformes
- Los colores y textos no cumplían con los requisitos.
- Implementación incorrecta.
- Ajustar los estilos y textos para cumplir con las especificaciones.

Conclusión
El archivo `index.html` fue corregido siguiendo la estrategia de testeo descrita. Ahora cumple con los requisitos funcionales y es completamente operativo. El código corregido se encuentra disponible en el repositorio de GitHub.

