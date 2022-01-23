<p align="center"><img width="500" src="https://github.com/dmlls/whatsapp-emoji-linux/blob/main/img/readme/emoji-showcase.png" alt="WhatsApp Emojis for Linux"></p>

<h1 align="center">WhatsApp Emojis for GNU/Linux</h1>
<p align="center">The freshest 3552 WhatsApp emojis to color up your favorite OS.</p>
<br/>

## Download
TODO

---

## Build

### Pre-requisites

Building WhatsAppEmoji requires:
- Python 3
- [pkg-config](https://www.freedesktop.org/wiki/Software/pkg-config/)
- [pngquant](https://pngquant.org/)
- [zopflipng](https://github.com/google/zopfli)

### Installing Python packages

Once the packages listed in pre-requisites are installed, you can install the Python dependencies listed under [`requirements.txt`](https://github.com/dmlls/whatsapp-emoji-linux/blob/main/requirements.txt). It is highly recommended that you install the dependencies in a virtual environment:

```shell
# Make sure you the pre-requisites are installed

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
This will create a directory `build` with the processed emojis. You will find the compiled font `WhatsAppEmoji.ttf` in the root directory.

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

---

## Credits
- Noto Emoji: https://github.com/googlei18n/noto-emoji
- Noto Tools: https://github.com/googlei18n/nototools
- Apple Emoji Linux: https://github.com/samuelngs/apple-emoji-linux

---

## Disclaimer
The emoji images provided are for educational purposes only. WhatsApp is a Trademark of WhatsApp LLC, registered in the U.S. and/or other countries. According to [Emojipedia](https://emojipedia.org/licensing/):

> To the best of our knowledge, specific information about licensing emojis from Apple, Facebook, WhatsApp or Samsung is not publicly available.
