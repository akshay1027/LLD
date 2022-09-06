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

  
