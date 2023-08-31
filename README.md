# AdvancedEditorUtilities
Widgets and Utilities to improve your daily workflow in Unreal Engine
Available on the [Unreal Marketplace](https://unrealengine.com/marketplace/en-US/product/f375645593fc4d909bf8c79b9f64a066)


## How to activate
* Open plugins
* Look for AdvancedEditorUtilities
* Activate the checkbox
* Restart the editor
* [OPTIONAL], if you want to enable it by default for every project, go to `Engine\Plugins\Marketplace\AdvancedEditorUtilities` and edit `AdvancedEditorUtilities.uplugin` by adding `"EnabledbByDefault": true,`

## How to use

### Open file in windows explorer
* Select a file in content browser
* Press ALT + F to open it in windows explorer
* [NOTE] If you select multiple files it will open all the respective folders at once

### Activate the main widget
* Click the extension button in the top bar (or press CTRL + ALT + U) to focus the main utility widget (The shortcut could be changed or removed in Editor Settings)
* Right click the widget and select `Run Editor Utility Widget` and a window should pop up
* Drag the window wherever you want, resize it, you can even snap it into the editor layout (as you can see in the Marketplace Pictures)

### Viewport mode selector
* Click any button under "Viewport modes" to change the current Viewport Mode, if you click the already highlighted one it will go back to the default viewport mode (By default it's "Lit" but you can change it in the `AEU_ViewModes` Widget. This works both in the editor and during play, but if you press play you have to select the viewport mode another time, because they are handled separately by the engine.


### Console Command Launcher
* Click any button under "Commands" to activate one of the default console commands
* [WARNING] Not every button works while the game is not running
* There are 5 types of button:
  * **Toggle** - Used for commands that toggle themselves on and off if called multiple times, like `Show Collision`
  * **MultiToggle** - Used for commands that have multiple parameters activable at the same time, like `Stat` that supports `Stat FPS`, `Stat Unit`, et cetera
  * **ToggleInverse** - Used when the command used to activate the state is different from the one used to deactivate it, like `EnableAllScreenMessages` and `DisableAllScreenMessages`, in this case the first parameter in the array is used to store the second ommand.
  * **SinglePress** - Used when the command is just a single action that doesn't change the button state, like `HighResShot`
  * **RadioButton** - Used when the command has multiple parameters that can't be activated at the same time, like `Slomo` or `MaxFPS`

### Editing default ViewModes
* You can hide unwanted ViewModes or Commands by editing the arrays in `Editor Settings/Advanced Editor Utility Plugin`(See picture below), by toggling the option `Display in Widget` (Orange rectangles) or simply deleting the value.
![image](https://github.com/Ares9323/AdvancedEditorUtilities/assets/46932745/8f1bc13b-c8be-4297-9d57-c5d55c2924a7)
* Use the reset checkboxes (Light blue rectangle) to reset the default values of the respective category (This is needed because UPROPERTIES with the "Config" specifier don't have the default yellow icon to reset them after you edit them)
* You can also edit them in a permanent way, by editing the `DefaultCommands` and `DefaultViewModes` arrays in C++ by editing `AdvancedEditorUtilitiesSettings.h` (**WARNING: you need to move the plugin from the Marketplace folder into a project "Plugins" folder to recompile it, then you can move it back but you might lose your settings if you update the plugin from the Epic Launcher**)
