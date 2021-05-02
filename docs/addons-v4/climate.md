# Homekit Infused 4.x.x

## Content
- [Introduction](index.md)
- [Installation](installation.md)
- [Configuration](configuration.md)
- [Addons](../addons.md)
- [Custom Views](custom_views.md)
- [Updates](updates.md)
- [Issues & Questions](issues.md)
- [About Me](about.md)
- [Thanks](thanks.md)

## Addons > Climate

![Homekit Infused](../images/climate.png)

This addon gives your view a climate preset control panel with 5 buttons to control all of your thermostats at once.
To add this addon to your view add `climate:` in your view_config.

To add climate to your view add the following line:

```yaml
# Example
  my_view:
    climate:
```

You can use any of the following options to modify your addon.
| Name | Required | Default | Description |
|----------------------------------|-------------|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| title | no | Presets | Change the title of the stack |
| name_power | no | Power | Change the name of the power button |
| icon_power | no | mdi:power | Change the icon of the power button |
| name_auto | no | Auto | Change the name of the auto button |
| icon_auto | no | mdi:calendar-clock | Change the icon of the auto button |
| name_cool | no | Cool | Change the name of the cool button |
| icon_cool | no | mdi:air-conditioner | Change the icon of the cool button |
| name_heat | no | Heat | Change the name of the heat button |
| icon_heat | no | mdi:fire | Change the icon of the heat button |
| icon_set_temperature | no | mdi:thermometer | Change the icon of the set_temperature button |
| show_title | no | true | Show or hide the stack title |
| show_power | no | true | Show or hide the power button |
| show_auto | no | true | Show or hide the auto button |
| show_cool | no | true | Show or hide the cool button |
| show_heat | no | true | Show or hide the heat button |
| show_set_temperature | no | true | Show or hide the set_temperature button |

```yaml
# Example
  my_view:
    climate: 
      title: Klimaat
      icon_power: mdi:thermostat
      show_auto: false
```