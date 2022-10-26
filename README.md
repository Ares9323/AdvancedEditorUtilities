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
* You can hide unwanted modes by editing the `AvailableViewModes` array both in C++ (`AdvancedEditorUtilityWidget.h`) and BP (`AEU_ViewModes`), by toggling the option `Display in Widget` or simply deleting the value.

### Console Command Launcher
* Click any button under "Commands" to activate one of the default console commands
* [WARNING] Not every button works while the game is not running
* You can hide or edit the default commands and parameters by editing the `AvailableComands` array both in C++ (`AdvancedEditorUtilityWidget.h`) and BP (`AEU_ConsoleCommands`), by toggling the option `Display in Widget` or simply deleting the value.
* There are 5 types of button:
  * **Toggle** - Used for commands that toggle themselves on and off if called multiple times, like `Show Collision`
  * **MultiToggle** - Used for commands that have multiple parameters activable at the same time, like `Stat` that supports `Stat FPS`, `Stat Unit`, et cetera
  * **ToggleInverse** - Used when the command used to activate the state is different from the one used to deactivate it, like `EnableAllScreenMessages` and `DisableAllScreenMessages`, in this case the first parameter in the array is used to store the second ommand.
  * **SinglePress** - Used when the command is just a single action that doesn't change the button state, like `HighResShot`
  * **RadioButton** - Used when the command has multiple parameters that can't be activated at the same time, like `Slomo` or `MaxFPS`
