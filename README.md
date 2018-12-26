
About
======

GUI is a multifunctional graphics library, especially designed and optimized for low-performance computers. You can realize all of your most perverted fantasies using it: from regular buttons, sliders and charts to complex animated interfaces. Extreme performance of the library is achieved by using double buffering and complex color grouping and processing algorithms.

For example, my OS, IDE and 3D-engine are fully implemented by the methods of this library:

![](https://i.imgur.com/Ki5bX0I.gif)

![](http://i.imgur.com/tHAiTmF.gif)

Let the abundance of text below not frighten you: this documentation has many illustrated examples with full working code.

| Contents |
| ----- |
| [Installation](#installation) |
| [Objects](#objects) |
| [Containers](#containers) |
| [Applications](#applications) |
| [Animations](#animations) |
| [Constants](#constants) |
| [Ready-to-use objects:](#ready-to-use-objects) |
| [   GUI.object](#guiobjectx-y-width-height) |
| [   GUI.container](#guicontainerx-y-width-height-extends-guiobject) |
| [   GUI.application](#guiapplicationx-y-width-height-extends-guicontainer) |
| [   GUI.panel](#guipanelx-y-width-height-color-transparency-extends-guiobject) |
| [   GUI.text](#guitextx-y-textcolor-text-extends-guiobject) |
| [   GUI.label](#guilabelx-y-width-height-textcolor-text-extends-guiobject) |
| [   GUI.image](#guiimage-x-y-loadedimage--extends-guiobject) |
| [   GUI.button](#guibuttonx-y-width-height-buttoncolor-textcolor-buttonpressedcolor-textpressedcolor-text-extends-guiobject) |
| [   GUI.actionButtons](#guiactionbuttonsx-y-fat-extends-guiobject) |
| [   GUI.input](#guiinputx-y-width-height-backgroundcolor-textcolor-placeholdertextcolor-backgroundfocusedcolor-textfocusedcolor-text-placeholdertext-erasetextonfocus-textmask-extends-guiobject) |
| [   GUI.slider](#guisliderx-y-width-primarycolor-secondarycolor-pipecolor-valuecolor-minimumvalue-maximumvalue-value-showcornervalues-currentvalueprefix-currentvaluepostfix-extends-guiobject) |
| [   GUI.switch](#guiswitchx-y-width-primarycolor-secondarycolor-pipecolor-state-extends-guiobject) |
| [   GUI.switchAndLabel](#guiswitchandlabelx-y-width-switchwidth-primarycolor-secondarycolor-pipecolor-textcolor-text-switchstate-extends-guicontainer) |
| [   GUI.colorSelector](#guicolorselectorx-y-width-height-color-text-extends-guiobject) |
| [   GUI.list](#guilistx-y-width-height-itemsize-spacing-backgroundcolor-textcolor-alternatebackgroundcolor-alternatetextcolor-backgroundselectedcolor-textselectedcolor-offsetmode-extends-guilayout) |
| [   GUI.menu](#guimenux-y-width-backgroundcolor-textcolor-backgroundpressedcolor-textpressedcolor-backgroundtransparency-extends-guilayout) |
| [   GUI.comboBox](#guicomboboxx-y-width-elementheight-backgroundcolor-textcolor-arrowbackgroundcolor-arrowtextcolor-extends-guiobject) |
| [   GUI.resizer](#guiresizerx-y-width-height-resizercolor-arrowcolor-extends-guiobject) |
| [   GUI.progressBar](#guiprogressbarx-y-width-primarycolor-secondarycolor-valuecolor-value-thin-showvalue-valueprefix-valuepostfix-extends-guiobject) |
| [   GUI.filesystemTree](#guifilesystemtreex-y-width-height-backgroundcolor-directorycolor-filecolor-arrowcolor-backgroundselectioncolor-textselectioncolor-arrowselectioncolor-disabledcolor-scrollbarbackground-scrollbarforeground-showmode-selectionmode-extends-guiobject) |
| [   GUI.filesystemChooser](#guifilesystemchooserx-y-width-height-backgroundcolor-textcolor-tipbackgroundcolor-tiptextcolor-initialtext-sumbitbuttontext-cancelbuttontext-placeholdertext-filesystemdialogmode-filesystemdialogpath-extends-guiobject) |
| [   GUI.codeView](#guicodeviewx-y-width-height-fromsymbol-fromline-maximumlinelength-selections-highlights-syntaxpatterns-syntaxcolorscheme-syntaxhighlight-lines-extends-guiobject) |
| [   GUI.chart](#guichartx-y-width-height-axiscolor-axisvaluecolor-axishelperscolor-chartcolor-xaxisvalueinterval-yaxisvalueinterval-xaxispostfix-yaxispostfix-fillchartarea-values-extends-guiobject) |
| [   GUI.brailleCanvas](#guibraillecanvasx-y-width-height-extends-guiobject) |
| [   GUI.scrollBar](#guiscrollbarx-y-width-height-backgroundcolor-foregroundcolor-minimumvalue-maximumvalue-value-shownvaluecount-onscrollvalueincrement-thinmode-extends-guiobject) |
| [   GUI.textBox](#guitextboxx-y-width-height-backgroundcolor-textcolor-lines-currentline-horizontaloffset-verticaloffset-autowrap-autoheight-extends-guiobject) |
| [   GUI.layout](#guilayoutx-y-width-height-columncount-rowcount-extends-guicontainer) |
| [   GUI.window](#guiwindowx-y-width-height-extends-guicontainer) |
| [   GUI.filledWindow](#guifilledwindowx-y-width-height-fillcolor-extends-guiwindow) |
| [   GUI.titledWindow](#guititledwindowx-y-width-height-title-addtitlepanel-extends-guiwindow) |
| [   GUI.tabbedWindow](#guitabbedwindowx-y-width-height-extends-guiwindow) |
| [   GUI.palette](#guipalettex-y-initialcolor-extends-guiwindow) |
| [   GUI.alert](#guialertvarargs) |
| [   GUI.addContextMenu](#guiaddcontextmenuparentcontainer-x-y-backgroundcolor-textcolor-backgroundpressedcolor-textpressedcolor-disabledcolor-separatorcolor-backgroundtransparency-shadowtransparency) |
| [   GUI.addFilesystemDialog](#guiaddfilesystemdialogparentcontainer-addpanel-) |
| [   GUI.addBackgroundContainer](#guiaddbackgroundcontainerparentcontainer-addpanel-addlayout-title) |
| [   GUI.highlightString](#guihighlightstringx-y-width-fromsymbol-indentationwidth-syntaxpatterns-syntaxcolorscheme-data) |
| [   GUI.getAlignmentCoordinates](#guigetalignmentcoordinatesfirstobjectx-firstobjecty-firstobjectwidth-firstobjectheight-firstobjecthorizontalalignment-firstobjectverticalalignment-secondobjectwidth-secondobjectheight-int-x-int-y) |
| [   GUI.getMarginCoordinates](#guigetmargincoordinatesx-y-horizontalalignment-verticalalignment-horizontalmargin-verticalmargin-int-x-int-y) |
| [Practical example #1: Creating an animated widget](#practical-example--1-creating-an-animated-widget) |

Installation
======

The easiest way is to use automatic [installer](https://pastebin.com/ryhyXUKZ) that will download all necessary files for you via single command:

    pastebin run ryhyXUKZ
    
However, you can download dependencies manually, if required. They are listed in the following table:

| Dependency | Description | Documentation |
| ------ | ------ | ------ |
| *[GUI](https://github.com/IgorTimofeev/GUI/blob/master/GUI.lua)* | This library | - | 
| *[advancedLua](https://github.com/IgorTimofeev/AdvancedLua/blob/master/AdvancedLua.lua)* | Addition to standard Lua libraries with a variety of functions: fast table serialization, text wrapping, binary data processing, etc. | [https://github.com/Igor...](https://github.com/IgorTimofeev/AdvancedLua/blob/master/README.md) | 
| *[color](https://github.com/IgorTimofeev/Color/blob/master/Color.lua)* | Extrusion and packaging of color channels, conversion of the RGB color model to HSB and vice versa, the implementation of alpha blending, the generation of color transitions and the conversion of color into an 8-bit format for the OpenComputers palette | [https://github.com/Igor...](https://github.com/IgorTimofeev/Color/blob/master/README.md) | 
| *[doubleBuffering](https://github.com/IgorTimofeev/DoubleBuffering/blob/master/DoubleBuffering.lua)* | Double buffering of the graphic context and various methods of primitives rasterizing | [https://github.com/Igor...](https://github.com/IgorTimofeev/Color/blob/master/README.md) | 
| *[image](https://github.com/IgorTimofeev/Image/blob/master/Image.lua)* | Implementation of the image standard for OpenComputers and basic methods of their processing: transpose, crop, rotate, reflection, etc. | - | 
| *[OCIF](https://github.com/IgorTimofeev/Image/blob/master/OCIF.lua)* | The OpenComputers Image Format module for the image library, written with regard to the features of the mod and realizing effective compression of pixel data | - | 

Objects
======

The library is divided into three main concepts: applications, containers and widgets. Applications are designed for launching your cool interfaces and handling computer events when user touches the screen, presses some keys, etc. Containers are designed for grouping widgets and processing their positions. Widgets are designed for displaying different stuff: they can represent buttons, scrollbars, sliders, etc. 

First let's talk about objects. Every GUI.**object** is a rectangular entity with it's own width and height, it's used as a template for any other stuff like containers and applications. You can easily create object via this method:

GUI.**object**(x, y, width, height)
-----------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| *int* | width | Object width |
| *int* | height | Object height |

Every created object and it's extended classes have several universal properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *int* | .**x** | Current screen rendering coordinate of object by x-axis |
| *int* | .**y** | Current screen rendering coordinate of object by y-axis |
| *int* | .**width** | Object width |
| *int* | .**height** | Object height |
| *boolean* | .**hidden** | Whether the object is hidden. If the object is hidden, then its rendering and analysis of system events are ignored |
| *boolean* | .**disabled** | Whether the object is disabled. If the object is disabled, then it can be rendered, but all system events are ignored |
| *boolean* | .**passScreenEvents** | Optional variable that allows screen events to pass througs objects withount being processed |
| *function* | :**draw**(*table* object) | Main method that is called to render this object on the screen. It can be defined by the user in any convenient way |

Here is example of implementation of simple rectangle object. Don't worry if you don't understand what "application" or "container" means, it's just an template for copy-pasting, just read two sections below and everything will be OK:

```lua
-- Import this library
local GUI = require("GUI")
-- We will also need downloaded double buffering library to render rectangles
local buffer = require("doubleBuffering")

--------------------------------------------------------------------------------

-- Create new application
local application = GUI.application()

-- Create and add template object to application
local object = application:addChild(GUI.object(3, 2, 50, 10))
-- Create own :draw() method and make it render green rectangle
object.draw = function(object)
	buffer.drawRectangle(object.x, object.y, object.width, object.height, 0x33FF80, 0x0, " ")
end

--------------------------------------------------------------------------------

-- Draw application content once on screen when program starts
application:draw(true)
-- Start processing events for application
application:start()
```

As a result, we will get a nice green rectangle:

![](https://i.imgur.com/VBrEdyx.png)

Containers
======

Now let's talk about containers. Container is a object that can store some other objects inside itself, its behavior is very similar to a folder that contains a some nested files and other folders. You can easily create empty container via this method:

GUI.**container**(x, y, width, height) extends GUI.**object**
-----------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Container's coordinate by x-axis |
| *int* | y | Container's coordinate by y-axis |
| *int* | width | Container's width |
| *int* | height | Container's height |

All container child objects are stored in container.**children** table. To add an object to the container, use the following method:

```lua
container:addChild(<Object>)
```

After adding any object to container using :**addChild()** method, the object will acquire additional properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**parent** | A pointer to the parent container of the object |
| *table* | .**firstParent** | A pointer to the first created container in children hierarchy. For exmaple, if there are many nested containers on screen, this field corresponds to the first of them (most of the time it's an GUI.**application**) |
| *int* | .**localX** | Local position on the x-axis in the parent container |
| *int* | .**localY** | Local position on the y-axis in the parent container |
| *function* | :**indexOf**() | Get the index of this object in the parent container (iterative method) |
| *function* | :**moveForward**() | Move the object "back" in the container children hierarchy |
| *function* | :**moveBackward**() | Move the object "forward" in the container children hierarchy |
| *function* | :**moveToFront**() | Move the object to the end of the container children hierarchy |
| *function* | :**moveToBack**() | Move the object to the beginning of the container children hierarchy |
| *function* | :**remove**() | Remove this object from the parent container. Roughly speaking, this is a convenient way of self-destruction |
| *function* | :**addAnimation**(*function* frameHandler, *function* onFinish): *table* animation | Add an animation to this object, see below |
| [*callback-function* | .**eventHandler**(*container* application, *object* object, ... *varargs* eventData) ]| An optional method for handling system events, called by the parent container handler. If it exists in the object under consideration, it will be called with the appropriate arguments |

Let's pay attention on object.**localX** and object.**localY** properties. They're represents local position of child object inside parent container. There's a difference from object.**x** and object.**y**: they're represents *current position of object on screen* and are being calculated automatically for performing drawing operations. But most of the time the developer will work with local position. The hierarchy and positioning of container's children is well presented in the following image:

![](https://i.imgur.com/MQCNRbd.png?1

Containers also have an important feature: any child that extends beyond the bounds of the container will be rendered only within the size of this container:

![](https://i.imgur.com/SBuL1it.png)

Of course, you can add to container another container, add a new ones to the added ones, creating complex hierarchy and grouping the child objects at your will.

Every container has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**children** | Table that contains all child objects of this container |
| *function* | :**addChild**(*table* child[, *int* atIndex]): *table* child| Add specified object to the container as a child. When you do this, the object's global coordinates will become local. If the optional parameter **atIndex** is specified, then the element will be added to the corresponding position in container.**children** table |
| *function* | :**removeChildren**([*int* fromIndex, *int* toIndex]) | Remove all child elements of the container. If the optional parameters of the element indices are specified, the deletion will be performed in the appropriate range |

Applications
======

Finally, let's talk about applications. Every application is full screen container that can automatically handle computer events. For example, it allows buttons to be pressed when user interacts with screen and it allows text fields receive data from the keyboard.

GUI.**application**([x, y, width, height]) extends GUI.**container**
-----------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| [*int* | x] | Optional coordinate by x-axis |
| [*int* | y] | Optional coordinate by y-axis |
| [*int* | width] | Optional width |
| [*int* | height] | Optional height |

Every application can be launched and start processing events. To do this, use the following:

```lua
application:start([delay])
```

If event application should be terminated, use the following:
```lua
application:stop()
```

Once the application receives the event, it recursively analyzes itself and all child objects for the .**eventHandler** function. If the child object has this function, then it runs with following parameters:

```lua
object.eventHandler = function(application, object, ...eventData)
    ...
end
```

The first parameter is a pointer to the application, the second is a pointer to the child object event handler belongs to, and the rest is the set of event parameters just like computer.**pullSignal**() do. For example, the "touch" event will call .**eventHandler** with 8 arguments:

| Argument | Description |
| ------ | ------ |
| table | Pointer to application object |
| table | Pointer to event handler object |
| "touch" | Event type |
| "7842f8..." | Screen address |
| 13 | Screen x |
| 21 | Screen y |
| 0 | Mouse button |
| "ECS" | Username |

The important detail of the event handlers is that if the event belongs to **screen** (touch, drag, drop, scroll), then the child object event handler will be called, and event processing for the remaining unprocessed child objects will be finished.

If you want to skip some event during event processing, call :**consumeEvent**() method. This will prevent all unprocessed child objects to handle current event data.

There is also an option to make any object **transparent** for screen events: just set .**passScreenEvents** = **true** variable for desired object. With this option it's event hanlder will be called as always, but event processing will continue for rest objects in container. This feature works with containers too.

And if the event does not belong to the screen, or the object **does not have** event handler method, the processing of the remaining child elements will continue as always. You can see the logic and the order of event processing in the following image:

![](https://i.imgur.com/iLYlSBo.png?1)

Every application has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *function* | :**start**([*float* delay]) | Run the event processing for this container and analyse events for all it's child objects. The  **delay** parameter is similar to computer.**pullSignal** one |
| *function* | :**stop**() | Stop processing events for this container |
| *function* | :**consumeEvent**() | Consume currently processing event and skip it's handling for rest unprocessed child objects |

Below is a classic example of the implementation of the application:

```lua
-- Import the library
local GUI = require("GUI")

--------------------------------------------------------------------------------

-- Create new application
local application = GUI.application()

-- Create simple event handler for it
application.eventHandler = function(application, object, ...)
    print("It works! The event data was: ", ...)
end

--------------------------------------------------------------------------------

-- Start processing events for application
application:start()
```

As a result, you will get an amusing output of event data to the terminal:

![](https://i.imgur.com/6xpX9L9.gif)

Animations
======

The next feature of an objects is animations: every object can be animated. For more information about creating animations, see practical examples in end of this documentation. By the way, here is field of animated GUI.**switch** objects:

![](http://i.imgur.com/f5aO73U.gif)

As described above, to add an animation to object, call <object>:**addAnimation**(...) function. It will return an animation object which has the following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**object** | A pointer to the widget which contains this animation |
| *float* | .**position** | Current animation playback position. It is always in **[0.0; 1.0]** range, where **0.0** is animation starting and **1.0** is animation ending |
| *function* | :**start**() | Start animation playback. Interesting detail: during animation playing an application which has some animated objects will temporary handle events with maximum available speed (i.e. like computer.**pullSignal**(0)). After finishing all animations, event handling delay will be the same it was in beginning |
| *function* | :**stop**() | Stop animation playback |
| *function* | :**remove**() | Remove animation from it's widget |
| *callback-function* | .**frameHandler**(*table* animation) | An animation frame handler. It is called every frame before drawing stuff to screen buffer. A single parameter is a pointer to animation object |
| *callback-function* | .**onFinish**() | This function is called after finishing animation playback. Important: calling :**stop**() will **not** call this function |

Constants
======

This is a rather boring section of the documentation, but it is still necessary for learning. The library has several universal constants, with which some objects are oftenly working. For example, if you want to centerize the text on the screen, you will need alignment constants. If you want to change object's direction - use direction constants, and so on.

| Type | Constant | Description |
| ------ | ------ | ------ |
| *enum* | GUI.**ALIGNMENT_HORIZONTAL_LEFT** | Align something to left side horizontally |
| *enum* | GUI.**ALIGNMENT_HORIZONTAL_CENTER** | Align something to center side horizontally |
| *enum* | GUI.**ALIGNMENT_HORIZONTAL_RIGHT** | Align something to right side horizontally |
| *enum* | GUI.**ALIGNMENT_VERTICAL_TOP** | Align something to top side vertically |
| *enum* | GUI.**ALIGNMENT_VERTICAL_CENTER** | Align something to center vertically |
| *enum* | GUI.**ALIGNMENT_VERTICAL_BOTTOM** | Align something to bottom side vertically |
| *enum* | GUI.**DIRECTION_HORIZONTAL** | Horizontal direction of something |
| *enum* | GUI.**DIRECTION_VERTICAL** | Vertical direction of something |
| *enum* | GUI.**SIZE_POLICY_ABSOLUTE** | Calculate sizes of something as absolute values |
| *enum* | GUI.**SIZE_POLICY_RELATIVE** | Calculate sizes of something as relative (percentage) values |
| *enum* | GUI.**IO_MODE_FILE** | Mode for working with files |
| *enum* | GUI.**IO_MODE_DIRECTORY** | Mode for working with directories |
| *enum* | GUI.**IO_MODE_BOTH** | Mode for working with bothly files and directories |
| *enum* | GUI.**IO_MODE_OPEN** | Mode for opening data |
| *enum* | GUI.**IO_MODE_SAVE** | Mode for saving data |

Still not tired? Now think how I fucked up writing them during the library development. Shitty constants...

| Type | Constant | Value | Description |
| ------ | ------ | ------ | ------ |
| *float* | GUI.**BUTTON_PRESS_DURATION** | 0.2 | Button pressing duration with disabled animation |
| *float* | GUI.**BUTTON_ANIMATION_DURATION** | 0.2 | Button pressing animation duration |
| *float* | GUI.**SWITCH_ANIMATION_DURATION** | 0.3 | Switch state changing animation duration |
| *float* | GUI.**FILESYSTEM_DIALOG_ANIMATION_DURATION** | 0.5 | Filesystem dialog showing animation duration |
| *int* | GUI.**CONTEXT_MENU_SEPARATOR_COLOR** | 0x878787 | Context menu separator color |
| *int* | GUI.**CONTEXT_MENU_DEFAULT_TEXT_COLOR** | 0x2D2D2D | Context menu default item text color |
| *int* | GUI.**CONTEXT_MENU_DEFAULT_BACKGROUND_COLOR** | 0xFFFFFF | Context menu default item background color |
| *int* | GUI.**CONTEXT_MENU_PRESSED_BACKGROUND_COLOR** | 0x3366CC | Context menu default item background color |
| *int* | GUI.**CONTEXT_MENU_PRESSED_TEXT_COLOR** | 0xFFFFFF | Context menu default item text color |
| *int* | GUI.**CONTEXT_MENU_DISABLED_COLOR** | 0x878787 | Context menu disabled item text color |
| *float* | GUI.**CONTEXT_MENU_BACKGROUND_TRANSPARENCY** | 0.24 | Context menu background transparency |
| *float* | GUI.**CONTEXT_MENU_SHADOW_TRANSPARENCY** | 0.4 | Context menu shadow transparency |
| *int* | GUI.**BACKGROUND_CONTAINER_PANEL_COLOR** | 0x0 | Background container panel color |
| *int* | GUI.**BACKGROUND_CONTAINER_TITLE_COLOR** | 0xE1E1E1 | Background container title color |
| *float* | GUI.**BACKGROUND_CONTAINER_PANEL_TRANSPARENCY** | 0.3 | Background container panel transparency |
| *int* | GUI.**WINDOW_BACKGROUND_PANEL_COLOR** | 0xF0F0F0 | Window background panel color |
| *float* | GUI.**WINDOW_SHADOW_TRANSPARENCY** | 0.6 | Window shadow transparency |
| *int* | GUI.**WINDOW_TITLE_BACKGROUND_COLOR** | 0xE1E1E1 | Window title background color |
| *int* | GUI.**WINDOW_TITLE_TEXT_COLOR** | 0x2D2D2D | Window title text color |
| *int* | GUI.**WINDOW_TAB_BAR_DEFAULT_BACKGROUND_COLOR** | 0x2D2D2D | Window tab bar default background color |
| *int* | GUI.**WINDOW_TAB_BAR_DEFAULT_TEXT_COLOR** | 0xF0F0F0 | Window tab bar default text color |
| *int* | GUI.**WINDOW_TAB_BAR_SELECTED_BACKGROUND_COLOR** | 0xF0F0F0 | Window tab bar selected background color |
| *int* | GUI.**WINDOW_TAB_BAR_SELECTED_TEXT_COLOR** | 0x2D2D2D | Window tab bar selected text color |
| *string* | GUI.**PALETTE_CONFIG_PATH** | "/lib/.palette.cfg" | Path where GUI.**palette** favourites colors are being saved |
| *table* | GUI.**LUA_SYNTAX_PATTERNS** | {...} | Required patterns for Lua syntax highlighting by GUI.**highlightString**(...) method |
| *table* | GUI.**LUA_SYNTAX_COLORS** | {...} | Default color scheme for Lua syntax highlighting by GUI.**highlightString**(...) method |

![](https://i.imgur.com/x0Cti52.jpg?2)

Ready-to-use objects
======

The objects are listed below comes with the library and are written on the instructions of this documentation. If you want, you can make absolutely similar or much more technically advanced widgets without any difficulties.

GUI.**panel**(x, y, width, height, color[, transparency]) extends GUI.**object**
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

-- Create new application
local application = GUI.application()

-- Add panel that fits application
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x262626))
-- Add smaller red panel
application:addChild(GUI.panel(10, 10, application.width - 20, application.height - 20, 0x880000))

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i.imgur.com/Rho1RTl.png?1)

GUI.**text**(x, y, textColor, text) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

application:addChild(GUI.text(3, 2, 0xFFFFFF, "Hello, world!"))
application:addChild(GUI.text(3, 3, 0xFFFFFF, "How are you? Wanna cast some EEWRD meatballs?"))

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/ygqLguM.png)

GUI.**label**(x, y, width, height, textColor, text) extends GUI.**object**
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

| Type | Property | Description |
| ------ | ------ | ------ |
| *function* | :**setAlignment**(*enum* horizontalAlignment, *enum* verticalAlignment): *table* label| Choose a text display option for label boundaries |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

application:addChild(GUI.label(1, 1, application.width, application.height, 0xFFFFFF, "Label with [left, top] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_LEFT, GUI.ALIGNMENT_VERTICAL_TOP)
application:addChild(GUI.label(1, 1, application.width, application.height, 0xFFFFFF, "Label with [center, top] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_CENTER, GUI.ALIGNMENT_VERTICAL_TOP)
application:addChild(GUI.label(1, 1, application.width, application.height, 0xFFFFFF, "Label with [right, top] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_RIGHT, GUI.ALIGNMENT_VERTICAL_TOP)
application:addChild(GUI.label(1, 1, application.width, application.height, 0xFFFFFF, "Label with [left, center] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_LEFT, GUI.ALIGNMENT_VERTICAL_CENTER)
application:addChild(GUI.label(1, 1, application.width, application.height, 0xFFFFFF, "Label with [center, center] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_CENTER, GUI.ALIGNMENT_VERTICAL_CENTER)
application:addChild(GUI.label(1, 1, application.width, application.height, 0xFFFFFF, "Label with [right, center] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_RIGHT, GUI.ALIGNMENT_VERTICAL_CENTER)
application:addChild(GUI.label(1, 1, application.width, application.height, 0xFFFFFF, "Label with [left, bottom] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_LEFT, GUI.ALIGNMENT_VERTICAL_BOTTOM)
application:addChild(GUI.label(1, 1, application.width, application.height, 0xFFFFFF, "Label with [center, bottom] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_CENTER, GUI.ALIGNMENT_VERTICAL_BOTTOM)
application:addChild(GUI.label(1, 1, application.width, application.height, 0xFFFFFF, "Label with [right, bottom] alighment")):setAlignment(GUI.ALIGNMENT_HORIZONTAL_RIGHT, GUI.ALIGNMENT_VERTICAL_BOTTOM)

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/ftonciY.png)

GUI.**image**( x, y, loadedImage ) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

-- Load image, create widget from it and add it to application
application:addChild(GUI.image(2, 2, image.load("/Furnance.pic")))

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i91.fastpic.ru/big/2017/0402/80/3b0ec81c3b2f660b9a4c6f18908f4280.png)

GUI.**button**(x, y, width, height, buttonColor, textColor, buttonPressedColor, textPressedColor, text) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

-- Add a regular button
local regularButton = application:addChild(GUI.button(2, 2, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Regular button"))
regularButton.onTouch = function()
	GUI.alert("Regular button was pressed")
end

-- Add a regular button with disabled state
local disabledButton = application:addChild(GUI.button(2, 6, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Disabled button"))
disabledButton.disabled = true

-- Add a regular button with switchMode state
local switchButton = application:addChild(GUI.button(2, 10, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Switch button"))
switchButton.switchMode = true
switchButton.onTouch = function()
	GUI.alert("Switch button was pressed")
end

-- Add a regular button with disabled animation
local notAnimatedButton = application:addChild(GUI.button(2, 14, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Not animated button"))
notAnimatedButton.animated = false
notAnimatedButton.onTouch = function()
	GUI.alert("Not animated button was pressed")
end

-- Add a rounded button
application:addChild(GUI.roundedButton(2, 18, 30, 3, 0xFFFFFF, 0x555555, 0x880000, 0xFFFFFF, "Rounded button")).onTouch = function()
	GUI.alert("Rounded button was pressed")
end

-- Add a framed button
application:addChild(GUI.framedButton(2, 22, 30, 3, 0xFFFFFF, 0xFFFFFF, 0x880000, 0x880000, "Framed button")).onTouch = function()
	GUI.alert("Framed button was pressed")
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/Q2sX0P5.gif)

GUI.**actionButtons**(x, y[, fat]) extends GUI.**object**
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Object coordinate by x-axis |
| *int* | y | Object coordinate by y-axis |
| [*boolean* | fat] | The option of drawing buttons with a large size |

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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

local actionButtonsRegular = application:addChild(GUI.actionButtons(3, 2, false))
local actionButtonsFat = application:addChild(GUI.actionButtons(3, 4, true))

actionButtonsRegular.close.onTouch = function()
	-- Do something when "close" button was touched
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/lYUS7fl.png)

GUI.**input**(x, y, width, height, backgroundColor, textColor, placeholderTextColor, backgroundFocusedColor, textFocusedColor, text[, placeholderText, eraseTextOnFocus, textMask]) extends GUI.**object**
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
| [*boolean* | eraseTextOnFocus] | Erase text when the input is focused |
| [*char* | textMask] | A mask character for the text to be entered. Convenient for creating a password entry field |

The input object is intended for input and analysis of text data from the keyboard. Pasting data from real clipboard is also supported. You can move the cursor with clicks or left and right arrows. Clicking on the object starts the process of entering text, and pressing Enter or clicking on an empty zone on the screen will finish it.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *string* | .**text** | A variable that contains current displayed text of an object |
| *boolean* | .**historyEnabled** | Optional property that allows widget to remember text that user inputs and to navigate through it's history via arrows buttons. Set to **false** by default |
| *function* | :**startInput**() | Method for activation of text inputting |
| *callback-function* | .**validator**(*string* text) | The function that is called after the text is entered in the input field. If it returns **true**, the text in the text field will be changed to the entered text, otherwise the entered data will be ignored |
| *callback-function* | .**onInputFinished**() | The function that is called after entering data in the input field: it's a handy thing if you want to do something after entering text. If the object has .**validator** function, and if the text does not pass the check through it, then .**onInputFinished** will not be called |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

application:addChild(GUI.input(2, 2, 30, 3, 0xEEEEEE, 0x555555, 0x999999, 0xFFFFFF, 0x2D2D2D, "Hello world", "Placeholder text")).onInputFinished = function()
	GUI.alert("Input finished!")
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i.imgur.com/njPN0eg.gif)

GUI.**slider**(x, y, width, primaryColor, secondaryColor, pipeColor, valueColor, minimumValue, maximumValue, value[, showCornerValues, currentValuePrefix, currentValuePostfix]) extends GUI.**object**
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
| *callback-function* | .**onValueChanged**() | This function will be called after slider value changing |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

local slider = application:addChild(GUI.slider(4, 2, 30, 0x66DB80, 0x0, 0xFFFFFF, 0xAAAAAA, 0, 100, 50, true, "Prefix: ", " postfix"))
slider.roundValues = true
slider.onValueChanged = function()
	-- Do something when slider's value changed
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i.imgur.com/F7jrTPM.gif)

GUI.**switch**(x, y, width, primaryColor, secondaryColor, pipeColor, state) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

local switch1 = application:addChild(GUI.switch(3, 2, 8, 0x66DB80, 0x1D1D1D, 0xEEEEEE, true))
local switch2 = application:addChild(GUI.switch(3, 4, 8, 0x66DB80, 0x1D1D1D, 0xEEEEEE, false))
switch2.onStateChanged = function(state)
	GUI.alert("Switch state changed!")
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i.imgur.com/prBIAsL.gif)

GUI.**switchAndLabel**(x, y, width, switchWidth, primaryColor, secondaryColor, pipeColor, textColor, text, switchState) extends GUI.**container**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

application:addChild(GUI.switchAndLabel(2, 2, 25, 8, 0x66DB80, 0x1D1D1D, 0xEEEEEE, 0x999999, "Sample text 1:", true))
application:addChild(GUI.switchAndLabel(2, 4, 25, 8, 0x66DB80, 0x1D1D1D, 0xEEEEEE, 0x999999, "Sample text 2:", false))

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i.imgur.com/4zKOla9.gif)

GUI.**colorSelector**(x, y, width, height, color, text) extends GUI.**object**
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
| *callback-function* | .**onColorSelected**() | This function will be called after choosing color from palette |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

application:addChild(GUI.colorSelector(2, 2, 30, 3, 0xFF55FF, "Choose color")).onColorSelected = function()
	-- Do something after choosing color
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i.imgur.com/QVxu2N0.gif)

GUI.**list**(x, y, width, height, itemSize, spacing, backgroundColor, textColor, alternateBackgroundColor, alternateTextColor, backgroundSelectedColor, textSelectedColor[, offsetMode]) extends GUI.**layout**
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
| *function* | :**setAlignment**(*enum* horizontalAlignment, *enum* verticalAlignment): *table* list| Set list items alignment. By default it's set to GUI.**ALIGNMENT_HORIZONTAL_LEFT** and GUI.**ALIGNMENT_VERTICAL_TOP** |
| *function* | :**setDirection**(*enum* direction): *table* list| Choose an items display option for List boundaries. The default alignment is **left** and **top** |
| *function* | :**setSpacing**(*int* spacing): *table* list| Set spacing between List items |
| *function* | :**setMargin**(*int* horizontalMargin, *int* verticalMargin): *table* list| Set margin in pixels depending on the current **alignment** of list |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

-- Create vertically oriented list
local verticalList = application:addChild(GUI.list(3, 2, 25, 30, 3, 0, 0xE1E1E1, 0x4B4B4B, 0xD2D2D2, 0x4B4B4B, 0x3366CC, 0xFFFFFF, false))
verticalList:addItem("Hello world")
verticalList:addItem("This is test").onTouch = function()
	GUI.alert("Selected item: " .. verticalList.selectedItem)
end
verticalList:addItem("Beautiful")
verticalList:addItem("Like a shit")

-- Create horizontally oriented list
local horizontalList = application:addChild(GUI.list(34, 2, 100, 3, 2, 0, 0xE1E1E1, 0x4B4B4B, 0xE1E1E1, 0x4B4B4B, 0x696969, 0xFFFFFF, true))
horizontalList:setDirection(GUI.DIRECTION_HORIZONTAL)
horizontalList:setAlignment(GUI.ALIGNMENT_HORIZONTAL_CENTER, GUI.ALIGNMENT_VERTICAL_TOP)
horizontalList:addItem("Applications")
horizontalList:addItem("Libraries")
horizontalList:addItem("Scripts")
horizontalList:addItem("Wallpapers")

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/lYzufn2.gif)

GUI.**menu**(x, y, width, backgroundColor, textColor, backgroundPressedColor, textPressedColor[, backgroundTransparency]) extends GUI.**layout**
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
| *function* | :**addItem**(*string* text[, *int* color]): *table* item | Add a new item to Menu. You can specify .**onTouch**() function to item if desired |
| *function* | :**addContextMenu**(*string* text[, *int* color]): *table* contextMenu | Add a context menu to this menu. The behavior of returned object is the same as GUI.**addContextMenu**(...): *table* contextMenu |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

-- Add menu object to application
local menu = application:addChild(GUI.menu(1, 1, application.width, 0xEEEEEE, 0x666666, 0x3366CC, 0xFFFFFF))
-- Add first item with black color. Attack a callback-function to it
menu:addItem("MineCode IDE", 0x0).onTouch = function()
	GUI.alert("Hello world!")
end
-- Add context menu and few items to it
local contextMenu = menu:addContextMenu("File")
contextMenu:addItem("New")
contextMenu:addItem("Open").onTouch = function()
	GUI.alert("Open item was pressed")
end
contextMenu:addSeparator()
contextMenu:addItem("Save")
contextMenu:addItem("Save as")
-- Add whatever you want
menu:addItem("Edit")
menu:addItem("View")
menu:addItem("About")

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/OHOhvcy.gif)

GUI.**comboBox**(x, y, width, elementHeight, backgroundColor, textColor, arrowBackgroundColor, arrowTextColor) extends GUI.**object**
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
| *function* | :**getItem**( *int*/*string* index/name ): *table* item| Get item by it's index or name |
| *function* | :**clear**()| Remove all items |
| *function* | :**count**(): *int* count| Get items count |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

local comboBox = application:addChild(GUI.comboBox(3, 2, 30, 3, 0xEEEEEE, 0x2D2D2D, 0xCCCCCC, 0x888888))
comboBox:addItem(".PNG")
comboBox:addItem(".JPG").onTouch = function()
	-- Do something when .JPG was selected
end
comboBox:addItem(".GIF")
comboBox:addItem(".PIC")

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i.imgur.com/6ROzLAc.gif)

GUI.**resizer**(x, y, width, height, resizerColor, arrowColor) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

-- Add a panel that symbolizes the system window, the size of which we will change
local panel = application:addChild(GUI.panel(3, 2, 30, 10, 0xE1E1E1))
-- Add a resizer, by default located in the right part of the window. Make the width of the resizer at least 3 to handle the drag/drop events in both directions
local resizer = application:addChild(GUI.resizer(panel.localX + panel.width - 2, panel.localY + math.floor(panel.height / 2 - 2), 3, 4, 0xAAAAAA, 0x0))

-- This function will be called during the "drag" event, when the user moves over the resizer
resizer.onResize = function(dragWidth, dragHeight)
	panel.width = panel.width + dragWidth
	resizer.localX = resizer.localX + dragWidth

	application:draw()
end

-- This function will be called on "drop" event
resizer.onResizeFinished = function()
	GUI.alert("Resize finished!")
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/PvARN8j.gif)

GUI.**progressBar**(x, y, width, primaryColor, secondaryColor, valueColor, value[, thin, showValue, valuePrefix, valuePostfix]) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

application:addChild(GUI.progressBar(2, 2, 80, 0x3366CC, 0xEEEEEE, 0xEEEEEE, 80, true, true, "Value prefix: ", " value postfix"))

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i89.fastpic.ru/big/2017/0402/f1/ef1da27531ccf899eb9eb59c010180f1.png)

GUI.**filesystemTree**(x, y, width, height, backgroundColor, directoryColor, fileColor, arrowColor, backgroundSelectionColor, textSelectionColor, arrowSelectionColor, disabledColor, scrollBarBackground, scrollBarForeground, showMode, selectionMode) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x262626))

local tree1 = application:addChild(GUI.filesystemTree(3, 2, 30, 41, 0xCCCCCC, 0x3C3C3C, 0x3C3C3C, 0x999999, 0x3C3C3C, 0xE1E1E1, 0xBBBBBB, 0xAAAAAA, 0xBBBBBB, 0x444444, GUI.IO_MODE_BOTH, GUI.IO_MODE_FILE))
tree1:updateFileList()
tree1.onItemSelected = function(path)
	GUI.alert("Something was selected, the path is: \"" .. path .. "\"")
end

local tree2 = application:addChild(GUI.filesystemTree(34, 2, 30, 41, 0xCCCCCC, 0x3C3C3C, 0x3C3C3C, 0x999999, 0x3C3C3C, 0xE1E1E1, 0xBBBBBB, 0xAAAAAA, 0xBBBBBB, 0x444444, GUI.IO_MODE_FILE, GUI.IO_MODE_FILE))
tree2:updateFileList()
tree2.onItemSelected = function(path)
	GUI.alert("File was selected, the path is: \"" .. path .. "\"")
end

local tree3 = application:addChild(GUI.filesystemTree(66, 2, 30, 41, 0xCCCCCC, 0x3C3C3C, 0x3C3C3C, 0x999999, 0x3C3C3C, 0xE1E1E1, 0xBBBBBB, 0xAAAAAA, 0xBBBBBB, 0x444444, GUI.IO_MODE_DIRECTORY, GUI.IO_MODE_DIRECTORY))
tree3:updateFileList()
tree3.onItemSelected = function(path)
	GUI.alert("Directory was selected, the path is: \"" .. path .. "\"")
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/igGozFP.gif)

GUI.**filesystemChooser**(x, y, width, height, backgroundColor, textColor, tipBackgroundColor, tipTextColor, initialText, sumbitButtonText, cancelButtonText, placeholderText, filesystemDialogMode, filesystemDialogPath) extends GUI.**object**
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
| *function* | :**setMode**( *enum* IOMode, *enum* showMode ) | This is method for setting window mode. First parameter is needed to tell window what to do: to open or to save items. It can be GUI.**IO_MODE_OPEN**, GUI.**IO_MODE_SAVE** or GUI.**IO_MODE_BOTH**. The second one is needed to setting showing mode. It can be GUI.**IO_MODE_FILE**, GUI.**IO_MODE_DIRECTORY** or GUI.**IO_MODE_BOTH** |
| *function* | :**addExtensionFilter**( *string* extension )| Add a filter to the specified file extension. After that, only files witch specified extension well be able to be selected |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x262626))

local filesystemChooser = application:addChild(GUI.filesystemChooser(2, 2, 30, 3, 0xE1E1E1, 0x888888, 0x3C3C3C, 0x888888, nil, "Open", "Cancel", "Choose", "/"))
filesystemChooser:setMode(GUI.IO_MODE_OPEN, GUI.IO_MODE_FILE)
filesystemChooser.onSubmit = function(path)
	GUI.alert("File \"" .. path .. "\" was selected")
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/F0ch8yQ.gif)

GUI.**codeView**(x, y, width, height, fromSymbol, fromLine, maximumLineLength, selections, highlights, syntaxPatterns, syntaxColorScheme, syntaxHighlight, lines) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x0))

-- Add codeView object to application
local codeView = application:addChild(GUI.codeView(2, 2, 72, 22, 1, 1, 1, {}, {}, GUI.LUA_SYNTAX_PATTERNS, GUI.LUA_SYNTAX_COLOR_SCHEME, true, {}))

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

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/UQJxhCn.png)

GUI.**chart**(x, y, width, height, axisColor, axisValueColor, axisHelpersColor, chartColor, xAxisValueInterval, yAxisValueInterval, xAxisPostfix, yAxisPostfix, fillChartArea, values) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

local chart = application:addChild(GUI.chart(2, 2, 100, 30, 0xEEEEEE, 0xAAAAAA, 0x888888, 0xFFDB40, 0.25, 0.25, "s", "t", true, {}))
for i = 1, 100 do
	table.insert(chart.values, {i, math.random(0, 80)})
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i91.fastpic.ru/big/2017/0402/5b/66ff353492298f6a0c9b01c0fc8a525b.png)

GUI.**brailleCanvas**(x, y, width, height) extends GUI.**object**
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
| *function* | :**set**( *int* x, *int* y, *boolean* state[, *int* color] )| Set the corresponding pixel value to the local coordinates of the BrailleCanvas. If there is already an existing pixel in this position, the value of its color will be replaced by a new one. If the color argument is not specified, then the pixel color will remain the same |
| *function* | :**get**( *int* x, *int* y ): *boolean* state, *int* color, *char* symbol | Get the state, color, and the symbol of the current braille pixel |
| *function* | :**fill**( *int* x, *int* y, *int* width, *int* height, *boolean* state, *int* color ) | Works similarly to the :**set**() method, however it allows editing entire canvas |
| *function* | :**clear**() | Clear canvas content |

Example of implementation:
```lua
local GUI = dofile("/lib/GUI.lua")

--------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x262626))

-- Add a text label for size comparison
application:addChild(GUI.label(3, 2, 30, 1, 0xFFFFFF, "Text for size comparison"))
-- Add BrailleCanvas with 30x15 screen pixels
local brailleCanvas = application:addChild(GUI.brailleCanvas(3, 4, 30, 15))

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

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/FPWbQkv.png)

GUI.**scrollBar**(x, y, width, height, backgroundColor, foregroundColor, minimumValue, maximumValue, value, shownValueCount, onScrollValueIncrement, thinMode) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

-- Add vertical scrollBar to application
local verticalScrollBar = application:addChild(GUI.scrollBar(2, 3, 1, 15, 0x444444, 0x888888, 1, 100, 1, 10, 1, true))
verticalScrollBar.onTouch = function()
	GUI.alert("Vertical scrollbar was touched")
end

-- Add horizontal too
local horizontalScrollBar = application:addChild(GUI.scrollBar(3, 2, 60, 1, 0x444444, 0x888888, 1, 100, 1, 10, 1, true))
horizontalScrollBar.onTouch = function()
	-- Do something on scrollBar touch
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/XrqDvBk.png)

GUI.**textBox**(x, y, width, height, backgroundColor, textColor, lines, currentLine, horizontalOffset, verticalOffset[, autoWrap, autoHeight]) extends GUI.**object**
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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

local textBox = application:addChild(GUI.textBox(2, 2, 32, 16, 0xEEEEEE, 0x2D2D2D, {}, 1, 1, 0))
table.insert(textBox.lines, {text = "Sample colored line ", color = 0x880000})
for i = 1, 100 do
	table.insert(textBox.lines, "Sample line " .. i)
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](http://i89.fastpic.ru/big/2017/0402/ad/01cdcf7aec919051f64ac2b7d9daf0ad.png)

Ready-to-use containers
======

There are various containers listed below that support all features of GUI.**container**, however they have a special functional and methods

GUI.**layout**(x, y, width, height, columnCount, rowCount) extends GUI.**container**
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Layout coordinate by x-axis |
| *int* | y | Layout coordinate by y-axis |
| *int* | width | Layout width |
| *int* | height | Layout height |
| *int* | columnCount | Layout grid column count |
| *int* | rowCount | Layout grid row count |

This is one of the most frequently used and technically advanced widgets. Layout is an inheritor
 of the GUI.**container** with similar behavior that can automatically calculate position of child objects within itself. For example, if you want to beautifully display a lot of objects without wasting time on manual calculation of coordinates, then layout is made for you. Picture below shows in detail the layout structure of 3x2:

![](https://i.imgur.com/rtn1uOV.png)

As you can see, there are 6 cells in this example: each of them can have its own direction, spacing between objects, alignment, margin and automatic fitting. Cells boundaries are **illusive**, so child objects **can** exist beyond them, if cell alignment allows it.

You can assign individual size for each column and row in pixels or as relative (percentage) value, you can change layout grid size and add/remove/resize rows and columns in realtime, you can toggle grid rendering for your comfort, you can even add layouts in each other to group widgets as you want, so working with it is fantastically convenient.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *int* | .**defaultColumn**| Column of grid cell to which new child objects will be added. Default value is **1** |
| *int* | .**defaultRow**| Row of grid cell to which new child objects will be added. Default value is **1** |
| *table* | .**cells**| Three-dismensional table with rows/columns indices. Each .**cells**[row][column] table contains data with cell alignment/direction/spacing/fitting/calculated width and height |
| *boolean* | .**showGrid**| Toggle grid borders rendering. The default value is **false** |
| *function* | :**setPosition**(*int* column, *int* row, *object* child): *object* child| Assign the specified grid cell to the layout child object. One cell can contain as many objects as you want |
| *function* | :**setGridSize**(*int* columnCount, *int* columnCount): *table* layout | Set size of the layout grid. All objects located outside the range of new size must be assigned to required cells again via :**setPosition**(...)  |
| *function* | :**setColumnWidth**(*int* column, *enum* sizePolicy, *float* size): *table* layout | Set width of the specified column. The value can be one of two types: GUI.**SIZE_POLICY_ABSOLUTE** or GUI.**SIZE_POLICY_RELATIVE**. In the first case, the width exists as pixels, and does not change when layout size is changed. The second one exists as the percentage width of the column: if you specify a relative value, and there are other columns to the right of the selected column, their relative width will be automatically recalculated to the desired percentage values. Relative width must be a number in **[0.0; 1.0]** range |
| *function* | :**setRowHeight**(*int* row, *enum* sizePolicy, *float* size): *table* layout | Set height of the specified row. The behavior of the function is similar to **:setColumnWidth**(...) |
| *function* | :**addColumn**(*enum* sizePolicy, *float* size): *table* layout | Add an empty column to layout grid with specified size |
| *function* | :**addRow**(*enum* sizePolicy, *float* size): *table* layout | Add an empty row to layout grid with specified size |
| *function* | :**removeColumn**(*int* column): *table* layout | Remove specified column from layout grid |
| *function* | :**removeRow**(*int* row): *table* layout | Remove specified row from layout grid |
| *function* | :**setDirection**(*int* column, *int* row, *enum* direction): *table* layout | Set grid cell orientation (direction) of the child objects positioning. You can use **GUI.DIRECTION_HORIZONTAL** or **GUI.DIRECTION_VERTICAL** |
| *function* | :**setAlignment**(*int* column, *int* row, *enum* horizontalAlignment, *enum* verticalAlignment): *table* layout | Assign the method for aligning child objects to the grid cell borders. Following values and any combination of them can be used: GUI.**ALIGNMENT_HORIZONTAL_LEFT**, GUI.**ALIGNMENT_HORIZONTAL_CENTER**, GUI.**ALIGNMENT_HORIZONTAL_RIGHT**, GUI.**ALIGNMENT_VERTICAL_TOP**, GUI.**ALIGNMENT_VERTICAL_CENTER** or GUI.**ALIGNMENT_VERTICAL_BOTTOM** |
| *function* | :**setSpacing**(*int* column, *int* row, *int* spacing): *table* layout | Assign the specified grid cell distance in pixels between child objects. The default value is **1** |
| *function* | :**setMargin**(*int* column, *int* row, *int* horizontalMargin, *int* verticalMargin): *table* layout | Assign the specified grid cell indents (margins) in pixels, depending on the current **alignment** of this cell |
| *function* | :**setFitting**(*int* column, *int* row, *int* horizontalFitting, *int* verticalFitting[, *int* horizontalOffset, *int* verticalOffset] ): *table* layout | Assign the specified grid cell automatic resizing of child objects by horizonal, vertical or both directions. By default new child sizes will be equal the cell size. If optional parameters are specified, then it is possible to set an size reducing, i.e. the size of objects will be equal to **Cell size - Offset value** |
| *function* | :**update**(): *table* layout | Forcibly recalculate child objects position. By default this function is being called automatically, but in some cases it can be helful |

Example of implementation:

```lua
local image = require("image")
local GUI = require("GUI")

------------------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

-- Add an layout with 5x1 grid size to application
local layout = application:addChild(GUI.layout(1, 1, application.width, application.height, 5, 1))

-- Add 9 buttons to layout and assign specified grid position to them
-- As you can see, button object is being created first - after that it's being added as child object to layout
-- Finally, a specified grid position is being assigned to added child object
layout:setPosition(1, 1, layout:addChild(GUI.button(1, 1, 26, 3, 0xEEEEEE, 0x000000, 0xAAAAAA, 0x0, "Button 1")))
layout:setPosition(2, 1, layout:addChild(GUI.button(1, 1, 26, 3, 0xEEEEEE, 0x000000, 0xAAAAAA, 0x0, "Button 2")))
layout:setPosition(2, 1, layout:addChild(GUI.button(1, 1, 26, 3, 0xEEEEEE, 0x000000, 0xAAAAAA, 0x0, "Button 3")))
layout:setPosition(3, 1, layout:addChild(GUI.button(1, 1, 26, 3, 0xEEEEEE, 0x000000, 0xAAAAAA, 0x0, "Button 4")))
layout:setPosition(3, 1, layout:addChild(GUI.button(1, 1, 26, 3, 0xEEEEEE, 0x000000, 0xAAAAAA, 0x0, "Button 5")))
layout:setPosition(3, 1, layout:addChild(GUI.button(1, 1, 26, 3, 0xEEEEEE, 0x000000, 0xAAAAAA, 0x0, "Button 6")))
layout:setPosition(4, 1, layout:addChild(GUI.button(1, 1, 26, 3, 0xEEEEEE, 0x000000, 0xAAAAAA, 0x0, "Button 7")))
layout:setPosition(4, 1, layout:addChild(GUI.button(1, 1, 26, 3, 0xEEEEEE, 0x000000, 0xAAAAAA, 0x0, "Button 8")))
layout:setPosition(5, 1, layout:addChild(GUI.button(1, 1, 26, 3, 0xEEEEEE, 0x000000, 0xAAAAAA, 0x0, "Button 9")))

-- Assign an callback function to the first added button
layout.children[1].onTouch = function()
	-- Enable layout grid rendering
	layout.showGrid = true
	-- Change layout grid size
	layout:setGridSize(3, 1)
	-- Change cell spacing for each column
	for column = 1, 3 do
		layout:setSpacing(column, 1, 4)
	end
	-- Change position of last 3 buttons to make them belong to last column
	for child = 7, 9 do
		layout:setPosition(3, 1, layout.children[child])
	end
	-- Enable automatic children width calculation for last column with offset of 4 pixels (2 on each side)
	layout:setFitting(3, 1, true, false, 4, 0)
	-- Draw changes on screen
	application:draw()
end

------------------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/DnNSX45.gif)

GUI.**window**(x, y, width, height) extends GUI.**container**
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Window coordinate by x-axis |
| *int* | y | Window coordinate by y-axis |
| *int* | width | Window width |
| *int* | height | Window height |

Windows are a wonderful thing, allowing the user to move them with a couple of mouse clicks. They already have a built-in .**eventHandler**, so you do not have to bother with anything. 

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *function* | :**resize**(*int* newWidth, *int* newHeight) | Sets a new window size and calls .**onResize**(...) callback-function if it exists |
| *function* | :**close**() | Closes window and performs an self :**remove**() on it |
| *function* | :**minimize**() | Toggles window hidden state. Call this function again to revert changes |
| *function* | :**maximize**() | Toggles window size to full-screen (to fit parent container) or default size. Call this function again to set previous used size. This will call :**resize**(...) function and, of course, .**onResize**(...) callback-function if it exists |
| *callback-function* | :**onResize**(*int* newWidth, *int* newHeight) | This function is called after window size hes been changed via :**resize**(...) function. Two parameters are new window size |

In addition to the empty window template, there are also several prepared window designs:

GUI.**filledWindow**(x, y, width, height, fillColor) extends GUI.**window**
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| ... | ... | ... |
| *int* | fillColor | Window background panel color |

Creates a window with background panel and action buttons inside it:

![](https://i.imgur.com/l3deL1z.png)

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**backgroundPanel** | Pointer to GUI.**panel** object |
| *table* | .**actionButtons** | Pointer to GUI.**actionButtons** object |

GUI.**titledWindow**(x, y, width, height, title, addTitlePanel) extends GUI.**window**
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| ... | ... | ... |
| *string* | title | Window title text |
| [*boolean* | addTitlePanel] | Optional adding of title background panel |

Creates a window with background panel, action buttons, label with specified title and title background panel if desired:

![](https://i.imgur.com/AU7kuwm.png)

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**backgroundPanel** | Pointer to GUI.**panel** object |
| *table* | .**actionButtons** | Pointer to GUI.**actionButtons** object |
| *table* | .**titleLabel** | Pointer to title GUI.**label** object |
| *table* | .**titlePanel** | Pointer to title GUI.**panel** object. Has a **nil** value if not specified |

GUI.**tabbedWindow**(x, y, width, height) extends GUI.**window**
------------------------------------------------------------------------

Creates a window with background panel, action buttons and tab bar objects

![](https://i.imgur.com/XERM46i.png)

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**backgroundPanel** | Pointer to GUI.**panel** object |
| *table* | .**actionButtons** | Pointer to GUI.**actionButtons** object |
| *table* | .**tabBar** | Pointer to title GUI.**tabBar** object |

Example of windows implementation:

```lua
local image = require("image")
local GUI = require("GUI")

------------------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x1E1E1E))

-- First, add an empty window to application
local window1 = application:addChild(GUI.window(90, 6, 60, 20))
-- Add a background panel and text widget to it
window1:addChild(GUI.panel(1, 1, window1.width, window1.height, 0xF0F0F0))
window1:addChild(GUI.text(3, 2, 0x2D2D2D, "Regular window example"))

-- Next add tabbed window
local window2 = application:addChild(GUI.tabbedWindow(4, 3, 60, 20))
-- Use pointer to GUI.tabBar object to add some tabs
window2.tabBar:addItem("Apps")
window2.tabBar:addItem("Libs")
window2.tabBar:addItem("Pictures")
window2.tabBar:addItem("Updates")
-- Add and .onTouch() method to close button to make window be able to close
window2.actionButtons.close.onTouch = function()
	window2:close()
	application:draw()
end
-- Do the same with maximize button
window2.actionButtons.maximize.onTouch = function()
	window2:maximize()
	application:draw()
end
-- Add callback method which is called on window resize. Use passed parameters to set sizes of window child objects
window2.onResize = function(newWidth, newHeight)
	window2.tabBar.width = newWidth
	window2.backgroundPanel.width = newWidth
	window2.backgroundPanel.height = newHeight - window2.tabBar.height
	application:draw()
end

-- Finally add titled window
local window3 = application:addChild(GUI.titledWindow(50, 22, 60, 20, "Titled window example", true))
-- Attach an single cell layout to it
local layout = window3:addChild(GUI.layout(1, 2, window3.width, window3.height - 1, 1, 1))
-- Add some stuff to layout
layout:addChild(GUI.button(1, 1, 36, 3, 0xB4B4B4, 0xFFFFFF, 0x969696, 0xB4B4B4, "Press me"))
layout:addChild(GUI.button(1, 1, 36, 3, 0xB4B4B4, 0xFFFFFF, 0x969696, 0xB4B4B4, "And me"))

------------------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/EZO66Ce.gif)

GUI.**palette**(x, y, initialColor) extends GUI.**window**
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *int* | x | Palette coordinate by x-axis |
| *int* | y | Palette coordinate by y-axis |
| *int* | initialColor | Initial color for palette |

The palette is the inherited object of GUI.**window**, allowing you to choose the desired color by clicking or entering the desired values into text input fields.

This object has following properties:

| Type | Property | Description |
| ------ | ------ | ------ |
| *table* | .**color** )| A table with currently selected color value with different color spaces. For example, if you need integer (hexadecimal) color value, use palette.**color**.**integer**. Otherwise there's also palette.**color**.**hsb**.**hue**, palette.**color**.**hsb**.**saturation**, palette.**color**.**hsb**.**brightness** and palette.**color**.**rgb**.**red**, palette.**color**.**rgb**.**green**, palette.**color**.**rgb**.**blue** values |
| *table* | .**submitButton** )| A pointer to submit GUI.**button** object |
| *table* | .**cancelButton** )| A pointer to cancel GUI.**button** object |

Example of implementation:
```lua
local GUI = require("GUI")

------------------------------------------------------------------------------------------

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x1E1E1E))

-- Add a palette window to application
local palette = application:addChild(GUI.palette(3, 2, 0x9900FF))
-- Specify an .onTouch() callback-function to submit button
palette.submitButton.onTouch = function()
	GUI.alert("You've been selected a color: " .. string.format("0x%X", palette.color.integer))
end

------------------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/NFM1aGo.gif)

Standalone methods
======

The library has several methods that can simplify the development of programs. For example, a context menu, an information window or a palette window.

GUI.**alert**(...varargs)
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
GUI.alert("Something went wrong here, my friend")
```

Result:

![](http://i.imgur.com/s8mA2FL.png?1)

GUI.**addContextMenu**(parentContainer, x, y[, backgroundColor, textColor, backgroundPressedColor, textPressedColor, disabledColor, separatorColor, backgroundTransparency, shadowTransparency])
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
| *function* | :**addItem**(*string* text[, *boolean* disabled, *string* shortcut, *int* color]): *table* item | Add new item to context menu. If **disabled** parameter is specified, item will be shown but not available for clicking You can also specify .**onTouch**() function to added item to do some stuff if desired |
| *function* | :**addSeparator**()| Add an separator to context menu |
| *function* | :**removeItem**(*int* index): *table* item | Remove item from context menu by it's index |
| *function* | :**addSubMenu**(*string* text[, *boolean* disabled]): *table* contextMenu| Add another context menu to this context menu. The returned menu object is independent and supports all the methods described above  |
| *callback-function* | .**onMenuClosed**(*int* selectedIndex)| This function is called after user selects a menu item or closes it. If an element has been selected, this function will have and selected item index as a parameter |

Example of implementation:

```lua
local GUI = require("GUI")

--------------------------------------------------------------------------------

local application = GUI.application()

-- Add an background panel and attack event handler to it
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D)).eventHandler = function(application, object, e1, e2, e3, e4)
	if e1 == "touch" then
		-- Add context menu object to application and some items to it
		local contextMenu = GUI.addContextMenu(application, e3, e4)
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

		application:draw()
	end
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/JqGXAs1.gif)

GUI.**addFilesystemDialog**(parentContainer, addPanel, ...)
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *table* | parentContainer | Container to which palette will be added |
| *boolean* | addPanel | Necessity to add a semi-transparent dark background panel |
| *varargs* | ... | Multiple parameters that comes to GUI.**filesystemDialog** starting from **width** |

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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

local filesystemDialog = GUI.addFilesystemDialog(application, false, 50, math.floor(application.height * 0.8), "Open", "Cancel", "File name", "/")
filesystemDialog:setMode(GUI.IO_MODE_OPEN, GUI.IO_MODE_FILE)
filesystemDialog:addExtensionFilter(".pic")
filesystemDialog.onSubmit = function(path)
	GUI.alert("This path was selected: " .. path)
end

filesystemDialog:show()

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result:

![](https://i.imgur.com/4WqJBVk.gif)

GUI.**addBackgroundContainer**(parentContainer, addPanel, addLayout[, title])
------------------------------------------------------------------------
| Type | Parameter | Description |
| ------ | ------ | ------ |
| *table* | parentContainer | Container to which palette will be added |
| *boolean* | addPanel | Necessity to add a semi-transparent dark background panel |
| *boolean* | addLayout | Necessity to add a 3-columned background layout |
| [*string* | title] | If specified, adds a label to layout as child |

This method creates a new container and adds it as a child to the specified container. If background panel is added, it will already have an event listener: so if you click on panel, this container will be removed automatically. Personally, I use this object everywhere to quickly create a simple menus with easy closing feature and automated layout calculations.

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

local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

-- Add a button to application and .onTouch() method
application:addChild(GUI.button(3, 2, 36, 3, 0xE1E1E1, 0x4B4B4B, 0xA5A5A5, 0x0, "Add container")).onTouch = function()
	-- Add a background container to application with background panel and layout
	local container = GUI.addBackgroundContainer(application, true, true, "Hello world")
	-- Add a switch and label to it's layout
	container.layout:addChild(GUI.switchAndLabel(1, 1, 36, 8, 0x66DB80, 0x2D2D2D, 0xE1E1E1, 0x878787, "I like to suck big dicks:", true))
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
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


Practical example # 1: Creating an animated widget
======

To demonstrate how to work with animations, here is the source code with detailed comments, allowing you to create the **switch** widget and add a motion animation to it. Of course, to understand all this shit, it is **highly** recommended to read information about GUI.**object** and methods of **Double buffering** library.

```lua
local color = require("color")
local buffer = require("doubleBuffering")
local GUI = require("GUI")

--------------------------------------------------------------------------------

-- Create a function that will draw your switch to screen buffer
-- It's recommended to use local function because it will exists in memory as single copy for each switch
local function switchDraw(switch)
	local bodyX = switch.x + switch.width - switch.bodyWidth
	-- Draw a switch text
	buffer.drawText(switch.x, switch.y, switch.colors.text, switch.text)
	-- Draw a background with passive color
	buffer.drawRectangle(bodyX, switch.y, switch.bodyWidth, 1, switch.colors.passive, 0x0, " ")
	buffer.drawText(bodyX + switch.bodyWidth, switch.y, switch.colors.passive, "⠆")
	-- Draw a background with active color
	buffer.drawText(bodyX - 1, switch.y, switch.colors.active, "⠰")
	buffer.drawRectangle(bodyX, switch.y, switch.pipePosition - 1, 1, switch.colors.active, 0x0, " ")
	-- Draw a switch "pipe"
	buffer.drawText(bodyX + switch.pipePosition - 2, switch.y, switch.colors.pipe, "⠰")
	buffer.drawRectangle(bodyX + switch.pipePosition - 1, switch.y, 2, 1, switch.colors.pipe, 0x0, " ")
	buffer.drawText(bodyX + switch.pipePosition + 1, switch.y, switch.colors.pipe, "⠆")
end

-- Create a switch event handler that is called after clicking on it.
-- Again, use local functions for stuff like this
local function switchEventHandler(application, switch, event)
	if event == "touch" then
		-- Change switch state to opposite
		switch.state = not switch.state
		-- Add an animation to switch that fill move "pipe" to correct side
		local animation = switch:addAnimation(
			-- As an animation frame handler you need a function that will set "pipe" position dependent of current animation position
			-- Remember that animation.position is always in [0.0; 1.0] range
			-- If switch state has a false value, you need to invert animation position to play it reversed visually
			function(application, animation)
				if switch.state then
					switch.pipePosition = math.round(1 + animation.position * (switch.bodyWidth - 2))
				else	
					switch.pipePosition = math.round(1 + (1 - animation.position) * (switch.bodyWidth - 2))
				end
			end,
			-- Specify a function that is called after animation finishing
			function(application, animation)
				-- Remove animation object from switch
				animation:remove()
				-- You can also create callback-functions support like this
				if switch.onStateChanged then
					switch.onStateChanged()
				end
			end
		)
		-- Start playing your animation
		animation:start(switch.animationDuration)
	end
end

-- This function will create a new switch object and fill it with required properties
local function newSwitch(x, y, totalWidth, bodyWidth, activeColor, passiveColor, pipeColor, textColor, text, switchState)
	-- Create object that inherits GUI.object
	local switch = GUI.object(x, y, totalWidth, 1)

	-- Specify some variables for you purpose
	switch.colors = {
		active = activeColor,
		passive = passiveColor,
		pipe = pipeColor,
		text = textColor
	}
	switch.bodyWidth = bodyWidth
	switch.text = text
	switch.state = switchState
	-- You can set any animation duration, even a few hours if you want to
	switch.animationDuration = 0.3	
	-- Position of "pipe" will be in range [1; bodyWidth - 1] cause it have 2 pixels width
	switch.pipePosition = switch.state and switch.bodyWidth - 1 or 1

	switch.draw = switchDraw
	switch.eventHandler = switchEventHandler

	return switch
end

--------------------------------------------------------------------------------

-- Now let's create application and fill it with our cool widget
local application = GUI.application()
application:addChild(GUI.panel(1, 1, application.width, application.height, 0x2D2D2D))

-- First, specify required switch count
-- Next, create some variables dependent of it: HUE from HSB color space, coordinates and animation duration
-- So in fact every next switch will have different color and longer animation duration
local count = 168
local hue = 0
local hueStep = 360 / count
local x, y = 3, 2
local animationDurationMin = 0.3
local animationDurationMax = 1.5
local animationDuration = animationDurationMin
local animationDurationStep = (animationDurationMax - animationDurationMin) / count

-- Add specified count of swithes to application
for i = 1, count do
	local switchColor = color.HSBToInteger(hue, 1, 1)
	local switch = application:addChild(
		newSwitch(x, y, 19, 7,
			switchColor,
			0x1D1D1D,
			0xEEEEEE,
			switchColor,
			"Switch " .. i .. ":",
			math.random(2) == 2
		)
	)

	switch.animationDuration = animationDuration

	y = y + switch.height + 1
	hue = hue + hueStep
	animationDuration = animationDuration + animationDurationStep

	if y >= application.height then
		x, y = x + switch.width + 3, 2
	end
end

--------------------------------------------------------------------------------

application:draw(true)
application:start()
```

Result: 

![Imgur](http://i.imgur.com/f5aO73U.gif)
