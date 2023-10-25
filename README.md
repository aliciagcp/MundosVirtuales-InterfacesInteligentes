 # MundosVirtuales-InterfacesInteligentes
## Seminario: Mundos virtuales. Introducción a la programación de gráficos 3D.
Integrantes del grupo:
- Muhammad Campos Preira
- Alicia Guadalupe Cruz Pérez
- Gabriel Jonay Vera Estévez

Se pide responder a las siguientes cuestiones y relacionar en los casos que sea posible con los contenidos que se han explicado en la sesión de mundos virtuales:

1. **Qué funciones se pueden usar en los scripts de Unity para llevar a cabo traslaciones, rotaciones y escalados.**

En Unity, las traslaciones, rotaciones y escalados de objetos se pueden realizar mediante el uso de las funciones y propiedades proporcionadas por la clase *Transform*.

Ejemplos en cada caso:

  + Traslaciones

    - **transform.Translate(Vector3 translation)**: Esta función permite trasladar el objeto en la dirección especificada por el vector translation.
```C
transform.Translate(Vector3.forward * Time.deltaTime); // Mueve hacia adelante
```
+
    - **transform.position**: Esta propiedad te permite acceder y modificar directamente la posición del objeto en el espacio 3D.
```C
transform.position = new Vector3(1f, 0f, 0f); // Establece la posición en (1, 0, 0)
```
  + Rotaciones

    - **transform.Rotate(Vector3 eulerAngles)**: Rota el objeto según los ángulos especificados en el vector eulerAngles.
```C
transform.Rotate(Vector3.up * Time.deltaTime * 30f); // Rota alrededor del eje Y
```
+
    - **transform.rotation**: Permite acceder y modificar directamente la rotación del objeto.
```C
transform.rotation = Quaternion.Euler(0f, 90f, 0f); // Establece la rotación a 90 grados alrededor del eje Y
```
  + Escalados

    - **transform.localScale**: Permite acceder y modificar directamente la escala del objeto en cada eje (X, Y, Z).
```C
transform.localScale = new Vector3(2f, 2f, 2f); // Duplica el tamaño del objeto en todo
```

2. **Como trasladarías la cámara 2 metros en cada uno de los ejes y luego la rotas 30º alrededor del eje Y?. Rota la cámara alrededor del eje Y 30º y desplázala 2 metros en cada uno de los ejes. ¿Obtendrías el mismo resultado en ambos casos?. Justifica el resultado**

No se obtendría el mismo resultado, ya que las transformaciones no son conmutativas.
  + Escenario 1: Traslación primero, luego rotación
```C
transform.Translate(new Vector3(2f, 2f, 2f));  // Traslación (2 metros en cada eje)
transform.Rotate(new Vector3(0f, 30f, 0f));    // Rotación (30 grados alrededor del eje Y)
```
Después de esta traslación, la posición de la cámara en el espacio será (2, 2, 2) y la cámara se rotará 30 grados alrededor del eje Y desde su posición trasladada.

  + Escenario 2: Rotación primero, luego traslación
```C
transform.Rotate(new Vector3(0f, 30f, 0f));    // Rotación (30 grados alrededor del eje Y)
transform.Translate(new Vector3(2f, 2f, 2f));  // Traslación (2 metros en cada eje)
```
Después de esta rotación, la cámara se rotará 30 grados alrededor del eje Y desde su posición original en el origen (0, 0, 0) y la posición de la cámara en el espacio será (2, 2, 2), pero estará rotada 30 grados alrededor del eje Y.

3. **Sitúa la esfera de radio 1 en el campo de visión de la cámara y configura un volumen de vista que la recorte parcialmente.**
4. **Sitúa la esfera de radio 1 en el campo de visión de la cámara y configura el volumen de vista para que la deje fuera de la vista.**
5. **Como puedes aumentar el ángulo de la cámara. Qué efecto tiene disminuir el ángulo de la cámara.**

Esto se hace a través de la propiedad *fieldOfView* de la cámara. Un campo de visión más amplio permite ver más contenido en el escenario, mientras que un campo de visión más estrecho mostrará menos contenido, pero con mayor detalle.
```C
Camera.main.fieldOfView = 90f; // Establece un campo de visión de 90 grados
```

6. **Es correcta la siguiente afirmación: Para realizar la proyección al espacio 2D, en el inspector de la cámara, cambiaremos el valor de projection, asignándole el valor de orthographic**
7. **Especifica las rotaciones que se han indicado en los ejercicios previos con la utilidad quaternion.**
8. **¿Como puedes averiguar la matriz de proyección en perspectiva que se ha usado para proyectar la escena al último frame renderizado?**
9. **¿Como puedes averiguar la matriz de proyección en perspectiva ortográfica que se ha usado para proyectar la escena al último frame renderizado?**
10. **¿Cómo puedes obtener la matriz de transformación entre el sistema de coordenadas local y el mundial?**
11. **¿Cómo puedes obtener la matriz para cambiar al sistema de referencia de vista?**
```C
Camera camara = Camera.main;  
// Obtiene la matriz de cambio del sistema de referencia local al sistema de referencia de vista
Matrix4x4 matrizDeCambio = camara.worldToCameraMatrix;
Debug.Log("Matriz de Cambio al Sistema de Referencia de Vista:\n" + matrizDeCambio);
````
12. **Especifica la matriz de la proyección usado en un instante de la ejecución del ejercicio 1 de la práctica 1.**
13. **Especifica la matriz de modelo y vista de la escena del ejercicio 1 de la práctica 1.**
14. **Aplica una rotación en el start de uno de los objetos de la escena y muestra la matriz de cambio al sistema de referencias mundial.**

```C
public Vector3 rotation = new Vector3(0f, 45f, 0f);

    void Start()
    {
        transform.Rotate(rotation); // Aplica la rotación al objeto
        Matrix4x4 matrix = Matrix4x4.TRS(transform.position, transform.rotation, transform.localScale);
        Debug.Log("Matriz de Rotación al Sistema Mundial:\n" + matrix);
    }
```

15. **¿Como puedes calcular las coordenadas del sistema de referencia de un objeto con las siguientes propiedades del Transform:?: 
Position (3, 1, 1), Rotation (45, 0, 45)**
```C
Vector3 coordenadasSistemaDeReferencia = transform.rotation * transform.position;
```
