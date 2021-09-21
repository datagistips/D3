## 21 Septembre

rect, circle, text
```
<svg version="1.1"
     baseProfile="full"
     width="300" height="200"
     xmlns="http://www.w3.org/2000/svg">

  <rect width="100%" height="100%" fill="red" />

  <circle cx="150" cy="100" r="80" fill="green" />

  <text x="150" y="125" font-size="60" text-anchor="middle" fill="white">SVG</text>

</svg>
```

```
<object data="image.svg" type="image/svg+xml" />
```

haut gauche = 0 

svg, viewbox
```
<svg width="100" height="100">
```

```
<svg width="200" height="200" viewBox="0 0 100 100">
```

rect
```
<rect x="10" y="10" width="30" height="30"/>
<rect x="60" y="10" rx="10" ry="10" width="30" height="30"/>
```

circle
```
<circle cx="25" cy="75" r="20"/>
```

ellipse,

ligne

```
<line x1="10" x2="50" y1="110" y2="150"/>
```

polylines, polygones
```
<polyline points="60, 110 65, 120 70, 115 75, 130 80, 125 85, 140 90, 135 95, 150 100, 145"/>
<polygon points="50, 160 55, 180 70, 180 60, 190 65, 205 50, 195 35, 205 40, 190 30, 180 45, 180"/>
```

path : toutes les formes
```
<path d="M20,230 Q40,205 50,230 T90,230" fill="none" stroke="blue" stroke-width="5"/>
```

Masjuscles, minuscules

move to
```
<svg width="200" height="200" xmlns="http://www.w3.org/2000/svg">
  <path d="M10 10"/>

  <!-- Indique la position -->
  <circle cx="10" cy="10" r="2" fill="red"/>
</svg>
```

L H V
```
L x y (ou l dx dy)
H x (ou h dx)
V y (ou v dy)
```

```
<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg">
  <path d="M10 10 H 90 V 90 H 10 L 10 10"/>

  <!-- Indique les points -->
  <circle cx="10" cy="10" r="2" fill="red"/>
  <circle cx="90" cy="90" r="2" fill="red"/>
  <circle cx="90" cy="10" r="2" fill="red"/>
  <circle cx="10" cy="90" r="2" fill="red"/>
</svg>
```

closepath Z
```
<path d="M10 10 H 90 V 90 H 10 Z" fill="transparent" stroke="black"/>
```

relatives
```
<path d="M10 10 h 80 v 80 h -80 Z" fill="transparent" stroke="black"/>
```

Pas vu : https://developer.mozilla.org/fr/docs/Web/SVG/Tutorial/Paths#commandes_pour_les_courbes
```

### Remplissage
```
<rect x="10" y="10" width="100" height="100"
       stroke="blue" fill="purple"
       stroke-opacity="0.8" fill-opacity="0.5"/>
```

stroke-width, stroke-linecap, stroke-linejoin, stroke-dasharray, 

css style
```
 <rect x="10" height="180" y="10" width="180" style="stroke: black; fill: red;"/>
```

```
<?xml version="1.0" standalone="no"?>
<svg width="200" height="200" xmlns="http://www.w3.org/2000/svg" version="1.1">
  <defs>
    <style type="text/css"><![CDATA[
       #MyRect {
         stroke: black;
         fill: red;
       }
    ]]></style>
  </defs>
  <rect x="10" height="180" y="10" width="180" id="MyRect"/>
</svg>
```

hover
```
 #MyRect:hover {
   stroke: black;
   fill: blue;
 }
```

fichier externe
```
<?xml version="1.0" standalone="no"?>
<?xml-stylesheet type="text/css" href="style.css"?>

<svg width="200" height="150" xmlns="http://www.w3.org/2000/svg" version="1.1">
  <rect height="10" width="10" id="MyRect"/>
</svg>
```

Pas vu : https://developer.mozilla.org/fr/docs/Web/SVG/Tutorial/Gradients

Pas vu : https://developer.mozilla.org/fr/docs/Web/SVG/Tutorial/Patterns

Texte
```
<text x="10" y="10">Hello World!</text>
```

font-family (en-US), font-style (en-US), font-weight (en-US), font-variant (en-US), font-stretch (en-US), font-size (en-US), font-size-adjust (en-US), kerning (en-US), letter-spacing (en-US), word-spacing (en-US) et text-decoration (en-US).

tspan
```
<text>
  This is <tspan font-weight="bold" fill="red">bold and red</tspan>
</text>
```

tref
```
<text id="example">This is an example text.</text>

<text>
    <tref xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#example" />
</text>
```

textPath
```
<path id="my_path" d="M 20,20 C 80,60 100,40 120,20" fill="transparent" />
<text>
  <textPath xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#my_path">
    A curve.
  </textPath>
</text>
```

### Transformations
```
<svg width="30" height="10">
    <g fill="red">
        <rect x="0" y="0" width="10" height="10" />
        <rect x="20" y="0" width="10" height="10" />
    </g>
</svg>
```

transform
```
<svg width="40" height="50" style="background-color:#bff;">
    <rect x="0" y="0" width="10" height="10" transform="translate(30,40)" />
</svg>
```

rotate
```
<svg width="31" height="31">
    <rect x="12" y="-10" width="20" height="20" transform="rotate(45)" />
</svg>
```

multiples
```
<svg width="40" height="50" style="background-color:#bff;">
    <rect x="0" y="0" width="10" height="10" transform="translate(30,40) rotate(45)" />
</svg>
```

scale
```
<svg width="100" height="100">
  <g transform="scale(2)">
    <rect width="50" height="50" />
  </g>
</svg>
```

svg dans svg
```
<svg xmlns="http://www.w3.org/2000/svg" version="1.1">
  <svg width="100" height="100" viewBox="0 0 50 50">
    <rect width="50" height="50" />
  </svg>
</svg>
```

Pas vu : https://developer.mozilla.org/fr/docs/Web/SVG/Tutorial/Clipping_and_masking

### Other content
Images
```
<svg version="1.1"
     xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
     width="200" height="200">
  <image x="90" y="-65" width="128" height="146" transform="rotate(45)"
     xlink:href="https://developer.mozilla.org/media/img/mdn-logo.png"/>
</svg>
```

Pas vu : foreignObject

Pas vu : https://developer.mozilla.org/fr/docs/Web/SVG/Tutorial/Filter_effects (ombres portées, etc...)

Pas vu : https://developer.mozilla.org/fr/docs/Web/SVG/Tutorial/SVG_fonts

### Images
```
<?xml version="1.0" standalone="no"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN"
  "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg width="5cm" height="4cm" version="1.1"
     xmlns="http://www.w3.org/2000/svg" xmlns:xlink= "http://www.w3.org/1999/xlink">
	<image xlink:href="firefox.jpg" x="0" y="0" height="50px" width="50px"/>
</svg>
```
