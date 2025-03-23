1. create_output_directory()

Propósito: Crea un directorio llamado output en el directorio actual si no existe.

2. create_density_plot(points, colors, indices, slice_axis, min_bound, max_bound, shifts, filename)
Propósito: Genera una visualización de densidad de puntos en un espacio tridimensional (proyectado en 2D) y guarda la imagen resultante como un archivo PNG.

Detalle técnico:

Filtrado de puntos:

Aplica desplazamientos (shifts) a los puntos originales (points) y selecciona solo aquellos indicados por indices.

Convierte las coordenadas tridimensionales en coordenadas bidimensionales (basadas en el eje slice_axis).

Creación de un grid de densidad:

Calcula un mapa de densidad (density_grid) basado en cuántos puntos caen dentro de cada celda del grid 2D.

Normaliza las coordenadas a valores discretos en el rango del grid.

Suavizado:

Aplica un filtro gaussiano con OpenCV (cv2.GaussianBlur) para suavizar la distribución de densidad.

Normalización de densidad:

Los valores del grid se escalan al rango [1, 255], donde 1 es el valor mínimo no cero.

Las áreas sin datos permanecen en 0.

Guardado de la imagen:

Se guarda la imagen generada como un archivo PNG redimensionado al tamaño deseado.

Retorno:

Devuelve la imagen de densidad cargada en escala de grises.
