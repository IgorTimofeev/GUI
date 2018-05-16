About
======
GUI is a multifunctional graphics library, especially designed and optimized for low-performance computers. You can realize all of your most perverted fantasies using it: from habitual buttons, sliders and charts to complex animated interfaces. Extreme performance of the library is achieved by using double buffering and complex color grouping and processing algorithms.

For example, my OS, IDE and 3D-application are fully implemented by the methods of this library:

![Imgur](https://i.imgur.com/Ki5bX0I.gif)

![Imgur](http://i.imgur.com/tHAiTmF.gif)

Let the abundance of text below not frighten you: this documentation has many illustrated examples with full working code.

| Contents |
| ----- |
| [Installation](#installation) |
| [Containers](#containers) |
| [Objects](#objects) |
| [Ready-to-use widgets](#ready-to-use-widgets) |
| [    GUI.panel](#guipanel-x-y-width-height-color-transparency--table-panel) |
| [    GUI.text](#guitext-x-y-textcolor-text--table-text) |
| [    GUI.label](#guilabel-x-y-width-height-textcolor-text--table-label) |
| [    GUI.image](#guiimage-x-y-loadedimage--table-image) |
| [    GUI.button](#guibutton-x-y-width-height-buttoncolor-textcolor-buttonpressedcolor-textpressedcolor-text--table-button) |
| [    GUI.actionButtons](#guiactionbuttons-x-y-fat--table-actionbuttons) |
| [    GUI.input](#guiinput-x-y-width-height-backgroundcolor-textcolor-placeholdertextcolor-backgroundfocusedcolor-textfocusedcolor-text-placeholdertext-erasetextonfocus-textmask--table-input) |
| [Standalone methods](#objects) |

Installation
======

Below is a table of dependencies that are necessary for this library. You can use following links to download dependencies manually or run an automatic [installer](https://pastebin.com/ryhyXUKZ) that downloads all the necessary files for you:

    pastebin run ryhyXUKZ

| Dependency | Description | Documentation |
| ------ | ------ | ------ |
| *[GUI](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/GUI.lua)* | This library | - | 
| *[advancedLua](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/advancedLua.lua)* | Addition to standard Lua libraries with a variety of functions: fast table serialization, text wrapping, binary data processing, etc. | [https://github.com/Igor...](https://github.com/IgorTimofeev/OpenComputers/blob/master/Documentation/advancedLua.md) | 
| *[color](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/color.lua)* | Extrusion and packaging of color channels, conversion of the RGB color model to HSB and vice versa, the implementation of alpha blending, the generation of color transitions and the conversion of color into an 8-bit format for the OpenComputers palette | [https://github.com/Igor...](https://github.com/IgorTimofeev/OpenComputers/blob/master/Documentation/color.md) | 
| *[doubleBuffering](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/doubleBuffering.lua)* | Double buffering of the graphic context and various methods of primitives rasterizing | [https://github.com/Igor...](https://github.com/IgorTimofeev/OpenComputers/blob/master/Documentation/doubleBuffering.md) | 
| *[image](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/image.lua)* | Implementation of the image standard for OpenComputers and basic methods of their processing: transpose, crop, rotate, reflection, etc. | - | 
| *[OCIF](https://github.com/IgorTimofeev/OpenComputers/blob/master/lib/FormatModules/OCIF.lua)* | The OpenComputers Image Format module for the image library, written with regard to the features of the mod and realizing effective compression of pixel data | - | 

Containers
======

The library is divided into two main concepts: containers and widgets. Containers is intended for grouping widgets, processing their positions and handle their events. With widgets the user interacts directly: they can be buttons, scrollbars, sliders, etc. But first let's talk about containers:

GUI.**container**( x, y, width, height ): *table* container
-----------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Container's coordinate by x-axis |
| *int* | y | Container's coordinate by y-axis |
| *int* | width | Container's width |
| *int* | height | Container's height |

Each container is a grouper for other objects, its behavior is very similar to a folder that contains a few of nested files and other folders. To create a container fit by screen size, use this:

```lua
GUI.fullScreenContainer()
```

All container child objects are stored in container.**children** table. To add an object to the container, use the following method:

```lua
container:addChild(<Object>)
```

After adding an object to the container, it will have two positions: the first one is local, it is used to position objects inside the containers:

```lua
object.localX = 2
object.localY = 4
```

The second position is global (screen). It allows you to get the current coordinate of the object on the screen and perform some drawing operations. These coordinates are **read-only** and they are calculated automatically, so most of the time the user interacts with local coordinates:

```lua
object.x = 10
object.y = 20
```

After adding an object to the container, its global and local coordinates will be equivalent. The system of hierarchy and positioning container's children is well presented in the following image:

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
| "7842f8..." | Screen address |
| 13 | Screen x |
| 21 | Screen y |
| 0 | Mouse button |
| "ECS" | Username |

The key detail of the event handler is that if the event is a "**screen**" (touch, drag, drop, scroll), then the child object event handler will be called only for this object, and event processing for the remaining unprocessed child objects will be finished.

If the event does not belong to the screen, or the object **does not have** event handler method, the processing of the remaining child elements will continue as always. You can see the logic and the order of event processing in the following image:

![](https://i.imgur.com/9RiUKtl.png)

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
-- Create simple event handler for it
anotherContainer.eventHandler = function(mainContainer, object, ...)
    print("It works! The event data was: ", ...)
end

--------------------------------------------------------------------------------

-- Start processing events for main container
mainContainer:startEventHandling()
```

As a result, you will get an amusing output of event data to the terminal:

![](https://i.imgur.com/6xpX9L9.gif)

Objects
======

After understanding the concept of containers, you can easily start adding your widgets to the created container. Each widget is the inherited object of GUI.**object**

GUI.**object**( x, y, width, height ): *table* object
-----------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object's coordinate by x-axis |
| *int* | y | Object's coordinate by y-axis |
| *int* | width | Object's width |
| *int* | height | Object's height |

In addition to the coordinates and size, any object has several universal properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *boolean* | .**hidden** | Whether the object is hidden. If the object is hidden, then its rendering and analysis of system events are ignored |
| *boolean* | .**disabled** | Whether the object is disabled. If the object is disabled, then it can be rendered, but all system events are ignored |
| *function* | :**draw**() | Mandatory method that is called to render the widget on the screen. It can be defined by the user in any convenient way |

After adding an object to the container using the :**addChild()** method, it acquires additional properties for ease of use:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**parent** | A pointer to the parent container of the object |
| *int* | .**localX** | Local position on the x-axis in the parent container |
| *int* | .**localY** | Local position on the y-axis in the parent container |
| *function* | :**indexOf**() | Get the index of this object in the parent container (iterative method, works slowly) |
| *function* | :**moveForward**() | Move the object "back" in the container children hierarchy |
| *function* | :**moveBackward**() | Move the object "forward" in the container children hierarchy |
| *function* | :**moveToFront**() | Move the object to the end of the container children hierarchy |
| *function* | :**moveToBack**() | Move the object to the beginning of the container children hierarchy |
| *function* | :**getFirstParent**() | Recursively get the first parent container. If there are many nested containers, the method will return the first in the hierarchy and the "main" of them |
| *function* | :**delete**() | Remove this object from the parent container. Roughly speaking, this is a convenient way of self-destruction |
| *function* | :**addAnimation**(*function* frameHandler, *function* onFinish): *table* animation | Add an animation to this object. For more information about animations and their creation, see below  |
| [*callback-function* | .**eventHandler**(*container* mainContainer, *object* object, ... *varargs* eventData) ]| An optional method for handling system events, called by the parent container handler. If it exists in the object under consideration, it will be called with the appropriate arguments |

An example of the implementation of the simplest rectangle object:

```lua
-- We will need downloaded double buffering library to render rectangles
local buffer = require("doubleBuffering")
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()

-- Create and add basic object to main container
local myObject = mainContainer:addChild(GUI.object(3, 2, 50, 10))
-- Create own :draw() method and make it render green rectangle
myObject.draw = function(object)
	buffer.square(object.x, object.y, object.width, object.height, 0x33FF80, 0x0, " ")
end

--------------------------------------------------------------------------------

-- Draw content of main container once on screen when program starts
mainContainer:drawOnScreen(true)
-- Start processing events for main container
mainContainer:startEventHandling()
```

As a result, we will get a nice green rectangle:

![](https://i.imgur.com/VBrEdyx.png)

Ready-to-use widgets
======

The widgets are listed below comes with the library and are written on the instructions of this documentation. If you want, you can make absolutely similar or much more technically advanced widgets without any difficulties.

GUI.**panel**( x, y, width, height, color, [transparency] ): *table* panel
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object's coordinate by x-axis |
| *int* | y | Object's coordinate by y-axis |
| *int* | width | Object's width |
| *int* | height | Object's height |
| *int* | color | Object's color |
| [*int* | transparency] | Optional transparency of the object |

The simplest object is a colored decorative panel. However, paradoxically, it is used quite often to create beautiful interface elements.

Example of panel implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()

-- Add panel that fits main container size
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x262626))
-- Add smaller red panel
mainContainer:addChild(GUI.panel(10, 10, mainContainer.width - 20, mainContainer.height - 20, 0x880000))

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![Imgur](http://i.imgur.com/Rho1RTl.png?1)

GUI.**text**( x, y, textColor, text ): *table* text
--------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object's coordinate by x-axis |
| *int* | y | Object's coordinate by y-axis |
| *int* | width | Object's width |
| *int* | height | Object's height |
| *int* | textColor | Object's text color |
| *string* | text | Object's text |

Another simpliest object is text. If you need to quickly display something in text form, then this widget is created for you. When you change the text, its width is automatically calculated to the desired value.

Example of implementation:
```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

mainContainer:addChild(GUI.text(3, 2, 0xFFFFFF, "Hello, world!"))
mainContainer:addChild(GUI.text(3, 3, 0xFFFFFF, "How are you? Wanna cast some EEWRD meatballs?"))

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![Imgur](https://i.imgur.com/ygqLguM.png)

GUI.**label**( x, y, width, height, textColor, text ): *table* label
--------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object's coordinate by x-axis |
| *int* | y | Object's coordinate by y-axis |
| *int* | width | Object's width |
| *int* | height | Object's height |
| *int* | textColor | Object's text color |
| *string* | text | Object's text |

A text label is an advanced version of the GUI.**text** that supports various alignment options.

| Тип свойства | Свойство |Описание |
| ------ | ------ | ------ |
| *function* | :**setAlignment**(*enum* horizontalAlignment, *enum* verticalAlignment): *table* label| Choose a text display option for label boundaries |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [left, top] alighment")):setAlignment(GUI.alignment.horizontal.left, GUI.alignment.vertical.top)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [center, top] alighment")):setAlignment(GUI.alignment.horizontal.center, GUI.alignment.vertical.top)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [right, top] alighment")):setAlignment(GUI.alignment.horizontal.right, GUI.alignment.vertical.top)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [left, center] alighment")):setAlignment(GUI.alignment.horizontal.left, GUI.alignment.vertical.center)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [center, center] alighment")):setAlignment(GUI.alignment.horizontal.center, GUI.alignment.vertical.center)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [right, center] alighment")):setAlignment(GUI.alignment.horizontal.right, GUI.alignment.vertical.center)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [left, bottom] alighment")):setAlignment(GUI.alignment.horizontal.left, GUI.alignment.vertical.bottom)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [center, bottom] alighment")):setAlignment(GUI.alignment.horizontal.center, GUI.alignment.vertical.bottom)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [right, bottom] alighment")):setAlignment(GUI.alignment.horizontal.right, GUI.alignment.vertical.bottom)

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![Imgur](https://i.imgur.com/ftonciY.png)

GUI.**image**( x, y, loadedImage ): *table* image
-------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object's coordinate by x-axis |
| *int* | y | Object's coordinate by y-axis |
| *table* | loadedImage | The image that was loaded by image.**load**() method |

To display beautiful things on the screen, plain text is not enough. GUI.**image** exists for this purpose.

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**image**| Table with pixel data of loaded image |

Example of implementation:

```lua
local image = require("image")
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

-- Load image, create widget from it and add it to main container
mainContainer:addChild(GUI.image(2, 2, image.load("/Furnance.pic")))

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i91.fastpic.ru/big/2017/0402/80/3b0ec81c3b2f660b9a4c6f18908f4280.png)

GUI.**button**( x, y, width, height, buttonColor, textColor, buttonPressedColor, textPressedColor, text ): *table* button
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object's coordinate by x-axis |
| *int* | y | Object's coordinate by y-axis |
| *int* | width | Object's width |
| *int* | height | Object's height |
| *int* | buttonColor | Object's default background color |
| *int* | textColor | Object's default text color |
| *int* | buttonPressedColor |  Object's pressed background color |
| *int* | textPressedColor | Object's pressed text color |
| *string* | text | Object's text |

What can be more familiar and convenient than a beautiful animated button? Click on it and enjoy. If you want to assign an action to a button after clicking, create a .**onTouch** method for it.

In addition to the standard design, there are also alternative buttons:

GUI.**framedButton**(...) has a frame around the edges

 ![Imgur](https://i.imgur.com/ajmXYFR.png)

GUI.**roundedButton**(...) has a nice rounded corners

 ![Imgur](https://i.imgur.com/0UO3Vbm.png)

For convenience, there is an adaptive version called GUI.**adaptiveButton**(...). It differs in that instead of **width** and **height**, it uses indentation in pixels from all sides of the text. This method is convenient for automatically calculating the size of a button on it's creation. Of course, GUI.**adaptiveFramedButton**(...) and GUI.**adaptiveRoundedButton**(...) are alse supported.

| Type | Property | Description |
| ------ | ------ | ------ |
| *boolean* | .**pressed**| This property allows the user to understand whether the button is pressed or not |
| *boolean* | .**switchMode**| This property is responsible for the mode at which the button behaves like a switch: when pressed, it will change its state to the opposite. The default value is **false** |
| *boolean* | .**animated**| This property is responsible for button's color transition animation when it is clicked. The default value is **true**|
| *float* | .**animationDuration**| Duration of the animation of the button when the animation is enabled. The default value is **0.2** |
| *callback-function* | .**onTouch**()| If this method exists, it is called after clicking on the button |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

-- Add a regular button
local regularButton = mainContainer:addChild(GUI.button(2, 2, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Regular button"))
regularButton.onTouch = function()
	GUI.error("Regular button was pressed")
end

-- Add a regular button with disabled state
local disabledButton = mainContainer:addChild(GUI.button(2, 6, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Disabled button"))
disabledButton.disabled = true

-- Add a regular button with switchMode state
local switchButton = mainContainer:addChild(GUI.button(2, 10, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Switch button"))
switchButton.switchMode = true
switchButton.onTouch = function()
	GUI.error("Switch button was pressed")
end

-- Add a regular button with disabled animation
local notAnimatedButton = mainContainer:addChild(GUI.button(2, 14, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Not animated button"))
notAnimatedButton.animated = false
notAnimatedButton.onTouch = function()
	GUI.error("Not animated button was pressed")
end

-- Add a rounded button
mainContainer:addChild(GUI.roundedButton(2, 18, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Rounded button")).onTouch = function()
	GUI.error("Rounded button was pressed")
end

-- Add a framed button
mainContainer:addChild(GUI.framedButton(2, 22, 30, 3, 0xFFFFFF, 0xFFFFFF, 0x880000, 0x880000, "Framed button")).onTouch = function()
	GUI.error("Framed button was pressed")
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![Imgur](https://i.imgur.com/Q2sX0P5.gif)

GUI.**actionButtons**( x, y, fat ): *table* actionButtons
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object's coordinate by x-axis |
| *int* | y | Object's coordinate by y-axis |
| [ *boolean* | fat ] | The option of drawing buttons with a large size |

This object is a container containing three round buttons. Basically, it is used to control the state of windows: to close, minimize, and so on.

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**close** | Pointer to an red button object |
| *table* | .**minimize** | Pointer to an yellow button object |
| *table* | .**maximize** | Pointer to an green button object |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

local actionButtonsRegular = mainContainer:addChild(GUI.actionButtons(3, 2, false))
local actionButtonsFat = mainContainer:addChild(GUI.actionButtons(3, 4, true))

actionButtonsRegular.close.onTouch = function()
	-- Do something when "close" button was touched
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/lYUS7fl.png)

GUI.**input**( x, y, width, height, backgroundColor, textColor, placeholderTextColor, backgroundFocusedColor, textFocusedColor, text, [placeholderText, eraseTextOnFocus, textMask ): *table* input
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object's coordinate by x-axis |
| *int* | y | Object's coordinate by y-axis |
| *int* | width | Object's width |
| *int* | height | Object's height |
| *int* | backgroundColor | Object's default background color |
| *int* | textColor | Object's default text color |
| *int* | placeholderTextColor | Object's **placeholder** color |
| *int* | backgroundFocusedColor | Object's focused background color |
| *int* | textFocusedColor | Object's focused text color |
| *string* | text | Object's text value |
| [*string* | placeholderText] | Text to be displayed, provided that the entered text is empty |
| [*boolean* | eraseTextOnFocus] | Delete text when the input is focused |
| [*char* | textMask] | A mask character for the text to be entered. Convenient for creating a password entry field |

The input object is intended for input and analysis of text data from the keyboard. You can move the cursor with clicks or left and right arrows. Clicking on the object starts the process of entering text, and pressing Enter or clicking on an empty zone on the screen will finish it.

| Type | Property | Description |
| ------ | ------ | ------ |
| *string* | .**text** | A variable that contains current displayed text of an object |
| *function* | :**startInput**() | Method for activation of text inputting |
| *callback-function* | .**validator**( *string* text ) | The function that is called after the text is entered in the input field. If it returns **true**, the text in the text field will be changed to the entered text, otherwise the entered data will be ignored |
| *callback-function* | .**onInputFinished**() | The function that is called after entering data in the input field: it's a handy thing if you want to do something after entering text. If the object has .**validator** function, and if the text does not pass the check through it, then .**onInputFinished** will not be called |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

mainContainer:addChild(GUI.input(2, 2, 30, 3, 0xEEEEEE, 0x555555, 0x999999, 0xFFFFFF, 0x2D2D2D, "Hello world", "Placeholder text")).onInputFinished = function()
	GUI.error("Input finished!")
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![Imgur](http://i.imgur.com/njPN0eg.gif)
