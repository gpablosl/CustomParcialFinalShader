# Documentación
Contenido de shader: Modelo de luz personalizado basado en Lambert, mapa de textura y mapa de normales, Rim light, Phong y un efecto Banded.

Este shader se realizó utilizando HLSL, el cual es un lenguaje de sombreado desarrollado por Microsoft para su uso con la interfaz de programación de aplicaciones Direct3D. Además, el shader es un modelo personalizado basado en Lambert.

El shader cuenta con varias cosas, entre ellas se encuentra un albedo color, que tiene la capacidad de cambiar el color del material, una textura principal, y un mapa de normales, para que el material no solo tenga una textura plana, si no que tenga más profundidad. La textura se consiguió por medio de una imagen de internet, mientras que el mapa de normales se consiguió utilizando una herramienta llamada CrazyBump. Utilizando esta herramienta, lo que se hizo fue tomar la imagen de la textura y el programa mapeo las normales, y solo se le movieron algunas características al mapa, como los detalles y el sharpen. A este mapa de normales se le puede modificar la intensidad con Normal strength.

Además de las texturas, el shader tiene luz Phong, de la cual se puede modificar el color especular (\_SpecularColor, \_SpecularPower, \_SpecularGloss). Este efecto hace un punto brillante o reflejo de luz. Se calcula la direccion de la luz, y se saca el producto punto de esto con la normal. Toma una segunda dirección y de aquí sale el reflejo, que se obtiene a partir de invertir la dirección de la luz.

Para mejorar el shader, a este se le añadió una luz de anillo en las orillas, mejor conocido como rim lighting, a esta se le puede personalizar la intensidad y el color, además, esta depende principalmente de la posición de la cámara a diferencia de las demás propiedades que solo dependen de la posición de la luz en sí, ya que el rim light se mueve junto con la cámara (siempre y cuando haya luz para empezar).

La última cosa que contiene el shader, es el Banded steps, la cual es una iluminación de anillos, se puede subdividir progresivamente del blanco al negro. Toda la luz que recibe está basada en Lambert, regresa NdotL, y funciona con 256 steps, para poder controlar el número de anillos y su tamaño.
