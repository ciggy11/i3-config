# i3 Window Manager Configuration File

This repository contains the configuration file (`config`) for the i3 window manager, tailored for the Manjaro Linux distribution. Below is an explanation of the keybindings and their corresponding code snippets in the configuration file.

## Table of Contents

- [i3 Window Manager Configuration File Boilerplate](#i3-window-manager-configuration-file-boilerplate)
- [Keybindings](#keybindings)
  - [General Keybindings](#general-keybindings)
  - [Application Launch Keybindings](#application-launch-keybindings)
  - [Navigation Keybindings](#navigation-keybindings)
  - [Window Movement Keybindings](#window-movement-keybindings)
  - [Layout Keybindings](#layout-keybindings)
  - [Miscellaneous Keybindings](#miscellaneous-keybindings)
  - [Window Resizing Keybindings (While in Resize Mode)](#window-resizing-keybindings-while-in-resize-mode)
- [Editing and Customizing the Configuration](#editing-and-customizing-the-configuration)
  - [Changing the Look of the System](#changing-the-look-of-the-system)
    - [Background](#background)
    - [Toolbar Fonts](#toolbar-fonts)
    - [System Colors](#system-colors)
    - [Menus](#menus)
    - [Additional Customization](#additional-customization)
    - [Applying Changes](#applying-changes)
    - [Additional Tools for Customization](#additional-tools-for-customization)
- [Copying the Configuration to the Correct Location](#copying-the-configuration-to-the-correct-location)


## Keybindings

### General Keybindings

- **Mod+Return**: Open terminal (Alacritty)
  ```bash
  bindsym $mod+Return exec alacritty
  ```

- **Mod+Shift+q**: Kill focused window
  ```bash
  bindsym $mod+Shift+q kill
  ```

- **Mod+Shift+r**: Restart i3
  ```bash
  bindsym $mod+Shift+r restart
  ```

- **Mod+Shift+e**: Exit i3
  ```bash
  bindsym $mod+Shift+e exec "i3-nagbar -t warning -m 'Do you really want to exit i3?' -b 'Yes, exit i3' 'i3-msg exit'"
  ```

- **Mod+Shift+c**: Reload configuration file
  ```bash
  bindsym $mod+Shift+c reload
  ```

- **Mod+1, Mod+2, Mod+3, Mod+4**: Switch to workspaces 1, 2, 3, 4
  ```bash
  bindsym $mod+1 workspace number 1
  bindsym $mod+2 workspace number 2
  bindsym $mod+3 workspace number 3
  bindsym $mod+4 workspace number 4
  ```

- **Mod+Right, Mod+Left**: Move to next/previous workspace
  ```bash
  bindsym $mod+Right workspace next
  bindsym $mod+Left workspace prev
  ```

### Application Launch Keybindings

- **Mod+Shift+f**: Launch Chrome
  ```bash
  bindsym $mod+Shift+f exec google-chrome
  ```

- **Mod+Shift+v**: Launch VSCode
  ```bash
  bindsym $mod+Shift+v exec code
  ```

- **Mod+Shift+m**: Launch Dolphin (File Manager)
  ```bash
  bindsym $mod+Shift+m exec dolphin
  ```

### Navigation Keybindings

- **Mod+j**: Focus left
  ```bash
  bindsym $mod+j focus left
  ```

- **Mod+k**: Focus down
  ```bash
  bindsym $mod+k focus down
  ```

- **Mod+l**: Focus up
  ```bash
  bindsym $mod+l focus up
  ```

- **Mod+;**: Focus right
  ```bash
  bindsym $mod+semicolon focus right
  ```

### Window Movement Keybindings

- **Mod+Shift+j**: Move window left
  ```bash
  bindsym $mod+Shift+j move left
  ```

- **Mod+Shift+k**: Move window down
  ```bash
  bindsym $mod+Shift+k move down
  ```

- **Mod+Shift+l**: Move window up
  ```bash
  bindsym $mod+Shift+l move up
  ```

- **Mod+Shift+;**: Move window right
  ```bash
  bindsym $mod+Shift+semicolon move right
  ```

### Layout Keybindings

- **Mod+b**: Switch to stacking layout
  ```bash
  bindsym $mod+b layout stacking
  ```

- **Mod+s**: Switch to stacking layout
  ```bash
  bindsym $mod+s layout stacking
  ```

- **Mod+w**: Switch to tabbed layout
  ```bash
  bindsym $mod+w layout tabbed
  ```

- **Mod+e**: Toggle split layout
  ```bash
  bindsym $mod+e layout toggle split
  ```

### Miscellaneous Keybindings

- **Mod+f**: Toggle fullscreen for the focused window
  ```bash
  bindsym $mod+f fullscreen toggle
  ```

- **Mod+a**: Focus the parent container
  ```bash
  bindsym $mod+a focus parent
  ```

### Window Resizing Keybindings (While in Resize Mode)

- **h**: Shrink window width
- **j**: Grow window height
- **k**: Shrink window height
- **l**: Grow window width
- **Enter**: Exit resize mode
- **Escape**: Exit resize mode

## Editing and Customizing the Configuration

To edit and customize the i3 configuration file:

1. Clone this repository to your local machine using Git:
   ```bash
   git clone https://github.com/00-Python/I3-Config.git
   ```

2. Navigate to the cloned repository directory:
   ```bash
   cd I3-Config/
   ```

3. Open the `config` file in a text editor of your choice. 

4. Save the changes after customization.

You can customize keybindings, colors, fonts, and other settings according to your preferences.


### Changing the Look of the System

Customizing the appearance of your i3 system allows you to personalize various aspects such as backgrounds, toolbar fonts, system colors, menus, and more. Below are detailed steps and options for customization:

#### Background

1. **Wallpaper**: Choose a wallpaper that suits your taste. You can find wallpapers online or use your own images.

2. **Set Wallpaper**: Use a tool like `feh` to set the wallpaper:
   ```bash
   feh --bg-fill /path/to/your/wallpaper.jpg
   ```

#### Toolbar Fonts

1. **Font Selection**: Modify the font settings in your i3 configuration file. You can specify the font family and size:
   ```bash
   font pango:Roboto Mono 10
   ```

#### System Colors

1. **Color Scheme**: Adjust the color scheme in your i3 configuration file. Customize variables such as `$bg-color`, `$text-color`, `$focused-bg-color`, `$focused-text-color`, etc.:
   ```bash
   set $bg-color #2E3440
   set $text-color #D8DEE9
   set $focused-bg-color #3B4252
   set $focused-text-color #E5E9F0
   ```

#### Menus

1. **Dmenu Customization**: Customize the appearance of Dmenu using command-line options in your i3 configuration file. You can modify fonts, colors, and more:
   ```bash
   bindsym $mod+d exec --no-startup-id dmenu_run -fn 'Roboto Mono-10' -nb '$bg-color' -nf '$text-color' -sb '$focused-bg-color' -sf '$focused-text-color'
   ```

#### Additional Customization

1. **Bar Settings**: Modify the appearance of the i3 status bar by adjusting settings in your configuration file. You can change colors, fonts, and add or remove status components:
   ```bash
   bar {
       status_command i3status
       colors {
           background $bg-color
           statusline $text-color
       }
   }
   ```

2. **Window Borders**: Customize the appearance of window borders by adjusting border styles and colors:
   ```bash
   default_border pixel 2
   default_floating_border pixel 2
   ```

3. **Transparency**: Add transparency effects to windows and menus for a sleeker look. You can use tools like `compton` for this purpose.

#### Applying Changes

1. **Save and Restart**: After making changes to your i3 configuration file, save the file and restart i3 for the changes to take effect:
   ```bash
   i3-msg restart
   ```

#### Additional Tools for Customization

1. **i3blocks**: Use i3blocks to create customizable status bars with various plugins for system information such as CPU usage, memory usage, battery status, etc.

2. **Rofi**: Rofi is a versatile application launcher that can also be used as a window switcher, SSH launcher, and more. Customize Rofi themes and colors to match your system's look.

3. **Polybar**: Polybar is another popular status bar that offers extensive customization options, including fonts, colors, modules, and more.


## Copying the Configuration to the Correct Location

Once you've made your customizations, follow these steps to copy the configuration to the correct location:

1. Navigate to the i3 configuration directory:
   ```bash
   cd ~/.config/i3/
   ```

2. Make a backup of your existing configuration file (optional but recommended):
   ```bash
   cp config config_backup
   ```

3. Copy the modified `config` file from the cloned repository to the i3 configuration directory:
   ```bash
   cp <path_to_cloned_repository>/config .
   ```

4. Restart i3 for the changes to take effect:
   ```bash
   i3-msg restart
   ```

Now, your customized i3 configuration should be applied.
