# LLD

## OOPS
- If any task is repeated, make that task into a function and just call them everytime with different arguments.
- In constructor, self means global context of class. The self variable is a reference to the object itself, so by using it you can read and update the properties of the object.
  ```
  class Wall:
      def __init__(self, armor, height):
          self.armor = armor
          self.height = height
          
  def main():
      wall1 = Wall(10, 5)
      print(wall1.armor)  # 10
      print(wall2.height) # 5
      
  main()
  ```
  - make the model of a class inside constructor, have a seperate function to get and update them.
  - Stay away from class variables. Just like global variables, class variables make it hard to keep track of which parts of your program are making data updates.

  ### Encapsulation:
  - Hide information.
  - The caller of a function doesn't need to worry too much about what happens inside, they just need to understand the inputs and outputs.
  ```
  acceleration = calc_acceleration(initial_speed, final_speed, time)
  ```
  - Python developers prefix properties and classes that they intend to be private with a double underscore.
  ```
  class Wizard:
    def __init__(self, name):
        self.name = name
        self.__mana = 45
        self.__health = 65
        
    def get_mana(self):
        return self.__mana
    
    def get_health(self):
        return self.__health

  def main():
      merlin = Wizard("Merlin")
      madame_mim = Wizard("Madame Mim")

      print_status(merlin)
      print_status(madame_mim)

  def print_status(wizard):
      print(
          f"{wizard.name} has {wizard.__health} health and {wizard.get_mana()} mana"
      )

  main()
  ```
  - Encapsulation Does Not Make Systems More Secure. It makes it "cleaner"

  ### Abstraction:
  - The goal of abstraction is to handle complexity by hiding unnecessary details from the user.
  - The process of using the double underscore is an encapsulation method. The process of deciding which data deserves to be hidden behind the double underscore is abstraction.

  ### Inheritance:
  ![inheritance-py](https://user-images.githubusercontent.com/65683151/188714887-11067b43-f122-437e-86c2-15ba127b202f.png)
  ```
  class Animal:
    # parent "Animal" class
    def __init__(self, num_legs):
        self.num_legs = num_legs

  class Cow(Animal):
    # child class "Cow" inherits "Animal"
    def __init__(self):
        # call the parent constructor to
        # give the cow some legs
        super().__init__(4)
  ```
  
  
  ### Polymorphism:
  ![polymorphism](https://user-images.githubusercontent.com/65683151/188716117-2d91cc1d-81f4-42da-9906-ae070b60ac09.png)
  ```
  class Creature():
    def move(self):
        print("the creature moves")

  class Dragon(Creature):
      def move(self):
          print("the dragon flies")

  class Kraken(Creature):
      def move(self):
          print("the kraken swims")

  for creature in [Creature(), Dragon(), Kraken()]:
      creature.move()
  # prints:
  # the creature moves
  # the dragon flies
  # the kraken swims
  ```
  
## Abstract class decorator with eg: 
https://blog.teclado.com/python-abc-abstract-base-classes/  
```
from abc import ABC,abstractmethod 

class Animal(ABC):
    @abstractmethod  
    def do(self, action, bro): # Renamed it to "do", and it has "action" parameter
        pass

class Lion(Animal): 
    def do(self, action, time): # It's still mandatory to implement action. "time" is our other parameter
        print(f"{action} a lion! At {time}") 

class Panda(Animal): 
    def do(self, action, time): 
        print(f"{action} a panda! At {time}") 

class Snake(Animal): 
    def do(self, action, time): 
        print(f"{action} a snake! At {time}")
        
zoo = [Lion(), Panda(), Snake()]

for animal in zoo:
    animal.do(action="feeding", time="10:10 PM")
```

  
