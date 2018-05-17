About
======
GUI is a multifunctional graphics library, especially designed and optimized for low-performance computers. You can realize all of your most perverted fantasies using it: from habitual buttons, sliders and charts to complex animated interfaces. Extreme performance of the library is achieved by using double buffering and complex color grouping and processing algorithms.

For example, my OS, IDE and 3D-engine are fully implemented by the methods of this library:

![](https://i.imgur.com/Ki5bX0I.gif)

![](http://i.imgur.com/tHAiTmF.gif)

Let the abundance of text below not frighten you: this documentation has many illustrated examples with full working code.

| Contents |
| ----- |
| [Installation](#installation) |
| [Containers](#containers) |
| [Objects](#objects) |
| [Constants](#constants) |
| [Standalone methods](#standalone-methods) |
| [    GUI.isPointInside](#guiispointinsideobject-x-y-boolean-result) |
| [    GUI.getAlignmentCoordinates](#guigetalignmentcoordinatesfirstobjectx-firstobjecty-firstobjectwidth-firstobjectheight-firstobjecthorizontalalignment-firstobjectverticalalignment-secondobjectwidth-secondobjectheight-int-x-int-y) |
| [    GUI.getMarginCoordinates](#guigetalignmentcoordinatesx-y-horizontalalignment-verticalalignment-horizontalmargin-verticalmargin-int-x-int-y) |
| [    GUI.highlightString](#guihighlightstringx-y-width-fromsymbol-indentationwidth-syntaxpatterns-syntaxcolorscheme-data) |
| [    GUI.error](#guierrorvarargs) |
| [    GUI.addPalette](#guiaddpaletteparentcontainer-addpanel-initialcolor-table-palette) |
| [    GUI.addFilesystemDialog](#guiaddfilesystemdialogparentcontainer-addpanel--table-filesystemdialog) |
| [    GUI.addBackgroundContainer](#guiaddbackgroundcontainerparentcontainer-addpanel-addlayout-title-table-palette) |
| [Ready-to-use widgets](#ready-to-use-widgets) |
| [    GUI.panel](#guipanel-x-y-width-height-color-transparency--table-panel) |
| [    GUI.text](#guitext-x-y-textcolor-text--table-text) |
| [    GUI.label](#guilabel-x-y-width-height-textcolor-text--table-label) |
| [    GUI.image](#guiimage-x-y-loadedimage--table-image) |
| [    GUI.button](#guibutton-x-y-width-height-buttoncolor-textcolor-buttonpressedcolor-textpressedcolor-text--table-button) |
| [    GUI.actionButtons](#guiactionbuttons-x-y-fat--table-actionbuttons) |
| [    GUI.input](#guiinput-x-y-width-height-backgroundcolor-textcolor-placeholdertextcolor-backgroundfocusedcolor-textfocusedcolor-text-placeholdertext-erasetextonfocus-textmask--table-input) |
| [    GUI.slider](#guislider-x-y-width-primarycolor-secondarycolor-pipecolor-valuecolor-minimumvalue-maximumvalue-value-showcornervalues-currentvalueprefix-currentvaluepostfix--table-slider) |
| [    GUI.switch](#guiswitch-x-y-width-primarycolor-secondarycolor-pipecolor-state--table-switch) |
| [    GUI.switchAndLabel](#guiswitchandlabel-x-y-width-switchwidth-primarycolor-secondarycolor-pipecolor-textcolor-text-switchstate--table-switchandlabel) |
| [    GUI.colorSelector](#guicolorselector-x-y-width-height-color-text--table-colorselector) |
| [    GUI.list](#guilist-x-y-width-height-itemsize-spacing-backgroundcolor-textcolor-alternatebackgroundcolor-alternatetextcolor-backgroundselectedcolor-textselectedcolor--offsetmode--table-list) |
| [    GUI.comboBox](#guicombobox-x-y-width-elementheight-backgroundcolor-textcolor-arrowbackgroundcolor-arrowtextcolor--table-combobox) |
| [    GUI.menu](#guimenu-x-y-width-backgroundcolor-textcolor-backgroundpressedcolor-textpressedcolor-backgroundtransparency--table-menu) |
| [    GUI.resizer](#guiresizer-x-y-width-height-resizercolor-arrowcolor--table-resizer) |
| [    GUI.progressBar](#guiprogressbar-x-y-width-primarycolor-secondarycolor-valuecolor-value-thin-showvalue-valueprefix-valuepostfix--table-progressbar) |
| [    GUI.filesystemTree](#guifilesystemtree-x-y-width-height-backgroundcolor-directorycolor-filecolor-arrowcolor-backgroundselectioncolor-textselectioncolor-arrowselectioncolor-disabledcolor-scrollbarbackground-scrollbarforeground-showmode-selectionmode--table-filesystemtree) |
| [    GUI.filesystemChooser](#guifilesystemchooser-x-y-width-height-backgroundcolor-textcolor-tipbackgroundcolor-tiptextcolor-initialtext-sumbitbuttontext-cancelbuttontext-placeholdertext-filesystemdialogmode-filesystemdialogpath--table-filesystemchooser) |
| [    GUI.codeView](#guicodeview-x-y-width-height-lines-fromsymbol-fromline-maximumlinelength-selections-highlights-highlightluasyntax-indentationwidth--table-codeview) |
| [    GUI.chart](#guichart-x-y-width-height-axiscolor-axisvaluecolor-axishelperscolor-chartcolor-xaxisvalueinterval-yaxisvalueinterval-xaxispostfix-yaxispostfix-fillchartarea-values--table-chart) |
| [    GUI.brailleCanvas](#guibraillecanvas-x-y-width-height--table-braillecanvas) |
| [    GUI.scrollBar](#guiscrollbar-x-y-width-height-backgroundcolor-foregroundcolor-minimumvalue-maximumvalue-value-shownvaluecount-onscrollvalueincrement-thinhorizontalmode--table-scrollbar) |
| [    GUI.textBox](#guitextbox-x-y-width-height-backgroundcolor-textcolor-lines-currentline-horizontaloffset-verticaloffset-autowrap-autoheight-table-textbox) |

Installation
======

The easiest way is to use automatic [installer](https://pastebin.com/ryhyXUKZ) that will download all necessary files for you via single command:

    pastebin run ryhyXUKZ
    
However, you can download dependencies manually, if required. They are listed in the following table:

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

![](https://i.imgur.com/GJmDQ2j.png)

Containers also have an important feature: any child that extends beyond the bounds of the container will be rendered only within the size of this container:

![](https://i.imgur.com/SBuL1it.png)

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

![](https://i.imgur.com/eHqIFNN.png)

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**children** | Table that contains all child objects of this container |
| *function* | :**addChild**(*table* child, [*int* atIndex]): *table* child| Add specified object to the container as a child. When you do this, the object's global coordinates will become local. If the optional parameter **atIndex** is specified, then the element will be added to the corresponding position in container.**children** table |
| *function* | :**removeChildren**([*int* fromIndex, *int* toIndex]): *table* container | Delete all child elements of the container. If the optional parameters of the element indices are specified, the deletion will be performed in the appropriate range |
| *function* | :**startEventHandling**([*float* delay]): *table* container | Run the event processing for this container and analyse events for all it's child objects. The  **delay** parameter is similar to computer.**pullSignal** one |
| *function* | :**stopEventHandling**(): *table* container | Stop processing events for this container |
| *function* | :**draw**() | Recursively renders the contents of the container in the order of the queue of its children. I draw your attention to the fact that this method only draws data into the screen buffer. To display changes on the screen, you must use the doubleBuffering.**drawChanges**() method or use method below |
| *function* | :**drawOnScreen**([*boolean* force]) | This method is similar to :**draw**() with the only difference that after drawing data into the screen buffer, it will automatically display changes on the screen. That is, in fact, it exists solely for the convenience of writing code |

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
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |

In addition to the coordinates and size, any object has several universal properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *boolean* | .**hidden** | Whether the object is hidden. If the object is hidden, then its rendering and analysis of system events are ignored |
| *boolean* | .**disabled** | Whether the object is disabled. If the object is disabled, then it can be rendered, but all system events are ignored |
| *function* | :**isPointInside**() | A method that allows you to determine whether a specified point is inside the geometry of a specified object |
| *function* | :**draw**() | Mandatory method that is called to render the widget on the screen. It can be defined by the user in any convenient way |

After adding an object to the container using the :**addChild()** method, it acquires additional properties for ease of use:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**parent** | A pointer to the parent container of the object |
| *int* | .**localX** | Local position on the x-axis in the parent container |
| *int* | .**localY** | Local position on the y-axis in the parent container |
| *function* | :**indexOf**() | Get the index of this object in the parent container (iterative method) |
| *function* | :**moveForward**() | Move the object "back" in the container children hierarchy |
| *function* | :**moveBackward**() | Move the object "forward" in the container children hierarchy |
| *function* | :**moveToFront**() | Move the object to the end of the container children hierarchy |
| *function* | :**moveToBack**() | Move the object to the beginning of the container children hierarchy |
| *function* | :**getFirstParent**() | Recursively get the first parent container. If there are many nested containers, the method will return the first in the hierarchy and the "main" of them |
| *function* | :**remove**() | Remove this object from the parent container. Roughly speaking, this is a convenient way of self-destruction |
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
	buffer.drawRectangle(object.x, object.y, object.width, object.height, 0x33FF80, 0x0, " ")
end

--------------------------------------------------------------------------------

-- Draw content of main container once on screen when program starts
mainContainer:drawOnScreen(true)
-- Start processing events for main container
mainContainer:startEventHandling()
```

As a result, we will get a nice green rectangle:

![](https://i.imgur.com/VBrEdyx.png)

Constants
======

This is a rather boring section of the documentation, but it is still necessary for learning. The library has several universal constants, with which some objects are oftenly working. For example, if you want to centerize the text on the screen, you will need alignment constants. If you want to change object's direction - use direction constants, and so on.

| Type | Constant | Value | Description |
| ------ | ------ | ------ | ------ |
| *enum* | GUI.**ALIGNMENT_HORIZONTAL_LEFT** | - | Align object to left side horizontally |
| *enum* | GUI.**ALIGNMENT_HORIZONTAL_CENTER** | - | Align object to center side horizontally |
| *enum* | GUI.**ALIGNMENT_HORIZONTAL_LEFT** | - | Align object to right side horizontally |
| *enum* | GUI.**ALIGNMENT_VERTICAL_TOP** | - | Align object to top side vertically |
| *enum* | GUI.**ALIGNMENT_VERTICAL_CENTER** | - | Align object to center side vertically |
| *enum* | GUI.**ALIGNMENT_VERTICAL_BOTTOM** | - | Align object to bottom side vertically |
| *enum* | GUI.**DIRECTION_HORIZONTAL** | - | Set horizontal direction to an object |
| *enum* | GUI.**DIRECTION_VERTICAL** | - | Set horizontal direction to an object |
| *enum* | GUI.**IO_MODE_OPEN** | - | Mode for opening data |
| *enum* | GUI.**IO_MODE_SAVE** | - | Mode for saving data |
| *enum* | GUI.**IO_MODE_FILE** | - | Mode for working with files |
| *enum* | GUI.**IO_MODE_DIRECTORY** | - | Mode for working with directories |
| *enum* | GUI.**IO_MODE_BOTH** | - | Mode for working with bothly files and directories |
| *enum* | GUI.**SIZE_POLICY_ABSOLUTE** | - | Calculation of object's sizes via absolute values |
| *enum* | GUI.**SIZE_POLICY_RELATIVE** | - | Calculation of object's sizes via relative (percentage) values |
| *string* | GUI.**PALETTE_CONFIG_PATH** | /lib/.palette.cfg | Path where GUI.**palette** favourites colors are being saved |
| *table* | GUI.**LUA_SYNTAX_PATTERNS** | - | Required patterns for Lua syntax highlighting by GUI.**highlightString**(...) method |
| *table* | GUI.**LUA_SYNTAX_COLORS** | - | Default color scheme for Lua syntax highlighting by GUI.**highlightString**(...) method |

Still not tired yet? And now think how I fucked up writing them during the library development. Shitty constants...

![](https://i.imgur.com/RDg5Qnz.jpg)

Standalone methods
======

The library has several methods that can simplify the development of programs. For example, a context menu, an information window or a palette window.

GUI.**error**(...varargs)
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *varargs* | ... | A lot of parameters having any type that need to be displayed in a window |

This method displays a debug window with text information. The line that is too long will be automatically wrapped. If parameter is a table, then it will be automatically serialized. To close the window, you must hit the Return key or click on the "OK" button

Example of implementation:

```lua
local buffer = require("doubleBuffering")
local GUI = require("GUI")

--------------------------------------------------------------------------------

buffer.clear(0x2D2D2D)
GUI.error("Something went wrong here, my friend")
```

Result:

![](http://i.imgur.com/s8mA2FL.png?1)

GUI.**addContextMenu**(parentContainer, x, y, [backgroundColor, textColor, backgroundPressedColor, textPressedColor, disabledColor, separatorColor, backgroundTransparency, shadowTransparency]): *table* contextMenu
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *table* | parentContainer | Container to which context menu will be added |
| *int* | x | Local coordinate by x-axis in parent container |
| *int* | y | Local coordinate by y-axis in parent container |
| [*int* | backgroundColor] | Optional default background color |
| [*int* | textColor] | Optional default text color |
| [*int* | backgroundPressedColor] | Optional pressed item background color |
| [*int* | textPressedColor] | Optional pressed item text color |
| [*int* | disabledColor] | Optional disabled item text color |
| [*int* | separatorColor] | Optional separator text color |
| [*float* [0.0; 1.0] | backgroundTransparency] | Optional background transparency |
| [*float* [0.0; 1.0] | shadowTransparency] | Optional shadow transparency |

This is one of the most commonly used methods. It adds a context menu to the specified container and allows to work with it fantastically easy. All optional parameters of the method exist only for customization, and if they are not specified, pre-stored library constants will be used.

If the context menu contains too many items, scrolling buttons will appear and mouse wheel support will be enabled to navigate menu content. Also if you select an item and it's have callback function .**onTouch()**, it will be called

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *function* | :**addItem**(*string* text, [*boolean* disabled, *string* shortcut, *int* color]): *table* item | Add new item to context menu. If **disabled** parameter is specified, item will be shown but not available for clicking You can also specify .**onTouch**() function to added item to do some stuff if desired |
| *function* | :**addSeparator**()| Add an separator to context menu |
| *function* | :**removeItem**(*int* index): *table* item | Remove item from context menu by it's index |
| *function* | :**addSubMenu**(*string* text, [*boolean* disabled]): *table* contextMenu| Add another context menu to this context menu. The returned menu object is independent and supports all the methods described above  |
| *callback-function* | .**onClose**(*int* selectedIndex)| This function is called after user selects a menu item or closes it. If an element has been selected, this function will have and selected item index as a parameter |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()

-- Add an background panel and attack event handler to it
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D)).eventHandler = function(mainContainer, object, e1, e2, e3, e4)
	if e1 == "touch" then
		-- Add context menu object to main container and some items to it
		local contextMenu = GUI.addContextMenu(mainContainer, e3, e4)
		contextMenu:addItem("New")
		contextMenu:addItem("Open").onTouch = function()
			-- Do something to open file or whatever
		end

		-- Add a sub menu and some items to it
		local subMenu = contextMenu:addSubMenu("Open with")
		subMenu:addItem("Explorer.app")
		subMenu:addItem("Viewer.app")
		subMenu:addItem("Finder.app")
		subMenu:addSeparator()
		subMenu:addItem("Browse...")

		contextMenu:addSeparator()
		contextMenu:addItem("Save", true)
		contextMenu:addItem("Save as")
		contextMenu:addSeparator()

		-- Of course, you can use loops to do the same
		for i = 1, 25 do
			contextMenu:addItem("Do something " .. i)
		end

		mainContainer:drawOnScreen()
	end
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/JqGXAs1.gif)

GUI.**addPalette**(parentContainer, addPanel, initialColor): *table* palette
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *table* | parentContainer | Container to which palette will be added |
| *boolean* | addPanel | Necessity to add a semi-transparent dark background panel |
| *int* | initialColor | Initial color that palette open with |

This method creates a palette window in the specified container right at its center and returns the palette object. It is convenient in that you do not need to manually calculate the coordinates of the window, as well as useful to people who do not want to use GUI.**colorSelector*

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

-- Create "main" container
local mainContainer = GUI.fullScreenContainer()
-- Add gray background panel
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

-- Add palette window
local palette = GUI.addPalette(mainContainer, false, 0x9900FF)
-- Do something after color selection
palette.onSubmit = function()
	GUI.error("This color was selected: " .. string.format("0x%06X", palette.color.integer))
	mainContainer:drawOnScreen()
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/GvVbn1b.gif)

GUI.**addFilesystemDialog**(parentContainer, addPanel, ...): *table* filesystemDialog
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *table* | parentContainer | Container to which palette will be added |
| *boolean* | addPanel | Necessity to add a semi-transparent dark background panel |
| *varargs* | ... | Multiple parameters that comes to GUI.**fileSystemDialog** starting from **width** |

This method creates a filesystem dialor in specified container with a nice drop-down animation and allows you to work with it in the same way as with a conventional JUI. It is useful for manual work with the file system, if there is no desire to work with GUI.**filesystemChooser**

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**filesystemDialog** | Pointer to internal filesystemDialog object |
| *function* | :**show**() | This method will update internal file list and start drop-down animation. After that dialog will be available for user interactions |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

local filesystemDialog = GUI.addFilesystemDialog(mainContainer, false, 50, math.floor(mainContainer.height * 0.8), "Open", "Cancel", "File name", "/")
filesystemDialog:setMode(GUI.IO_MODE_OPEN, GUI.IO_MODE_FILE)
filesystemDialog:addExtensionFilter(".pic")
filesystemDialog.onSubmit = function(path)
	GUI.error("This path was selected: " .. path)
end

filesystemDialog:show()

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/4WqJBVk.gif)

GUI.**addBackgroundContainer**(parentContainer, addPanel, addLayout, [title]): *table* palette
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *table* | parentContainer | Container to which palette will be added |
| *boolean* | addPanel | Necessity to add a semi-transparent dark background panel |
| *boolean* | addLayout | Necessity to add a 3-columned background layout |
| [*string* | title] | If specified, adds a label to layout as child |

This method creates a new container and adds it as a child to the specified container. If background panel is added, it will already have an event listener: so if you click on panel, this container will be deleted automatically. Personally, I use this object everywhere to quickly create a simple menus with easy closing feature and automated layout calculations.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**panel** | Pointer to background panel object. Doesn't exists if **addPanel** parameter is set to **false** |
| *table* | .**layout** | Pointer to background layout object. Doesn't exists if **addLayout** parameter is set to **false** |
| *table* | .**label** | Pointer to title label object. Doesn't exists if **title** parameter is **nil** |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

-- Add a button to main container and .onTouch() method
mainContainer:addChild(GUI.button(3, 2, 36, 3, 0xE1E1E1, 0x4B4B4B, 0xA5A5A5, 0x0, "Add container")).onTouch = function()
	-- Add a background container to main container with background panel and layout
	local container = GUI.addBackgroundContainer(mainContainer, true, true, "Hello world")
	-- Add a switch and label to it's layout
	container.layout:addChild(GUI.switchAndLabel(1, 1, 36, 8, 0x66DB80, 0x2D2D2D, 0xE1E1E1, 0x878787, "I like to suck big dicks:", true))
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/VOX9BzY.gif)

GUI.**highlightString**(x, y, width, fromSymbol, indentationWidth, syntaxPatterns, syntaxColorScheme, data)
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Coordinate by x-axis to draw from |
| *int* | y | Coordinate by y-axis to draw from |
| *int* | width | Width of highlighting area  |
| *int* | fromSymbol | Symbol index to draw from |
| *int* | indentationWidth | Width of indentation that will be added instead on whitespace symbols in string starting |
| *table* | syntaxPatterns | Patterns for syntax highlighting |
| *table* | syntaxColorScheme | Color scheme for syntax highlighting |
| *string* | data | String to highlight |

This method allows you to highlight specified string and draw the result to screen buffer using specified syntax patterns and specified color scheme. This library already comes with a set of patterns and color scheme for Lua syntax (see **Constants**), however you can easily write your own for any other programming language if you wish.

Example of implementation:

```lua
local GUI = require("GUI")
local buffer = require("doubleBuffering")

--------------------------------------------------------------------------------

buffer.clear(0x1E1E1E)

-- Open file and read it's lines
local y = 1
for line in io.lines("/lib/advancedLua.lua") do
	-- Replace tab symbols to 2 whitespaces and Windows line endings to UNIX line endings
	line = line:gsub("\t", "  "):gsub("\r\n", "")
	-- Highlight result
	GUI.highlightString(3, y, buffer.getWidth(), 1, 2, GUI.LUA_SYNTAX_PATTERNS, GUI.LUA_SYNTAX_COLOR_SCHEME, line)
	
	y = y + 1
	if y > buffer.getHeight() then
		break
	end
end

buffer.drawChanges(true)
```

Result:

![](https://i.imgur.com/kYRHeMu.png)

GUI.**isPointInside**(object, x, y): *boolean* result
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *table* | object | Pointer to any object |
| *int* | x | Coordinate by x-axis on screen |
| *int* | y | Coordinate by y-axis on screen |

This method checks whether the specified point is inside the boundaries of the specified object. This method is useful in rare cases for manual verification.

GUI.**getAlignmentCoordinates**(firstObjectX, firstObjectY, firstObjectWidth, firstObjectHeight, firstObjectHorizontalAlignment, firstObjectVerticalAlignment, secondObjectWidth, secondObjectHeight): *int* x, *int* y
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | firstObjectX | Coordinate by x-axis of first object |
| *int* | firstObjectY | Coordinate by y-axis of first object |
| *int* | firstObjectWidth | Width of first object |
| *int* | firstObjectHeight | Height of first object |
| *enum* | firstObjectHorizontalAlignment | Horizontal alignment of first object |
| *enum* | firstObjectVerticalAlignment | Vertical alignment of first object |
| *int* | secondObjectWidth | Width of second object |
| *int* | secondObjectHeight | Height of second object |

This method calculates global (screen) coordinates of the second object inside the first, based on coordinates and sizes of both objects. For example, it's used by GUI.**layout**, GUI.**label** and GUI.**textBox**

GUI.**getMarginCoordinates**(x, y, horizontalAlignment, verticalAlignment, horizontalMargin, verticalMargin): *int* x, *int* y
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *enum* | horizontalAlignment | Object horizontal alignment |
| *enum* | verticalAlignment | Object vertical alignment |
| *int* | horizontalMargin | Object horizontal margin in pixels |
| *int* | verticalMargin | Object vertical margin in pixels |

This method calculates the global (screen) coordinates inside the object, based on its alignment and pixel margin. For example, it's used by GUI.**layout**

Ready-to-use widgets
======

The widgets are listed below comes with the library and are written on the instructions of this documentation. If you want, you can make absolutely similar or much more technically advanced widgets without any difficulties.

GUI.**panel**( x, y, width, height, color, [transparency] ): *table* panel
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | color | Object color |
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

![](http://i.imgur.com/Rho1RTl.png?1)

GUI.**text**( x, y, textColor, text ): *table* text
--------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | textColor | Object text color |
| *string* | text | Object text |

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

![](https://i.imgur.com/ygqLguM.png)

GUI.**label**( x, y, width, height, textColor, text ): *table* label
--------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | textColor | Object text color |
| *string* | text | Object text |

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

mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [left, top] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_LEFT, GUI.ALIGNMENT_VERTICAL_TOP)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [center, top] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_CENTER, GUI.ALIGNMENT_VERTICAL_TOP)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [right, top] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_RIGHT, GUI.ALIGNMENT_VERTICAL_TOP)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [left, center] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_LEFT, GUI.ALIGNMENT_VERTICAL_CENTER)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [center, center] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_CENTER, GUI.ALIGNMENT_VERTICAL_CENTER)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [right, center] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_RIGHT, GUI.ALIGNMENT_VERTICAL_CENTER)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [left, bottom] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_LEFT, GUI.ALIGNMENT_VERTICAL_BOTTOM)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [center, bottom] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_CENTER, GUI.ALIGNMENT_VERTICAL_BOTTOM)
mainContainer:addChild(GUI.label(1, 1, mainContainer.width, mainContainer.height, 0xFFFFFF, "Label with [right, bottom] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_RIGHT, GUI.ALIGNMENT_VERTICAL_BOTTOM)

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/ftonciY.png)

GUI.**image**( x, y, loadedImage ): *table* image
-------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *table* | loadedImage | The image that was loaded by image.**load**() method |

To display beautiful things on the screen, plain text is not enough. GUI.**image** exists for this purpose.

This object has following properties:

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
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | buttonColor | Object default background color |
| *int* | textColor | Object default text color |
| *int* | buttonPressedColor |  Object pressed background color |
| *int* | textPressedColor | Object pressed text color |
| *string* | text | Object text |

What can be more familiar and convenient than a beautiful animated button? Click on it and enjoy. If you want to assign an action to a button after clicking, create a .**onTouch** method for it.

In addition to the standard design, there are also alternative buttons:

GUI.**framedButton**(...) has a frame around the edges

 ![](https://i.imgur.com/ajmXYFR.png)

GUI.**roundedButton**(...) has a nice rounded corners

 ![](https://i.imgur.com/0UO3Vbm.png)

For convenience, there is an adaptive version called GUI.**adaptiveButton**(...). It differs in that instead of **width** and **height**, it uses indentation in pixels from all sides of the text. This method is convenient for automatically calculating the size of a button on it's creation. Of course, GUI.**adaptiveFramedButton**(...) and GUI.**adaptiveRoundedButton**(...) are alse supported.

This object has following properties:

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

![](https://i.imgur.com/Q2sX0P5.gif)

GUI.**actionButtons**( x, y, [fat] ): *table* actionButtons
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| [ *boolean* | fat ] | The option of drawing buttons with a large size |

This object is a container containing three round buttons. Basically, it is used to control the state of windows: to close, minimize, and so on.

This object has following properties:

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

GUI.**input**( x, y, width, height, backgroundColor, textColor, placeholderTextColor, backgroundFocusedColor, textFocusedColor, text, [placeholderText, eraseTextOnFocus, textMask] ): *table* input
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | backgroundColor | Object default background color |
| *int* | textColor | Object default text color |
| *int* | placeholderTextColor | Object **placeholder** color |
| *int* | backgroundFocusedColor | Object focused background color |
| *int* | textFocusedColor | Object focused text color |
| *string* | text | Object text value |
| [*string* | placeholderText] | Text to be displayed, provided that the entered text is empty |
| [*boolean* | eraseTextOnFocus] | Delete text when the input is focused |
| [*char* | textMask] | A mask character for the text to be entered. Convenient for creating a password entry field |

The input object is intended for input and analysis of text data from the keyboard. Pasting data from real clipboard is also supported. You can move the cursor with clicks or left and right arrows. Clicking on the object starts the process of entering text, and pressing Enter or clicking on an empty zone on the screen will finish it.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *string* | .**text** | A variable that contains current displayed text of an object |
| *function* | :**startInput**() | Method for activation of text inputting |
| *callback-function* | .**validator**(*string* text) | The function that is called after the text is entered in the input field. If it returns **true**, the text in the text field will be changed to the entered text, otherwise the entered data will be ignored |
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

![](http://i.imgur.com/njPN0eg.gif)

GUI.**slider**( x, y, width, primaryColor, secondaryColor, pipeColor, valueColor, minimumValue, maximumValue, value, [showCornerValues, currentValuePrefix, currentValuePostfix] ): *table* slider
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | primaryColor | Object primary color |
| *int* | secondaryColor | Object secondary color |
| *int* | pipeColor | Object "pipe" color |
| *int* | valueColor | Object text value color |
| *float* | minimumValue | Object minimum value |
| *float* | maximumValue | Object maximum value |
| *float* | value | Object current value |
| [*bool* | showCornerValues] | Do min/max values are needed to be shown at slider's corners |
| [*string* | currentValuePrefix] | Prefix for value displaying |
| [*string* | currentValuePostfix] | Postfix for value displaying |

Standard slider is used to select a numerical value from the specified range. The value of the slider is always **float**.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *float* | .**value** | Current slider value variable |
| *boolean* | .**roundValues** | This property will **visually** round silder values |
| *callback-function* | .**onValueChanged**()| This function will be called after slider value changing |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

local slider = mainContainer:addChild(GUI.slider(4, 2, 30, 0x66DB80, 0x0, 0xFFFFFF, 0xAAAAAA, 0, 100, 50, true, "Prefix: ", " postfix"))
slider.roundValues = true
slider.onValueChanged = function(value)
	-- Do something when slider's value changed
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i.imgur.com/F7jrTPM.gif)

GUI.**switch**( x, y, width, primaryColor, secondaryColor, pipeColor, state ): *table* switch
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | primaryColor | Object primary color |
| *int* | secondaryColor | Object secondary color |
| *int* | pipeColor | Object "pipe" color |
| *boolean* | state | Object state |

This is one of my favorite widgets. An animated switch is designed to change the state of anything from true to false and vice versa.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *boolean* | .**state** | Current switch state variable |
| *function* | :**setState**(*boolean* state)| Change switch state to specified one |
| *callback-function* | .**onStateChanged**()| This function will be called when switch state is changed |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

local switch1 = mainContainer:addChild(GUI.switch(3, 2, 8, 0x66DB80, 0x1D1D1D, 0xEEEEEE, true))
local switch2 = mainContainer:addChild(GUI.switch(3, 4, 8, 0x66DB80, 0x1D1D1D, 0xEEEEEE, false))
switch2.onStateChanged = function(state)
	GUI.error("Switch state changed!")
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i.imgur.com/prBIAsL.gif)

GUI.**switchAndLabel**( x, y, width, switchWidth, primaryColor, secondaryColor, pipeColor, textColor, text, switchState ): *table* switchAndLabel
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Total width |
| *int* | switchWidth | Switch width |
| *int* | primaryColor | Switch primary color |
| *int* | secondaryColor | Switch secondary color |
| *int* | textColor | Label text color |
| *string* | text | Label text |
| *boolean* | state | Switch state |

This object is a container containing a label and switch, and is a quick way to visualize the boolean parameters for your programs.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**switch**| Pointer to switch child object |
| *table* | .**label**| Pointer to label child object |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

mainContainer:addChild(GUI.switchAndLabel(2, 2, 25, 8, 0x66DB80, 0x1D1D1D, 0xEEEEEE, 0x999999, "Sample text 1:", true))
mainContainer:addChild(GUI.switchAndLabel(2, 4, 25, 8, 0x66DB80, 0x1D1D1D, 0xEEEEEE, 0x999999, "Sample text 2:", false))

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i.imgur.com/4zKOla9.gif)

GUI.**colorSelector**( x, y, width, height, color, text ): *table* colorSelector
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | color | Current selected color |
| *string* | text | Object text |

The choice of colors is almost the most difficult task on such inconvenient devices as computers from OpenComputers. ColorSelector will do everything for you: just click and choose the desired color from a palette.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *callback-function* | .**onTouch**() | This function will be called after choosing color from palette |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

mainContainer:addChild(GUI.colorSelector(2, 2, 30, 3, 0xFF55FF, "Choose color")).onTouch = function()
	-- Do something after choosing color
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i.imgur.com/QVxu2N0.gif)

GUI.**list**( x, y, width, height, itemSize, spacing, backgroundColor, textColor, alternateBackgroundColor, alternateTextColor, backgroundSelectedColor, textSelectedColor, [offsetMode] ): *table* list
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | itemSize | Item size by selected direction |
| *int* | spacing | Space between items |
| *int* | backgroundColor | Object background color |
| *int* | textColor | Object text color |
| *int* | alternateBackgroundColor | Object alternate background color |
| *int* | alternateTextColor | Object alternate text color |
| *int* | backgroundSelectedColor | Object selection background color |
| *int* | textSelectedColor | Object selection text color |
| [*boolean* | offsetMode] | Optional mode, in which the items size are created based on the pixel offset from their texts |

This object is used to select items from the list. It resembles a single-column Excel table with the ability to change the orientation. List is universal object and is used as a inherited source for many other widgets.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *int* | .**selectedItem** | Index of currently selected item |
| *function* | :**addItem**(*string* text): *table* item| Add new item to object. You can specify .**onTouch**() function to if desired |
| *function* | :**getItem**(*int* index): *table* item| Get item by it's index |
| *function* | :**select**(*int* index): *table* list| Select item from List by it's index |
| *function* | :**deselect**(): *table* list| Deselect selected elements |
| *function* | :**setAlignment**(*enum* horizontalAlignment, *enum* verticalAlignment): *table* list| Установить вариант выравнивания элементов List. По умолчанию вырванивание идет по левому верхнему углу |
| *function* | :**setDirection**(*enum* direction): *table* list| Choose an items display option for List boundaries. The default alignment is **left** and **top** |
| *function* | :**setSpacing**(*int* spacing): *table* list| Set spacing between List items |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

-- Create vertically oriented list
local verticalList = mainContainer:addChild(GUI.list(3, 2, 25, 30, 3, 0, 0xE1E1E1, 0x4B4B4B, 0xD2D2D2, 0x4B4B4B, 0x3366CC, 0xFFFFFF, false))
verticalList:addItem("Hello world")
verticalList:addItem("This is test").onTouch = function()
	GUI.error("Selected item: " .. verticalList.selectedItem)
end
verticalList:addItem("Beautiful")
verticalList:addItem("Like a shit")

-- Create horizontally oriented list
local horizontalList = mainContainer:addChild(GUI.list(34, 2, 100, 3, 2, 0, 0xE1E1E1, 0x4B4B4B, 0xE1E1E1, 0x4B4B4B, 0x696969, 0xFFFFFF, true))
horizontalList:setDirection(GUI.DIRECTION_HORIZONTAL)
horizontalList:setAlignment(GUI.ALIGNMENT_HORIZONTAL_CENTER, GUI.ALIGNMENT_VERTICAL_TOP)
horizontalList:addItem("Applications")
horizontalList:addItem("Libraries")
horizontalList:addItem("Scripts")
horizontalList:addItem("Wallpapers")

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/lYzufn2.gif)

GUI.**menu**( x, y, width, backgroundColor, textColor, backgroundPressedColor, textPressedColor, [backgroundTransparency] ): *table* menu
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | backgroundColor | Object background color |
| *int* | textColor | Object text color |
| *int* | backgroundPressedColor | Object background pressed color |
| *int* | textPressedColor | Object text pressed color |
| [*int* | backgroundTransparency]  | Optional background transparency |

The menu object allows you to select items from the set of listed options. For the most part it is used in structures like "**File - Edit - View - Help**", etc.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *function* | :**addItem**(*string* text, *int* color): *table* item | Add a new item to Menu. You can specify .**onTouch**() function to item if desired |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

local menu = mainContainer:addChild(GUI.menu(1, 1, mainContainer.width, 0xEEEEEE, 0x666666, 0x3366CC, 0xFFFFFF, nil))
menu:addItem("MineCode IDE", 0x0)
local item = menu:addItem("File")
item.onTouch = function()
	local contextMenu = GUI.contextMenu(item.x, item.y + 1)
	contextMenu:addItem("New")
	contextMenu:addItem("Open").onTouch = function()
		GUI.error("Open was pressed")
	end
	contextMenu:addSeparator()
	contextMenu:addItem("Save")
	contextMenu:addItem("Save as")
	contextMenu:show()
end
menu:addItem("Edit")
menu:addItem("View")
menu:addItem("About")

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i.imgur.com/b1Tmge5.gif)

GUI.**comboBox**( x, y, width, elementHeight, backgroundColor, textColor, arrowBackgroundColor, arrowTextColor ): *table* comboBox
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | elementHeight | Object item height |
| *int* | backgroundColor | Object background color |
| *int* | textColor | Object text color |
| *int* | arrowBackgroundColor | Object arrow background color |
| *int* | arrowTextColor | Object arrow text color |

The combo box is designed to select one of the big set of items from the compact drop-down menu.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *int* | .**selectedItem** | Index of selected element |
| *function* | :**addItem**(*string* text, *boolean* disabled, *string* shortcut, *int* color): *table* item| Add a new item to ComboBox. If **disabled** parameter is specified, this item will not react to mouse clicking. You can specify .**onTouch**() function to item if desired |
| *function* | :**addSeparator**()| Add a new visual separator |
| *function* | :**removeItem**( *int*  index) | Remove item by it's index |
| *function* | :**getItem**( *int* index ): *table* item| Get item by it's index |
| *function* | :**indexOfItem**( *string* itemText ): *int* index | Get index of item by it's text (iterative method) |
| *function* | :**clear**()| Remove all items |
| *function* | :**count**(): *int* count| Get items count |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

local comboBox = mainContainer:addChild(GUI.comboBox(3, 2, 30, 3, 0xEEEEEE, 0x2D2D2D, 0xCCCCCC, 0x888888))
comboBox:addItem(".PNG")
comboBox:addItem(".JPG").onTouch = function()
	-- Do something when .JPG was selected
end
comboBox:addItem(".GIF")
comboBox:addItem(".PIC")

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i.imgur.com/6ROzLAc.gif)

GUI.**resizer**( x, y, width, height, resizerColor, arrowColor ): *table* resizer
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | resizerColor | Resizer bar color |
| *int* | arrowColor |  Arrow color, it will be shown on **touch/drag/drop** events |

This object is designed to automate the resizing of any objects. When you move the mouse pointer with the left button pressed, the resizer will call the corresponding callback methods.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *callback-function* | .**onResize**(*int* dragWidth, *int* dragHeight) | 
This function is called while moving the mouse pointer with the left button pressed on the resizer. Two parameters are the distance traveled by the mouse pointer |
| *callback-function* | .**onResizeFinished**() | This function is called after you stop moving the mouse pointer over the resizer |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

-- Add a panel that symbolizes the system window, the size of which we will change
local panel = mainContainer:addChild(GUI.panel(3, 2, 30, 10, 0xE1E1E1))
-- Add a resizer, by default located in the right part of the window. Make the width of the resizer at least 3 to handle the drag/drop events in both directions
local resizer = mainContainer:addChild(GUI.resizer(panel.localX + panel.width - 2, panel.localY + math.floor(panel.height / 2 - 2), 3, 4, 0xAAAAAA, 0x0))

-- This function will be called during the "drag" event, when the user moves over the resizer
resizer.onResize = function(dragWidth, dragHeight)
	panel.width = panel.width + dragWidth
	resizer.localX = resizer.localX + dragWidth

	mainContainer:drawOnScreen()
end

-- This function will be called on "drop" event
resizer.onResizeFinished = function()
	GUI.error("Resize finished!")
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/PvARN8j.gif)

GUI.**progressBar**( x, y, width, primaryColor, secondaryColor, valueColor, value, [thin, showValue, valuePrefix, valuePostfix] ): *table* progressBar
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | primaryColor | Object primary color |
| *int* | secondaryColor | Object secondary color |
| *int* | valueColor | Object value text color |
| *int* [0; 100] | value | Object value |
| [*bool* | thin] | Thin drawing mode |
| [*bool* | showValue] | Show value mode |
| [*string* | valuePrefix] | Object value prefix |
| [*string* | valuePostfix] | Object value postfix  |

This object is very often used when downloading files, scanning areas, blah blah blah. To whom do I tell this? You're a smart guy (girl?), aren't you?

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *int* | .**value**| Current progressbar value |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

mainContainer:addChild(GUI.progressBar(2, 2, 80, 0x3366CC, 0xEEEEEE, 0xEEEEEE, 80, true, true, "Value prefix: ", " value postfix"))

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i89.fastpic.ru/big/2017/0402/f1/ef1da27531ccf899eb9eb59c010180f1.png)

GUI.**filesystemTree**( x, y, width, height, backgroundColor, directoryColor, fileColor, arrowColor, backgroundSelectionColor, textSelectionColor, arrowSelectionColor, disabledColor, scrollBarBackground, scrollBarForeground, showMode, selectionMode ): *table* filesystemTree
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* or *nil* | backgroundColor | Object default background color |
| *int* | directoryColor | Object directories text color |
| *int* | fileColor | Object files color |
| *int* | arrowColor | Object default directories arrow color |
| *int* | backgroundSelectionColor | Object selection background color |
| *int* | textSelectionColor | Object selection text color |
| *int* | arrowSelectionColor | Object selection directories arrow color |
| *int* | disabledColor | Object extension mismatch color |
| *int* | scrollBarBackground | Object scrollBar primary color |
| *int* | scrollBarForeground | Object scrollBar secondary colo |
| *enum* | filesystemShowMode | Directory content show mode. Can be GUI.**IO_MODE_FILE**, GUI.**IO_MODE_DIRECTORY** or GUI.**IO_MODE_BOTH**
| *enum* | filesystemSelectionMode | Directory content selection mode. Can be the same values as above |

This object is intended for navigation on the filesystem via hierarchical tree. When you click on the directory, its contents will be shown, and while scrolling with the mouse wheel, the content will move in the specified direction.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *string* | .**workPath** | Current root directory |
| *string* | .**selectedItem** | Current selected item path |
| *function* | :**updateFileList**()| Update tree file list |
| *function* | :**expandPath**(*string* path)| Recursuvely expands specified path and shows it's content |
| *function* | :**addExtensionFilter**( *string* extension )| Add a filter to the specified file extension. After that, only files witch specified extension well be able to be selected |
| *callback-function* | .**onItemSelected**(*string* path) | This function is called when some item was selected |
| *callback-function* | .**onItemExpanded**(*string* path) | This function is called when some directory was expanded |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x262626))

local tree1 = mainContainer:addChild(GUI.filesystemTree(3, 2, 30, 41, 0xCCCCCC, 0x3C3C3C, 0x3C3C3C, 0x999999, 0x3C3C3C, 0xE1E1E1, 0xBBBBBB, 0xAAAAAA, 0xBBBBBB, 0x444444, GUI.IO_MODE_BOTH, GUI.IO_MODE_FILE))
tree1:updateFileList()
tree1.onItemSelected = function(path)
	GUI.error("Something was selected, the path is: \"" .. path .. "\"")
end

local tree2 = mainContainer:addChild(GUI.filesystemTree(34, 2, 30, 41, 0xCCCCCC, 0x3C3C3C, 0x3C3C3C, 0x999999, 0x3C3C3C, 0xE1E1E1, 0xBBBBBB, 0xAAAAAA, 0xBBBBBB, 0x444444, GUI.IO_MODE_FILE, GUI.IO_MODE_FILE))
tree2:updateFileList()
tree2.onItemSelected = function(path)
	GUI.error("File was selected, the path is: \"" .. path .. "\"")
end

local tree3 = mainContainer:addChild(GUI.filesystemTree(66, 2, 30, 41, 0xCCCCCC, 0x3C3C3C, 0x3C3C3C, 0x999999, 0x3C3C3C, 0xE1E1E1, 0xBBBBBB, 0xAAAAAA, 0xBBBBBB, 0x444444, GUI.IO_MODE_DIRECTORY, GUI.IO_MODE_DIRECTORY))
tree3:updateFileList()
tree3.onItemSelected = function(path)
	GUI.error("Directory was selected, the path is: \"" .. path .. "\"")
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/igGozFP.gif)

GUI.**filesystemChooser**( x, y, width, height, backgroundColor, textColor, tipBackgroundColor, tipTextColor, initialText, sumbitButtonText, cancelButtonText, placeholderText, filesystemDialogMode, filesystemDialogPath ): *table* filesystemChooser
--------------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | backgroundColor | Object background color |
| *int* | textColor | Object text color |
| *int* | tipBackgroundColor | Object "pipe" background color |
| *int* | tipTextColor | Object "pipe" text color |
| *string* | path | Initial path of and object. Can be also **nil** value, it it doesn't needed |
| *string* | sumbitButtonText | Object submit button text |
| *string* | cancelButtonText | Object cancel button text |
| *string* | placeholderText | Text that is shown when no path was typed manually |
| *enum* | filesystemDialogMode | Directory content show mode. Can be GUI.**IO_MODE_FILE**, GUI.**IO_MODE_DIRECTORY** or GUI.**IO_MODE_BOTH** |
| *string* | filesystemDialogPath | Initial directory of dialog window |

This object is intended for convenient selection of a file or directory. When you click on the object, a dialog window pops up with filesystemTree already familiar to us, allowing you to select the desired item by navigating the file system.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *callback-function* | .**onSubmit**( *string* path ) | This function is called after choosing file or directory and pressing submit button in dialog window. One single parameter is an absolute path to selected item |
| *callback-function* | .**onCancel**(  )| This function is called after pressing cancel button in dialog window |
| *function* | :**setMode**( *enum* IOMode, *enum* showMode ) | This is method for setting window mode. First parameter is needed to tell window what to do: to open or to save items. It can be GUI.**IO_MODE_OPEN**, GUI.**IO_MODE_SAVE** or GUI.**IO_MODE_BOTH**. The second one is needed to setting showing mode. It can be GUI.**IO_MODE_FILE**, GUI.**IO_MODE_FILE** or GUI.**IO_MODE_BOTH** |
| *function* | :**addExtensionFilter**( *string* extension )| Add a filter to the specified file extension. After that, only files witch specified extension well be able to be selected |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x262626))

local filesystemChooser = mainContainer:addChild(GUI.filesystemChooser(2, 2, 30, 3, 0xE1E1E1, 0x888888, 0x3C3C3C, 0x888888, nil, "Open", "Cancel", "Choose", "/"))
filesystemChooser:setMode(GUI.IO_MODE_OPEN, GUI.IO_MODE_FILE)
filesystemChooser.onSubmit = function(path)
	GUI.error("File \"" .. path .. "\" was selected")
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/F0ch8yQ.gif)

GUI.**codeView**( x, y, width, height, fromSymbol, fromLine, maximumLineLength, selections, highlights, syntaxPatterns, syntaxColorScheme, syntaxHighlight, lines ): *table* codeView
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | fromSymbol | From what symbol is drawing will start |
| *int* | fromLine |  From what lines is drawing will start |
| *int* | maximumLineLength | Length of the biggest line form **lines** table |
| *table* | selections | Table with structure {{from = {line = *int* line, symbol = *int* symbol}, to = {line = *int* line, symbol = *int* symbol}}, ...}, that allows to specify selection data just like in any text editor |
| *table* | highlights | Table with structure {[*int* lineIndex] = *int* color, ...} that allows to highlight specified lines with specified |
| *table* | syntaxPatterns | Patterns for syntax highlighting |
| *table* | syntaxColorScheme | Color scheme for syntax highlighting |
| *boolean* | syntaxHighlight | Does code syntax highlighting need to be enabled |
| *table* | lines | Table with strings that will be displayed |

This object is intended for visual display of the code with line numbers, indentations, selections, scroll bars and optional syntax highlighting.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**lines** | Table with strings displayed by widget |
| *int* | .**fromLine** | Line to display from |
| *int* | .**fromSymbol** | Symbol to display from |
| *table* | .**selections** | Table with selections |
| *table* | .**highlights** | Table with highlights |
| *boolean* | .**syntaxHighlight** | Variable to set syntax highlighting |

Example of implementation:

```lua
local GUI = require("GUI")
local unicode = require("unicode")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x0))

-- Add codeView object to main container
local codeView = mainContainer:addChild(GUI.codeView(2, 2, 72, 22, 1, 1, 1, {}, {}, GUI.LUA_SYNTAX_PATTERNS, GUI.LUA_SYNTAX_COLOR_SCHEME, true, {}))

-- Open file and read it's lines
local counter = 1
for line in io.lines("/lib/advancedLua.lua") do
	-- Replace tab symbols to 2 whitespaces and Windows line endings to UNIX line endings
	line = line:gsub("\t", "  "):gsub("\r\n", "\n")
	codeView.maximumLineLength = math.max(codeView.maximumLineLength, unicode.len(line))
	table.insert(codeView.lines, line)

	counter = counter + 1
	if counter > codeView.height then
		break
	end
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/UQJxhCn.png)

GUI.**chart**( x, y, width, height, axisColor, axisValueColor, axisHelpersColor, chartColor, xAxisValueInterval, yAxisValueInterval, xAxisPostfix, yAxisPostfix, fillChartArea, values ): *table* chart
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | axisColor | Object axis color |
| *int* | axisValueColor | Object axis values color |
| *int* | axisHelpersColor | Object axis helpers color |
| *int* | chartColor | Object chart color |
| *float* [0.0; 1.0] | xAxisValueInterval | X-axis values interval |
| *float* [0.0; 1.0] | yAxisValueInterval | Y-axis values interval |
| *string* | xAxisPostfix | X-axis values postfix |
| *string* | yAxisPostfix | Y-axis values postfix |
| *boolean* | fillChartArea | Does filling chart area is needed |
| *table* | values | Table with structure {{*float* x, *float* y}, ...} with chart values |

This object is intended for the sorted display of data in the form of a two-dimensional graph with the signed coordinate axis. Both positive and negative values are supported, but the axes are always located on the left and the bottom edges of the object.

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

local chart = mainContainer:addChild(GUI.chart(2, 2, 100, 30, 0xEEEEEE, 0xAAAAAA, 0x888888, 0xFFDB40, 0.25, 0.25, "s", "t", true, {}))
for i = 1, 100 do
	table.insert(chart.values, {i, math.random(0, 80)})
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i91.fastpic.ru/big/2017/0402/5b/66ff353492298f6a0c9b01c0fc8a525b.png)

GUI.**brailleCanvas**( x, y, width, height ): *table* brailleCanvas
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |

This object is inherently similar to a pixel canvas. Its distinctive feature is the use of Braille symbols, which creates an increased resolution in comparison with the standard resolution: each real pixel can hold up to 2x4 "mini-pixels." It's very useful for detailed rendering of small details, with which the mod can't handle. For example, if a BrailleCanvas with a size of 10x10 real pixels is created, it will contain 20x40 braille pixels.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *function* | :**set**( *int* x, *int* y, *boolean* state, [*int* color] )| Set the corresponding pixel value to the local coordinates of the BrailleCanvas. If there is already an existing pixel in this position, the value of its color will be replaced by a new one. If the color argument is not specified, then the pixel color will remain the same |
| *function* | :**get**( *int* x, *int* y ): *boolean* state, *int* color, *char* symbol | Get the state, color, and the symbol of the current braille pixel |
| *function* | :**fill**( *int* x, *int* y, *int* width, *int* height, *boolean* state, *int* color ) | Works similarly to the :**set**() method, however it allows editing entire canvas |
| *function* | :**clear**() | Clear canvas content |

Example of implementation:
```lua
local GUI = dofile("/lib/GUI.lua")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x262626))

-- Add a text label for size comparison
mainContainer:addChild(GUI.label(3, 2, 30, 1, 0xFFFFFF, "Text for size comparison"))
-- Add BrailleCanvas with 30x15 screen pixels
local brailleCanvas = mainContainer:addChild(GUI.brailleCanvas(3, 4, 30, 15))

-- Let's draw! First we will create "border" around object with two vertical lines
local canvasWidthInBraillePixels = brailleCanvas.width * 2
for i = 1, brailleCanvas.height * 4 do
	brailleCanvas:set(1, i, true, 0xFFFFFF)
	brailleCanvas:set(canvasWidthInBraillePixels, i, true, 0xFFFFFF)
end

-- After that let's add two horizontal lines
local canvasHeightInBraillePixels = brailleCanvas.height * 4
for i = 1, brailleCanvas.width * 2 do
	brailleCanvas:set(i, 1, true, 0xFFFFFF)
	brailleCanvas:set(i, canvasHeightInBraillePixels, true, 0xFFFFFF)
end

-- Now we're drawing one red diagonal
for i = 1, 60 do
	brailleCanvas:set(i, i, true, 0xFF4940)
end

-- Drawing yellow rectangle
brailleCanvas:fill(20, 20, 20, 20, true, 0xFFDB40)
-- Drawing smaller rectangle, but with pixels state = false
brailleCanvas:fill(25, 25, 10, 10, false)

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/FPWbQkv.png)

GUI.**scrollBar**( x, y, width, height, backgroundColor, foregroundColor, minimumValue, maximumValue, value, shownValueCount, onScrollValueIncrement, thinMode ): *table* scrollBar
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* | backgroundColor | Object background color |
| *int* | foregroundColor | Object text color |
| *int* | minimumValue | Object minimum value |
| *int* | maximumValue | Object maximum value |
| *int* | value | Object current value |
| *int* | shownValueCount | Object shown value count (per "page") |
| *int* | onScrollValueIncrement | Value increment on **scroll** event |
| *boolean* | thinMode | Thin drawing mode |

This object is intended for visual demonstration of the number of displayed objects on the screen. Itself is practically not used, useful in combination with other widgets.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *float* | .**value** | Current object value variable |
| *callback-function* | .**onTouch**( )| This function is called after touching scrollBar. It's .**value** will be calculated automatically |
| *callback-function* | .**onScroll**( )| This function is called on scrolling via mouse. Object .**value** will be changed by .**onScrollValueIncrement** |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

-- Add vertical scrollBar to main container
local verticalScrollBar = mainContainer:addChild(GUI.scrollBar(2, 3, 1, 15, 0x444444, 0x888888, 1, 100, 1, 10, 1, true))
verticalScrollBar.onTouch = function()
	GUI.error("Vertical scrollbar was touched")
end

-- Add horizontal too
local horizontalScrollBar = mainContainer:addChild(GUI.scrollBar(3, 2, 60, 1, 0x444444, 0x888888, 1, 100, 1, 10, 1, true))
horizontalScrollBar.onTouch = function()
	-- Do something on scrollBar touch
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](https://i.imgur.com/XrqDvBk.png)

GUI.**textBox**(x, y, width, height, backgroundColor, textColor, lines, currentLine, horizontalOffset, verticalOffset, [autoWrap, autoHeight]): *table* textBox
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |
| *int* or *nil* | backgroundColor | Object background color. Can be **nil** to be ignored |
| *int* | textColor | Object text color |
| *table* | lines | Table with textBox strings. There is also alternative option to set line color: line must be a table with structure: {text = *string*, color = *int*}  |
| *int* | currentLine | Current line to draw with |
| *int* | horizontalOffset | Horizontal offset from left and right borders |
| *int* | verticalOffset | Vertical offset from top and bottom borders |
| [*boolean* | autoWrap] | Optional automatic text wrapping by textBoxWidth |
| [*boolean* | autoHeight] | Optional automatic object height calculation to fit lines table |

This object is designed to display a large amount of text data in a small container with scroll bars. When using the mouse wheel and activating the **scroll** event, the contents of the textbox will automatically "scroll" in the desired direction. There's also feature of setting desired alignment.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**lines**| Pointer to table with object strings |
| *int* | .**currentLine**| Current line to draw with |
| *boolean* | .**autoWrap**| Automatic text wrapping mode |
| *boolean* | .**autoHeight**| Automatic height calculation mode |
| *boolean* | .**scrollBarEnabled**| Scrollbar showing state |
| *function* | :**scrollUp**([*int* count]): *table* textBox| Scroll textBox up to specified about of lines (1 by default) |
| *function* | :**scrollDown**([*int* count]): *table* textBox| Scroll textBox down to specified about of lines (1 by default) |
| *function* | :**scrollToStart**(): *table* textBox| Scroll textBox to start |
| *function* | :**scrollToEnd**(): *table* textBox| Scroll textBox to end |
| *function* | :**setAlignment**(*enum* horizontalAlignment, *enum* verticalAlignment): *table* textBox| Choose a text display option for textBox boundaries |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local mainContainer = GUI.fullScreenContainer()
mainContainer:addChild(GUI.panel(1, 1, mainContainer.width, mainContainer.height, 0x2D2D2D))

local textBox = mainContainer:addChild(GUI.textBox(2, 2, 32, 16, 0xEEEEEE, 0x2D2D2D, {}, 1, 1, 0))
table.insert(textBox.lines, {text = "Sample colored line ", color = 0x880000})
for i = 1, 100 do
	table.insert(textBox.lines, "Sample line " .. i)
end

--------------------------------------------------------------------------------

mainContainer:drawOnScreen(true)
mainContainer:startEventHandling()
```

Result:

![](http://i89.fastpic.ru/big/2017/0402/ad/01cdcf7aec919051f64ac2b7d9daf0ad.png)

Ready-to-use containers
======

The widgets are listed below comes with the library and are written on the instructions of this documentation. If you want, you can make absolutely similar or much more technically advanced widgets without any difficulties.

GUI.**layout**(x, y, width, height, columnCount, rowCount): *table* layout
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Layout coordinate by x-axis |
| *int* | y | Layout coordinate by y-axis |
| *int* | width | Layout width |
| *int* | height | Layout height |
| *int* | columnCount | Layout grid column count |
| *int* | rowCount | Layout grid row count |

This is one of the most useful and technically advanced widgets. Layout is an inheritor
 of the GUI.**container** with similar behavior that can automatically calculate position of child objects within itself. For example, if you want to beautifully display a lot of objects without wasting time on manual calculation of coordinates, then layout is made for you. Picture below shows in detail the layout structure of 4x2:

![Imgur](https://i.imgur.com/JgIlilp.png)

As you can see, there is 8 cells in this example, each of which can have its own direction, distance between objects, alignment and margin. The boundaries of the cells are **illusive**, so child objects can easily go beyond them, if cell alignment allows it.

Each column and row can be assigned its own individual size either in pixels or in relative (percentage) value, so working with layout is fantastically convenient.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *int* | .**children** | Table that contains all child objects of this container |

Example of implementation:

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
