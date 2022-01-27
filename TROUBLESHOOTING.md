# Troubleshooting

### Non-color emojis being displayed in some apps

It can happen that after the installation, some programs display a mixture of
non-color and color (WhatsApp) emojis, e.g.:

<p align="center"><img width="700" src="https://github.com/dmlls/whatsapp-emoji-linux/blob/main/img/troubleshooting/non-color-emojis.png" alt="Building"></p>

A way to solve this can be the following. First, ensure that the necessary
directories exist with `mkdir -p ~/.config/fontconfig/conf.d`. Then, create the
file `~/.config/fontconfig/conf.d/01-emoji.conf` with the following content:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
  <alias>
    <family>serif</family>
    <prefer>
      <family>WhatsApp Emoji</family>
    </prefer>
  </alias>
  <alias>
    <family>sans-serif</family>
    <prefer>
      <family>WhatsApp Emoji</family>
    </prefer>
  </alias>
  <alias>
    <family>monospace</family>
    <prefer>
      <family>WhatsApp Emoji</family>
    </prefer>
  </alias>
</fontconfig>
```

Save the file and refresh the font cache with `fc-cache -f -v`. Don't forget to
reopen any opened programs for changes to take effect.
