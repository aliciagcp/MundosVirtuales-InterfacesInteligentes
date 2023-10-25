# MundosVirtuales-InterfacesInteligentes
## Seminario: Mundos virtuales. Introducción a la programación de gráficos 3D.
Integrantes del grupo:
- Muhammad Campos Preira
- Alicia Guadalupe Cruz Pérez
- Gabriel Jonay Vera Estévez

Se pide responder a las siguientes cuestiones y relacionar en los casos que sea posible con los contenidos que se han explicado en la sesión de mundos virtuales:

1. **Qué funciones se pueden usar en los scripts de Unity para llevar a cabo traslaciones, rotaciones y escalados.**
2. **Como trasladarías la cámara 2 metros en cada uno de los ejes y luego la rotas 30º alrededor del eje Y?. Rota la cámara alrededor del eje Y 30ª y desplázala 2 metros en cada uno de los ejes. ¿Obtendrías el mismo resultado en ambos casos?. Justifica el resultado**
No se obtendría el mismo resultado, ya que las transformaciones no son conmutativas.

Escenario 1: Traslación primero, luego rotación
```C
transform.Translate(new Vector3(2f, 2f, 2f));
```
4. **Sitúa la esfera de radio 1 en el campo de visión de la cámara y configura un volumen de vista que la recorte parcialmente.**
5. **Sitúa la esfera de radio 1 en el campo de visión de la cámara y configura el volumen de vista para que la deje fuera de la vista.**
6. **Como puedes aumentar el ángulo de la cámara. Qué efecto tiene disminuir el ángulo de la cámara.**
7. **Es correcta la siguiente afirmación: Para realizar la proyección al espacio 2D, en el inspector de la cámara, cambiaremos el valor de projection, asignándole el valor de orthographic**
8. **Especifica las rotaciones que se han indicado en los ejercicios previos con la utilidad quaternion.**
9. **¿Como puedes averiguar la matriz de proyección en perspectiva que se ha usado para proyectar la escena al último frame renderizado?.**
10. **¿Como puedes averiguar la matriz de proyección en perspectiva ortográfica que se ha usado para proyectar la escena al último frame renderizado?.**
11. **¿Cómo puedes obtener la matriz de transformación entre el sistema de coordenadas local y el mundial?.**
12. **Cómo puedes obtener la matriz para cambiar al sistema de referencia de vista**
13. **Especifica la matriz de la proyección usado en un instante de la ejecución del ejercicio 1 de la práctica 1.**
14. **Especifica la matriz de modelo y vista de la escena del ejercicio 1 de la práctica 1.**
15. **Aplica una rotación en el start de uno de los objetos de la escena y muestra la matriz de cambio al sistema de referencias mundial.**
16. **¿Como puedes calcular las coordenadas del sistema de referencia de un objeto con las siguientes propiedades del Transform:?: 
Position (3, 1, 1), Rotation (45, 0, 45)**
