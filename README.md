# course_completion-analysis
Course Completion Analysis: Paradoja de Simpson en Finalización de Cursos
🎯 Objetivo del proyecto

Este notebook analiza datos de finalización de cursos en una plataforma de educación online, donde cada fila representa a un estudiante que tomó un curso en uno de dos formatos posibles: A o B.

¿Qué formato de curso parece más efectivo para que los estudiantes completen el curso?

Al igual que en el análisis de clinical_trial_analysis, el objetivo del ejercicio no es solo responder esa pregunta, sino demostrar cómo una conclusión basada en el promedio global puede ser incompleta o directamente engañosa, y cómo segmentar por una variable relevante del estudiante —en este caso, su nivel de experiencia— puede revelar un patrón distinto (y más confiable) al que sugiere el dato global. Este fenómeno es otro caso de paradoja de Simpson.

📂 Dataset utilizado
course_completion.csv → Datos de estudiantes de una plataforma de educación online, con las columnas:
nivel_experiencia — Nivel de experiencia del estudiante (Beginner / Advanced).
formato_curso — Formato del curso tomado (A o B).
completo_curso — Indica si el estudiante completó el curso (variable binaria).
🔄 Etapas del análisis realizadas
Cálculo de la tasa de finalización global por formato de curso: se agrupan los datos únicamente por formato_curso y se calcula el promedio de completo_curso, obteniendo una primera conclusión (aparente): el formato A tiene una tasa de finalización superior al B (~78.3% vs ~71.9%).
Segmentación por nivel de experiencia: se repite el cálculo, pero agrupando ahora por nivel_experiencia y formato_curso en conjunto. Al segmentar, el resultado se invierte por completo: el formato B resulta más efectivo tanto para estudiantes Advanced como para Beginner, contradiciendo la conclusión inicial basada solo en el promedio global.
🔍 Principal hallazgo
La conclusión inicial ("el formato A es más efectivo") es incompleta y engañosa. Al segmentar por nivel de experiencia, el formato B es consistentemente mejor en ambos subgrupos:
Estudiantes Advanced: formato B alcanza 100% de finalización vs 90.6% del formato A.
Estudiantes Beginner: formato B alcanza 66.8% de finalización vs 41.7% del formato A.
Este es un caso claro de paradoja de Simpson: el promedio global "mezcla" subgrupos con tasas de finalización distintas en proporciones distintas entre los dos formatos, produciendo una conclusión que no se sostiene al analizar los datos de forma segmentada.
Recomendación: antes de decidir qué formato de curso escalar o priorizar, es indispensable segmentar por variables relevantes del estudiante (como nivel de experiencia) en vez de confiar únicamente en el promedio general, ya que este puede ocultar el patrón real y llevar a una decisión contraria a la más efectiva.
▶️ Cómo ejecutar el notebook

Puedes abrir y correr este análisis directamente en Google Colab, sin instalar nada en tu computador:

Entra a Google Colab.
Ve a Archivo > Abrir notebook > GitHub.
Pega la URL de este repositorio.
Selecciona el archivo course_completion_analysis.ipynb de la lista que aparece.
El notebook se abrirá listo para ejecutar.

💡 Alternativa rápida: si el repositorio es público, puedes pegar directamente esta estructura de URL en tu navegador: https://colab.research.google.com/github/<usuario>/<repositorio>/blob/main/course_completion_analysis.ipynb

🔁 Guía de reproducción
Ejecuta todas las celdas en orden, usando Entorno de ejecución > Reiniciar y ejecutar todo. El notebook sigue una secuencia simple: cálculo global → segmentación por nivel de experiencia → comparación de resultados.
La carga del dataset está incluida en las celdas de código (/content/course_completion.csv) — no necesitas subir el archivo manualmente antes de empezar, siempre que lo hayas cargado en la carpeta /content de tu entorno de Colab (o ajustes la ruta si usas otro entorno).
No se requieren pasos manuales adicionales — el notebook es corto y cada celda vuelve a cargar el dataset de forma independiente, por lo que las celdas pueden ejecutarse en orden sin depender de variables intermedias complejas.

⚠️ Si al ejecutar alguna celda aparece un error de tipo FileNotFoundError, verifica que el archivo course_completion.csv esté efectivamente subido a la carpeta /content de tu sesión de Colab (los archivos subidos a Colab se eliminan al cerrar la sesión, por lo que hay que volver a subirlos cada vez que se reinicia el entorno).

🔗 Repositorio

Link al repositorio público del proyecto:
