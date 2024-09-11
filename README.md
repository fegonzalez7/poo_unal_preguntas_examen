# poo_unal_preguntas_examen
Repo de banco de preguntas para poo en python

## Formato:
Cuáles son las 4 caracteristicas de OOP?
<details><summary>Respuesta</summary>
<p>
  Abstacción, herencia, polimosfismo, encapsulamiento.
</p>
</details>

Qué es instanciar?

<details><summary>Respuesta</summary>
<p>
  Es crear un objeto único a partir de una clase
</p>
</details>

Qué es la abstracción?

<details><summary>Respuesta</summary>
<p>
  Es destacar las características principales de un objeto 
</p>
</details>

Cúal es el objetivo de la herencia?

<details><summary>Respuesta</summary>
<p>
   
  * Extensibilidad del código
  * Ahorrar código 
  * Abstracción
</p>
</details>

Qué es un mixin?

<details><summary>Respuesta</summary>
<p>
  Es una clase que no es instanciada, y se usa para dar funcionalidades 
</p>
</details>

¿Cúal es la relación de palabras de la herencia?

<details><summary>Respuesta</summary>
<p>
  " Es un " 
</p>
</details>

¿Cúal es la relación de palabras de la Composición?

<details><summary>Respuesta</summary>
<p>
  " Tiene un " 
</p>
</details>

¿Cúal es la diferencia entre Herencia y Composición?

<details><summary>Respuesta</summary>
<p>
  
  * La herencia crea una relación jerárquica entre clases 
  * La Composición permite que una clase tenga a otra como parte de sus estados (atributos)
</p>
</details>

Cuál es el propósito de `self` en una clase de Python?
<details><summary>Respuesta</summary>
<p>
  Permite a un objeto referenciar sus propios atributos y métodos desde dentro de la clase.
</p>
</details>

## Preguntas añadidas

¿Cuáles son las etapas para realizar un proyecto orientado a objetos?
  
<details><summary>Respuesta</summary>
<p>
  Análisis (el 'qué', qué se debe hacer), diseño (el 'cómo', cómo se puede resolver usando objetos), implementación (el 'dónde', dónde se podría implementar).
</p>
</details>

<br>

¿Qué es un objeto?

<details><summary>Respuesta</summary>
<p>
  Una colección de datos (atributos) y comportamientos (métodos) asociados.
</p>
</details>

<br>

¿Qué es una clase?

<details><summary>Respuesta</summary>
<p>
  Una plantilla para crear objetos que describe sus comportamientos y atributos esenciales.
</p>
</details>

<br>

En el siguiente fragmento de código, ¿qué conceptos de POO se evidencian?

```python
class Vehicle():
  def start():
    raise NotImplementedError('Subclass must implement abstract method')

class Car(Vehicle):
  def start():
    print('Car starting')

class Plane(Vehicle):
  def start():
    print('Plane starting')
```

<details><summary>Respuesta</summary>
<p>
  Herencia (heredando de <code>Vehicle</code>), abstracción (definiendo a <code>Vehicle</code> como la clase de ciertos objetos que podrán prenderse) y polimorfismo (redefiniendo el método abstracto <code>start()</code> en clases hijas).
</p>
</details>

<br>

¿Qué es el encapsulamiento?

<details><summary>Respuesta</summary>
<p>
  Es el principio que aboga por la protección (u ocultación) de información y métodos de una clase, restringiendo el acceso a cualquier objeto de esta mediante una interfaz pública.
</p>
</details>

<br>

¿Cómo se implementa el encapsulamiento en Python?

<details><summary>Respuesta</summary>
<p>
  Mediante la definición de getters y setters para los atributos privados de una clase, y usando la convención de nombres con uno o dos guiones bajos para indicar que un atributo o método es protegido o privado, respectivamente.
</p>
</details>

<br>

¿En Python hay atributos realmente privados o protegidos?

<details><summary>Respuesta</summary>
<p>
  No. Python no le cambiará nada a un atributo que tiene un único guión bajo al inicio de su identificador (es solo una convención), y a los que tienen un dunder (``__``) al inicio, Python les cambia el nombre usando <i>name mangling</i> pero aún así se pueden acceder desde fuera de la clase refiriéndose a estos como <code>objeto._Clase__atributo</code>.
</p>
</details>

<br>

¿Cómo se le llama al método ``__init__`` de una clase?

<details><summary>Respuesta</summary>
<p>
  Constructor.
</p>
</details>

<br>

¿Cuál es el problema del diamante? ¿Cómo lo maneja Python?

<details><summary>Respuesta</summary>
<p>
  El problema del diamante surge cuando se utiliza herencia múltiple, es decir, cuando una clase hereda de dos o más clases. Si alguna de estas clases tiene un método con el mismo nombre (como ocurriría si se utiliza polimorfismo), Python no sabría a qué método de qué clase llamar, pues están en el mismo nivel de jerarquía. Sin embargo, para esto Python utiliza el MRO (Method Resolution Order), que es un algoritmo que determina el orden en que se buscarán los métodos en las clases padre. Este funciona recorriendo cada nivel de jerarquía de izquierda a derecha antes de subir al siguiente nivel.
</p>
</details>

<br>

¿El polimorfismo requiere necesariamente herencia?

<details><summary>Respuesta</summary>
<p>
  No. Se puede lograr implementando métodos con el mismo nombre y funcionalidades diferentes. Usualmente va de la mano con el <i>Duck Typing</i> Por ejemplo,
    
  ```python
    class Dog:
      def speak(self):
        return "Woof!"

    class Cat:
      def speak(self):
        return "Meow!"

    class Bird:
      def speak(self):
        return "Tweet!"

    def make_animal_speak(animal):
    print(animal.speak())

    dog = Dog()
    cat = Cat()
    bird = Bird()

    make_animal_speak(dog)
    make_animal_speak(cat) 
    make_animal_speak(bird)
  ```

</p>
</details>

<br>

¿Qué es el Duck Typing?

<details><summary>Respuesta</summary>

<p>
  Es un estilo de programación que se basa en la idea de que algo es lo que hace, es decir, si algo se mueve como un pato, come como un pato, y duerme como un pato, es un pato. Puede que sea un perro o un gato, pero si cumple con las características de un pato, se le considera un pato. En Python, esto se traduce en que no importa si un objeto es de una clase específica, sino que importa si tiene los métodos y atributos necesarios para realizar una tarea (ver el ejemplo de la pregunta anterior). Ejemplo,

  ```python
  class AudioFile:
    def __init__(self, filename):
      self.filename = filename

  class MP3File(AudioFile):
    def play(self):
      print(f"playing {self.filename} as mp3")

  class WavFile(AudioFile):
    def play(self):
      print(f"playing {self.filename} as wav")

  class OggFile(AudioFile):
    def play(self):
      print(f"playing {self.filename} as ogg")

  def play_media(player):
    player.play()

  mp3_player = MP3File()
  ogg_player = OggFile()
  wav_player = WavFile()

  play_media(mp3_player)  
  play_media(ogg_player)
  play_media(wav_player)
  ```

  En este ejemplo, se reproducirá un archivo, sin importar si es de audio o de video y qué tipo de cada uno. Como todos se pueden reproducir (tienen el método `play()`), se les considera reproducibles.

</p>
</details>

<br>

Cuále es la diferencia entre atributos de clase y atributos de instancia?
<details><summary>Respuesta</summary>
<p>
  los atributos de clase estan asociados a la clase y no a una instancia en particular por lo que este atributo sera compartido por toda instancia de esta clase mientras que los atributos de instancia pertenecen a cada objeto unico por lo tanto cada uno tendra su propio valor
</p>
</details>

¿ Cual es la diferencia entre una clase y una interface?

<details><summary>Respuesta</summary>

<p>
Una interface solo consiste de metodos sin ninguna implementacion ejecutable. Y
sus funcionalidades requieridas deben ser implementadas por la clase que la herede.
</p>
</details>
 


¿ Cual es la finalidad de definir setter y getters en una clase?

<details><summary>Respuesta</summary>

<p>
Estos se encargan de modificar y controlar atributos privados de una clase
</p>
</details>
 
¿ Cual es la diferencia entre un mixin y una interface?

<details><summary>Respuesta</summary>

<p>
Los Mixins puede heredar metodos abstractos o concretos, y por el otro lado,
las interfaces unicamente heredan metodos abstractos
</p>
</details>
 
