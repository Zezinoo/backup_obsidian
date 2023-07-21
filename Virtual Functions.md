When you create a [[classes]], you might want to create methods that are shared by different instances, but behave differently when called by subclasses of the class. Then, we would have to override such methods on the subclass definition.
```cpp
class Entity{
   virtual std::string getName(){return "Entity"}
   
}

class Player : public Entity{
 std::string m_Name;
 
 Player(const std::string& name){
      M_name = name;};
std::string getName(){return m_Name}
    
}
int main(){
  Entity* e = new Entity();
  Player* p = new Player("player");
  LOG(p->getName());//player
  LOG(e->getName());// Entity
}
```
Had we not declalared the function as virtual, it would always print Entity as the output. One could also use the override keyword to explicitly override a function in a subclass, in newer versions.
