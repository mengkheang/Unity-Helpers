fork from [Unity-Helpers](https://github.com/mikecann/Unity-Helpers) by remove some of the stuffs I don't need like
(Enumerate Resources, ViewStateController, FPSCounter, Misc Hacks)

Unity-Helpers
=============

A set of utils and extensions for making unity development easier.

Unity is a great tool for making games however there are a few annoyances with its API that I have tried to fix with this library. 

One such annoyance is the innability to use interfaces in GetComponent(), so I wrote some extension methods to help with that:

```
using UnityHelpers;

var obj = new GameObject();
obj.AddComponent<MyComponent>();

obj.Has<MyComponent>(); // Returns true or false 
obj.HasComponentOrInterface<IMyComponent>(); // Can also handle interfaces

obj.Get<MyComponent>(); // Returns the first component
obj.GetComponentOrInterface<IMyComponent>(); // Returns the first component that implements the interface

obj.GetAll<MyComponent>(); // Gets all the components
obj.GetAllComponentsOrInterfaces<IMyComponent>(); // Gets all the components that implement the interface
```

Another utility is for adding children to GameObjects:

```
using UnityHelpers;

var obj = new GameObject();

obj.AddChild("Mike"); // Creates a new GameObject named "Mike" and adds it as a child

var player = obj.AddChild<Player>("Dave"); // Creates a new GameObject named "Dave" and adds the component "Player" returning it

obj.AddChild(typeof(Player), typeof(Friendly), typeof(AI)); // Creates a new GameObject and adds a number of components
```

There are a number of useful utils for loading assets into GameObjects too:

```
using UnityHelpers;

var obj = new GameObject();

obj.Load("Prefabs/Spaceship"); // Loads the Spaceship prefab from the Resources folder and adds it as a child
```

Most of the Utils also can be accessed via the UnityUtils.* class too rather than just extension methods:

```
using UnityHelerps;

var player = UnityUtils.Load<Player>("Prefabs/Spaceship");
```
Tests
=====

I'm using Unity build-in Unit Test with Unity 5.3.4f1. If you would like to run the tests yourself then go to _**Windows**_ → _**Editor Tests Runner**_ and run all the tests.

Usage
=====

Simply include the source in your Assets folder in your project, to use the extension methods don't forget to include the namespace:

```
using UnityHelpers;
```

License
=======

Unity-Helpers [License](https://github.com/mikecann/Unity-Helpers/blob/master/LICENSE)

The MIT License (MIT)

Copyright © 2016 Thor Mengkheang, http://mengkheang.github.io/ \<thormengkheang@gmail.com\>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
