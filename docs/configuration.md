# Homekit Infused 2021.x.x

## Content
- [Introduction](index.md)
- [Installation](installation.md)
- [Configuration](configuration.md)
- [Addons](addons.md)
- [Splitting the Configuration](splitting-the-config.md)
- [Updates](updates.md)
- [Issues & Questions](issues.md)
- [About Me](about.md)
- [Thanks](thanks.md)

## Configuration
In Homekit Infused it is super easy to setup views and configure them for either the built-in addons or custom cards.

*NOTE: For ANY change in the config below to take effect you MUST restart Home Assistant!!

### Setting up general config
Some of the variables can be found in the general config. The things you can find here are screen margins, header icon settings, rgb popup settings and vacuum settings.
To setup any of these open the following file `/hki-user/config/general_config.yaml`. 

By default it should be ready for you and this file should only be touched when you want to change something that is related to the settings above. I suggest skipping this file for now and continue with setting up the views instead. 

[Click here](addons-v4/general-config.md) for documentation.

### Setting up views
Views are completely conditional, this means that Homekit Infused doesn't have predefined views (unlike older versions of the project). You can create views pretty fast and easy by only entering a name!
To create a view open the following file `/hki-user/config/view_config.yaml`. 

To setup a new view you can enter ANY name you want, just make SURE your name is lowercase and doesn't contain spaces. Use underscores as HKI will automatically convert them.

```yaml
# Example Minimal
  living_room:
    subtitle: Overview
    icon: mdi:floor-lamp
```
```yaml
# Example Minimal with a subtitle
  living_room:
    subtitle: Overview
    icon: mdi:floor-lamp
```

The example above will create a view for you named Living Room and automatically does the following:
- sets the title of the view (in this case Living Room)
- sets the path of the view for your browser to use (in this case https://hassio.local/homekit-infused/living_room)
- sets an icon for the navigation_bar, subtitle and menu/favorites button
- creates an entry in the menu

This is the bare minimum that will give you a brand new view, however without any other code the view will be sitting empty. Homekit Infused is capable of filling the views for you, use custom user code, or both at the same time. Below are all the view options that you can add to your view to customize each view entirely to your taste.

| Name | Required | Default | Description |
|----------------------------------|-------------|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 'object' | yes | none | Sets the name, path and title of the view, this is not an actual property but the first line of your view |
| title | no | view_name | Set the title of the view, if undefined it will use the name of the view instead |
| subtitle | no | undefined | Set the subtitle text, this accepts button-card JS templates, if you don't set a subtitle it will show the default notifications instead |
| icon | no | mdi:home | Set the icon for the navigation_bar, shortcut buttons and subtitle, this also accepts FA icons, you can use button-card JS templates as long as you don't set this icon to show in the nav_bar |
| type | no | undefined | Set the type to `room` if you want this view to show up as a room, this only has effect when using the `rooms` addon |
| show_header | no | true | Show or hide the entire HKI header (this includes the subtitle) |
| show_subtitle | no | subtitle | Set to show the header subtitle to true or false |
| show_in_favorites | no | false | Set to `true` if you want this view to be auto included in the favorites addon |
| show_in_menu | no | undefined | This forces a view to be shown in the menu addon, this is useful when using the `menu:` or `view_selector:` addon |
| button_label | no | no label | Set the button label text, this accepts button-card JS templates |
| button_badge | no | undefined | This will set a bagde for the menu and favorites button, it will always show the state of an entered entity, you can use any entity_id (e.g. `sensor.current_temperature`) |
| show_in_navbar | no | false | Set to `true` if you want this view to be visible in the navigation_bar, this is not the same as the menu! |
| 'addon_name' | no | undefined | Add an addon to your view, refer to the [Addons](addons.md) section for documentation |

```yaml
# Another Example 
  kitchen:
    subtitle: My Kitchen
    button_badge: sensor.kitchen_temp
    icon: mdi:fridge
    type: room
    show_in_navbar: true
    show_in_favorites: true
```

*Note: HKI can take any card available to Home Assistant, even if it is not included in the HKI addons. You must use the `custom:` addon to do this. You can find more information on this [here](addons-v4/custom.md), you can also find this information when visiting the addons list.

### Setting up device counters
For the header sensors to work properly we need to setup some groups from which HKI can count devices from. Open `/hki-user/device_counters.yaml` and add all your known entities to their corresponding groups. We can re-use these entities again in buttons or in custom-cards, for more information [click here](addons-v4/device-counters.md).

### Setting up Notifications
You can setup notifications to show in the subtitle of the header. You must set this up yourself by opening `/hki-user/notifications.yaml`. For more documentation and examples [click here](addons-v4/notifications.md)!

### More examples
I could go on with examples forever, but it is way better to just check out the example config that I have over [here](https://github.com/jimz011/homekit-infused/tree/4.x.x-personal)
