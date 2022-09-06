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
