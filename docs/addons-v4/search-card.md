# Homekit Infused 2021.x.x

## Content
- [Introduction](../index.md)
- [Installation](../installation.md)
- [Configuration](../configuration.md)
- [Addons](../addons.md)
- [Splitting the Configuration](../splitting-the-config.md)
- [Updates](../updates.md)
- [Issues & Questions](../issues.md)
- [About Me](../about.md)
- [Thanks](../thanks.md)

## Addons > Search Card

![Homekit Infused](../images/search-card.png)

This addon gives your view a search bar to quickly search any of your entities.
This addon will always be the first card to show.
This addon has no extra options.

To add this addon to your view add `search:` in your view_config.
To search_card map to your view add the following line:

```yaml
# Example
  my_view:
    search:
```     