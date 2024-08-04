# poo_unal_preguntas_examen
Repo de banco de preguntas para poo en python

## Formato:
Cuáles son las 4 caracteristicas de OOP?
<details><summary>Respuesta</summary>
<p>
  Abstacción, herencia, polimosfismo, encapsulamiento.
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



