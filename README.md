| Contents |
| ----- |
| [About](#About) |
| [Installation](#Installation) |
| [Containers](#Containers) |

About
======
GUI is a multifunctional graphics library, especially designed and optimized for low-performance computers. You can realize all of your most perverted fantasies using it: from habitual buttons, sliders and charts to complex animated interfaces. Extreme performance of the library is achieved through the use of double buffering and complex color grouping and processing algorithms.

For example, my operating system, IDE and 3D application are fully implemented by the methods of this library:

![Imgur](https://i.imgur.com/Ki5bX0I.gif)

![Imgur](http://i.imgur.com/tHAiTmF.gif)

Let the abundance of text below not frighten you: this documentation has many illustrated examples with full working code.

Installation
======

Below is a table of dependencies that are necessary for this library. You can use following links to download dependencies manually or run an automatic [installer](https://pastebin.com/ryhyXUKZ) that downloads all the necessary files for you:

    pastebin run ryhyXUKZ

| Библиотека | Функционал | Документация |
| ------ | ------ | ------ |
| *[GUI](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/GUI.lua)* | This library | - | 
| *[advancedLua](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/advancedLua.lua)* | Addition to standard Lua libraries with a variety of functions: fast table serialization, text wrapping, binary data processing, etc. | [https://github.com/Igor...](https://github.com/IgorTimofeev/OpenComputers/blob/master/Documentation/advancedLua.md) | 
| *[color](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/color.lua)* | Extrusion and packaging of color channels, conversion of the RGB color model to HSB and vice versa, the implementation of alpha blending, the generation of color transitions and the conversion of color into an 8-bit format for the OpenComputers palette | [https://github.com/Igor...](https://github.com/IgorTimofeev/OpenComputers/blob/master/Documentation/color.md) | 
| *[doubleBuffering](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/doubleBuffering.lua)* | Double buffering of the graphic context and various methods of primitives rasterizing | [https://github.com/Igor...](https://github.com/IgorTimofeev/OpenComputers/blob/master/Documentation/doubleBuffering.md) | 
| *[image](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/image.lua)* | Implementation of the image standard for OpenComputers and basic methods of their processing: transpose, crop, rotate, reflection, etc. | - | 
| *[OCIF](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/FormatModules/OCIF.lua)* | The OpenComputers Image Format module for the image library, written with regard to the features of the mod and realizing effective compression of pixel data | - | 

Containers
======

The library is divided into two main concepts: containers and widgets. Containers is intended for grouping widgets, processing their positions and handle their events. With widgets, the user interacts directly: they can be buttons, scrollbars, sliders, etc. But first let's talk about containers:

GUI.**container**( x, y, width, height ): *table* container
-----------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Container's coordinate by x-axis |
| *int* | y | Container's coordinate by y-axis |
| *int* | width | Container's width |
| *int* | height | Container's height |

Each container is a grouper for other objects, its behavior is very similar to a folder that contains a few of nested files and other folders. To create a container fit by screen size, use the GUI.**fullScreenContainer**().

All container child objects are stored in container.**children** table. To add an object to the container, use the following method:

```lua
container:addChild(<Object>)
```

After adding an object to the container, it will have two positions: the first one is local, it is used to position objects inside the containers. Most of the time the user interacts with local coordinates:

```lua
object.localX = 2
object.localY = 4
```

The second position is global (screen). It allows you to get the current coordinate of the object on the screen and perform some drawing operations. These coordinates are **read-only** and they are calculated automatically:

```lua
object.x = 10
object.y = 20
```

After adding an object to the container, its global and local coordinates will be equivalent. The system of hierarchy and positioning container's children is presented in the following image:

![Imgur](https://i.imgur.com/GJmDQ2j.png)

Containers also have an important feature: any child that extends beyond the bounds of the container will be rendered only within the size of this container:

![Imgur](https://i.imgur.com/SBuL1it.png)

Of course, you can add to container some other containers, and add a new ones to the added ones, creating complex hierarchical chains and grouping the child objects at your discretion.

Finally, the most important feature of containers is the automated event processing. For example, it allows buttons to be pressed when user interacts with screen and it allows text input fields receive data from the keyboard.

Each container can start processing events, after which it becomes "main". To do it, To do this, use the following:

```lua
container:startEventHandling([delay])
```

If event processing should be terminated, use the following:
```lua
container:stopEventHandling()
```

Once the "main" container sees the event, it recursively analyzes itself and all child objects for the .**eventHandler** function. If the child object has this function, then it runs with the following parameters:

```lua
function(mainContainer, object, ...eventData)
    ...
end
```

The first parameter is a pointer to the table of the "main" container, the second is a pointer to the table of the child object of the event in question, and the rest is the set of event parameters just like computer.**pullSignal**() do. For example, the "touch" event will generate 6 parameters:

| Parameter | Description |
| ------ | ------ |
| "touch" | Event type |
| "7842f8-..." | Screen address |
| 13 | Screen x |
| 21 | Screen y |
| 0 | Mouse button |
| "ECS" | Username |

The key detail of the event handler is that if the event is a "**screen**" (touch, drag, drop, scroll), then the child object event handler will be called only for this object, and event processing for the remaining unprocessed child objects will be finished.

If the event does not belong to the screen, or the object **does not have** event handler method, the processing of the remaining child elements will continue as always.

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**children** | Table that contains all child objects of this container | 
| *function* | :**addChild**(*table* child, [*int* atIndex]): *table* child| Add specified object to the container as a child. When you do this, the object's global coordinates will become local. If the optional parameter **atIndex** is specified, then the element will be added to the corresponding position in container.**children** table |
| *function* | :**deleteChildren**([*int* fromIndex, *int* toIndex]): *table* container | Delete all child elements of the container. If the optional parameters of the element indices are specified, the deletion will be performed in the appropriate range |
| *function* | :**startEventHandling**([*float* delay]): *table* container | Run the event processing for this container and analyse events for all it's child objects. The  **delay** parameter is similar to computer.**pullSignal** one |
| *function* | :**stopEventHandling**(): *table* container | Stop processing events for this container |
| *function* | :**draw**() | Recursively renders the contents of the container in the order of the queue of its children. I draw your attention to the fact that this method only draws data into the screen buffer. To display changes on the screen, you must use the doubleBuffering.**draw** () method or use method below |
| *function* | :**drawOnScreen**([*boolean* force]) | This method is similar to :**draw**() with the only difference that after drawing data  into the screen buffer, it will automatically display changes on the screen. That is, in fact, it exists solely for the convenience of writing code |

Below is a classic example of the implementation of the container:

```lua
-- Import the library
local GUI = require("GUI")

--------------------------------------------------------------------------------

-- Create container fitted to screen resolution
local mainContainer = GUI.fullScreenContainer()
-- Create and add second container to main container
local anotherContainer = mainContainer:addChild(GUI.container(3, 2, 50, 25))
-- Create simple event handler to it
anotherContainer.eventHandler = function(mainContainer, object, ...)
    print("It works! The event data was: ", ...)
end

--------------------------------------------------------------------------------

-- Start processing event for main container
mainContainer:startEventHandling()
```

As a result, you will get an amusing output of event data to the terminal:

![](https://i.imgur.com/6xpX9L9.gif)

