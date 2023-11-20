# Element Motiv

K1 element theme


### Aplikace
Url čistého kodu vložit do témat elementu

## [Night Owl Dark Theme](https://raw.githubusercontent.com/aaronraimist/element-themes/master/Night%20Owl/Night%20Owl%20Dark/Night-Owl-Dark-Theme.json)

Made by [`@foxy:teapot.ovh`](https://github.com/foxyseta)

![Night Owl Dark Theme Screenshot](Night%20Owl/Night%20Owl%20Dark/Night-Owl-Dark-Theme.png)

# Advanced

The themes in this repository use Element's relatively basic theming system which can only change a limited number of colors. Element's [theming documentation](https://github.com/vector-im/element-web/blob/master/docs/theming.md) has more information on how these work. For more advanced themes where you want to customize things like fonts, button shapes, or all of the colors you'll need to use CSS which isn't supported by Element's theming system. To use CSS based themes you could use a browser extension like Stylus. https://github.com/dannycolin/riot-compact is an example of a more advanced theme.


## Workarounds

Element's theme implementation is fairly limited so custom themes might introduce some odd elements. For example, when using ThomCat Black, the selected reaction 'pill' is outlined in green since Element doesn't give us a variable to control the color that is used there.

![pill_before](images/Pill1.png)

To fix this, we have to edit the custom theme CSS file directly, in this case `theme-dark-custom.css`.  `cssbeautify-cli` is not necessary if your `sed`-fu is better than the author's is.

```
cssbeautify-cli -f theme-dark-custom.css > /tmp/theme-dark-custom-sed.css
sed '/.mx_ReactionsRowButton.mx_ReactionsRowButton_selected/!b;n;c\ \ \ \ background-color:var(--accent-color);' /tmp/theme-dark-custom-sed.css > /tmp/theme-dark-custom.css
sudo -u <nginx/apache_user> cp /tmp/theme-dark-custom.css /<element_directory>/bundles/<bundle_version>/
```
The results:

![pill_after](images/Pill2.png)


## build.py
There is a [build.py](./build.py) python file which takes all the themes and
outputs it to a file as an array of JSON. Simply execute it in this directory.
](https://github.com/jordandrako/element-themes/edit/catppuccin/README.md)
