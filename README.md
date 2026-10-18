# Paintly Numbers

Turn any photo into a paint-by-number template, with a mixing recipe for every color, made from the paints you actually own.

**Try it:** https://margahernandez.github.io/paintly-numbers/

## What it does

- **Photo to template.** Upload a photo, take one with your camera, or paste it in. The app breaks it into numbered shapes you can paint.
- **Three difficulty levels.** Beginner, Intermediate, and Advanced follow typical paint-by-number kits, from about 12 to 48 colors. Each level also sets the shape size. You get the exact number of colors you pick.
- **Small details stay.** Features that stand out, such as eyes, catchlights, and lash lines, are kept even when they're tiny.
- **Mixing recipes.** Every color comes with a recipe in parts, for example "4 parts Ultramarine, 1 part Burnt sienna, a touch of White".
- **My paints.** Recipes use only the paints you have. You can add a whole set by brand or add paints one by one, and you can adjust any swatch to match your tube. If your paints can't quite reach a color, the recipe says so and shows the closest mix.
- **Track progress.** Tick off colors as you paint them, and the template fills them in.
- **Printable Artwork Sheet.** Download a PDF in A4 or A3 with smooth light outlines, readable numbers, and a color key with every recipe. The sheet is simplified for paper so each shape is big enough to paint, and every color stays on it.
- **Library.** Your outlined artworks and their reference photos are kept separately, and you can select several to delete.

## Paint sets included

| Brand | Set |
| --- | --- |
| Himi (Miya) | Jelly Gouache, 24 colors |
| Holbein | Artists' Gouache, set of 12 |
| Daler-Rowney | Simply Gouache, set of 12 |
| Winsor & Newton | Designers Gouache, introductory set of 10 |
| Winsor & Newton | Cotman Watercolour, Sketchers' Pocket Box of 12 |
| Winsor & Newton | Winton Oil Colour, set of 10 |
| Sakura Koi | Watercolor Pocket Field Sketch Box, 12 colors |
| Liquitex | Basics Acrylic, set of 12 |

Each set lists the colors in the retail set. The swatch colors are close approximations, not official brand data. Brands sometimes change what's in a set, so check the list against your box.

## How it works

1. **Reading the photo.** The photo is analyzed in Lab color space, which follows how people see differences in color.
2. **Finding colors.** k-means clustering finds 100 starting colors. These are joined step by step, closest pair first, until exactly the chosen number is left. Colors that would mix the same are joined first, so each number gets its own recipe. With a smaller paint list, two numbers can end up with the same mix, and the app points it out.
3. **Cleaning up shapes.** Specks and wiggly edges are smoothed away. A contrast check protects small details that stand out from what's around them.
4. **Smooth outlines.** Shape borders are traced as chains and smoothed with a Gaussian, so outlines read as curves instead of pixel steps.
5. **Mixing recipes.** Each paint is modeled with a simplified Kubelka-Munk approach (how much light a paint absorbs and scatters), so blue and yellow make green and white tints strongly. Every mix of one, two, or three paints in simple part ratios is checked, and the app picks the mix with the best balance of closeness and simplicity.
6. **The printed sheet.** Shapes are simplified for the paper size. Anything narrower than about 3.5 mm joins its neighbor, and numbers are sized to fit their shape. A small PDF writer built into the app puts it all together.

## Privacy

Everything runs in your browser. Your photos are never uploaded anywhere. Artworks, progress, and your paint list are saved in this browser's local storage, so they stay on this device.

## Running it locally

There's no build step and nothing to install. The whole app is one file, so just open `index.html` in a browser. It works offline apart from the font.

## Credits

- Sample photos are from [Unsplash](https://unsplash.com) and are used under the [Unsplash License](https://unsplash.com/license).
- The typeface is [Recursive](https://www.recursive.design/), served by Google Fonts.

## About

Designed and built by Marga Hernandez with the help of Claude AI. More work at [margahernandez.framer.ai](https://margahernandez.framer.ai).
