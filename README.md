<p align="center"><img src="https://github.com/dmlls/whatsapp-emoji-linux/blob/main/img/readme/emoji-showcase.png" alt="WhatsApp Emojis for Linux"></p>

<h1 align="center">WhatsApp Emojis for GNU/Linux</h1>
<p align="center">The freshest 3540 WhatsApp emojis to color up our favorite OS.</p>

<p align="center"><a href="https://github.com/dmlls/whatsapp-emoji-linux/releases/tag/latest"><img alt="GitHub release (latest by date)" src="https://img.shields.io/github/v/release/dmlls/whatsapp-emoji-linux?color=%233ea54a&display_name=release&label=WhatsApp%20Version"></a></p>
<br/>

<h2>Installing <img width="22" src="https://github.com/dmlls/whatsapp-emoji-linux/blob/main/img/readme/installing.png" alt="Installing"></h2>

<h3><a href="https://github.com/dmlls/whatsapp-emoji-linux/releases/download/latest/WhatsAppEmoji.ttf">Download font</a>&nbsp;&nbsp;•&nbsp;&nbsp;<a href="https://aur.archlinux.org/packages/ttf-whatsapp-emoji/">Available on <img width="21" src="https://github.com/dmlls/whatsapp-emoji-linux/blob/main/img/readme/arch-linux.png" alt="Arch Linux AUR">AUR</a></h3>
<br/>

### Before installing...
**WhatsAppEmoji will conflict with the following fonts:**
- [Noto Emoji](https://github.com/googlefonts/noto-emoji)
- [Symbola](https://dn-works.com/ufas/)
- [JoyPixel](https://www.joypixels.com/)
- [Twitter Color Emoji](https://github.com/eosrei/twemoji-color-font)
- [Apple Color Emoji](https://github.com/samuelngs/apple-emoji-linux)

**Make sure these fonts are not installed, and if so, uninstall them first.**
<br/><br/>

### Option 1: Install for current user

To install the font only for you, copy the .ttf file to `~/.local/share/fonts/`, e.g.:
```shell
cp WhatsAppEmoji.ttf ~/.local/share/fonts/
```


### Option 2: System-wide installation

To install the font for all the users, copy the .ttf file to `cd /usr/share/fonts/TTF/`, e.g.:
```shell
sudo cp WhatsAppEmoji.ttf /usr/share/fonts/TTF/
```

<br/>

### After installing...

Don't forget to rebuild the system font cache with:
```shell
fc-cache -f -v
```
Finally, you will have restart any open program in order for the installation to take effect.

<br/><br/>

<h2>Troubleshooting <img width="22" src="https://github.com/dmlls/whatsapp-emoji-linux/blob/main/img/readme/troubleshooting.png" alt="Building"></h2>

- [Non-color emojis being displayed in some apps](https://github.com/dmlls/whatsapp-emoji-linux/blob/main/TROUBLESHOOTING.md#non-color-emojis-being-displayed-in-some-apps).

<br/><br/>

<h2>Building <img width="22" src="https://github.com/dmlls/whatsapp-emoji-linux/blob/main/img/readme/building.png" alt="Building"></h2>

### Pre-requisites

Building WhatsAppEmoji requires:
- Python 3
- [pkg-config](https://www.freedesktop.org/wiki/Software/pkg-config/)
- [pngquant](https://pngquant.org/)
- [zopflipng](https://github.com/google/zopfli)

### Installing Python packages

Once the packages listed in pre-requisites are installed, you can install the Python dependencies listed under [`requirements.txt`](https://github.com/dmlls/whatsapp-emoji-linux/blob/main/requirements.txt). It is highly recommended that you install the dependencies in a virtual environment:

```shell
# Make sure the pre-requisites are installed

# Create & activate a virtual environment
python3 -m venv venv
source venv/bin/activate

# Install Python requirements
pip install -r requirements.txt
```

### Build

Once all the dependencies are installed, you can build the font:

```shell
time make -j
```

This will create a directory `build` with the processed emojis and the compiled font `WhatsAppEmoji.ttf`.

Bear in mind that building the font will take several miutes.

### Install

To automatically install the font in your system, run:

```shell
make install
```

Finally, rebuild the system font cache with:
```shell
fc-cache -f -v
```

You will need to restart any open program for the installed font to be displayed.

<br/><br/>

<h2>Credits <img width="25" src="https://github.com/dmlls/whatsapp-emoji-linux/blob/main/img/readme/credits.png" alt="Credits"></h2>

- Noto Emoji: https://github.com/googlei18n/noto-emoji
- Noto Tools: https://github.com/googlei18n/nototools
- Apple Emoji Linux: https://github.com/samuelngs/apple-emoji-linux

<br/><br/>

<h2>Disclaimer <img width="22" src="https://github.com/dmlls/whatsapp-emoji-linux/blob/main/img/readme/disclaimer.png" alt="Disclaimer"></h2>

The emoji images included in this repository belong to WhatsApp. WhatsApp is a Trademark of WhatsApp LLC, registered in the U.S. and/or other countries. These images are provided for non-commercial, educational purposes only. Its use is solely transformative, i.e., intended with a further purpose or different character, and do not substitute under any circumstance for the original use of the work.
