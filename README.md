# Core Update Manager

An optimized, garbage-free Update Manager for Unity with custom execution order that works with Arrays.  
First used for Grand Dad Mania Revived (https://pechka-productions.itch.io/grand-dad-mania). If you're asking "why" then read this: https://blogs.unity3d.com/2015/12/23/1k-update-calls/

Long story short: having magic methods called from Unity has an overhead and thus, if you wish to gain performance or get more freedom/features at the expense of being a little more careful and using a little bit more memory, you can write your own Update Manager which will be the only thing that receives the magic Update method and distributes it across all the other objects. In Grand Dad Mania Revived we managed to save 0.5ms on average on Xiaomi Mi5S Plus.

While Unity is doubling-down on their Entity Component System paradigm, the usual MonoBehaviour approach is not going away, so this project will most definitely be useful for you. The Update Manager will be faster than Unity's marshalled calls in pretty much any project.

# How to use
  -Use CoreMonoBeh instead of MonoBehaviour  
  -Override the CoreInitSetup() method and generate a LoopUpdateSettings struct inside it with settings for your loops  
  -Use override functions that start with Core instead of Unity's marshalled calls (for example CoreAwake instead of Awake)  

Read ```DOCUMENTATION.md``` for details.

Please read the ```LICENSE```.
