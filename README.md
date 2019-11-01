# color-extraction.py
color-extraction by using colorgram.py
## prerequisites

```
pip install colorgram.py
pip install colormap
pip install easydev
```

## Example
```
import colorgram

# Extract 6 colors from an image.
colors = colorgram.extract('sweet_pic.jpg', 6)

# colorgram.extract returns Color objects, which let you access
# RGB, HSL, and what proportion of the image was that color.
first_color = colors[0]
rgb = first_color.rgb # e.g. (255, 151, 210)
hsl = first_color.hsl # e.g. (230, 255, 203)
proportion  = first_color.proportion # e.g. 0.34

# RGB and HSL are named tuples, so values can be accessed as properties.
# These all work just as well:
red = rgb[0]
red = rgb.r
saturation = hsl[1]
saturation = hsl.s
```
### colorgram.extract(image, number_of_colors)
Extract colors from an image. ``image`` may be either a path to a file, a file-like object, or a Pillow ``Image`` object. The function will return a list of ``number_of_colors`` ``Color`` objects.

### colorgram.Color
A color extracted from an image. Its properties are:

- Color.rgb - The color represented as a ``namedtuple`` of RGB from 0 to 255, e.g. ``(r=255, g=151, b=210)``.
- Color.hsl - The color represented as a ``namedtuple`` of HSL from 0 to 255, e.g. ``(h=230, s=255, l=203)``.
- Color.proportion - The proportion of the image that is in the extracted color from 0 to 1, e.g. ``0.34``.
