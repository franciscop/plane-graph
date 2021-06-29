# Plane Graph

Generate beautiful euclidean graphs with HTML:

<table>
  <tr>
    <td>
      <img width="300px" src="./examples/simple.svg" />
    </td>
    <td>
      <img width="300px" src="./examples/scale.svg" />
    </td>
    <td>
      <img width="300px" src="./examples/complete.svg" />
    </td>
  </tr>
    <tr>
      <td align="center">Three of the building blocks</td>
      <td align="center">Scaled and with coordinates</td>
      <td align="center">Many options shown together</td>
    </tr>
</table>

```html
<plane-graph width="200" height="200">
  <point label="point" x="7" y="7"></point>
  <line label="line" from="0,0" to="4,8"></line>
  <vector label="vector" to="8,4"></vector>
</plane-graph>

<plane-graph width="200" height="200" x="3.9" y="3.9" units>
  <vector label="v" to="3,3.2" axis></vector>
</plane-graph>

<plane-graph width="200" height="200" x="4.9" y="4.9" units>
  <vector label="b" color="blue" from="3,4" to="4,2" axis></vector>
  <vector label="a" color="red" from="0,0" to="3,4" axis></vector>
  <vector label="c" from="0,0" to="4,2"></vector>
</plane-graph>
```

## Getting started

To use this library as usual you'll need three things. First, import it from a CDN; put this line anywhere in your HTML:

```
<script src="https://cdn.jsdelivr.net/npm/plane-graph"></script>
```

Now let's draw a graph anywhere within your HTML:

```html
<plane-graph width="200" height="200" grid>
  <vector label="u" to="8,4"></vector>
  <vector label="v" to="4,8"></vector>
</plane-graph>
```

Finally, if this is going to be included in a commercial or for-profit project make sure to buy a license:

\$9 BUY A LICENSE

## Documentation

### \<plane-graph>

| attribute | default      | description                                                    |
| --------- | ------------ | -------------------------------------------------------------- |
| `width`   | `"600"`      | The width of the containing SVG element (pixels)               |
| `height`  | `"400"`      | The height of the containing SVG element (pixels)              |
| `x`       | `"0,10"`     | The x-coordinates of the graph to fit into the SVG             |
| `y`       | `"0,10"`     | The y-coordinates of the graph to fit into the SVG             |
| `labels`  | `['x', 'y']` | [BUG] Text to display alongside both axis (x,y)                |
| `units`   | `"false"`    | Show the numbers on each of the axis                           |
| `grid`    | `"1"`        | The size of the grid, or `false` to hide it                    |
| `dark`    | _mediaquery_ | Use dark theme (true), light theme (false) or auto (undefined) |
| `pad`     | `"24"`       | The space around the content to avoid SVG clipping             |

### \<point>

| attribute | default   | description                                       |
| --------- | --------- | ------------------------------------------------- |
| `x`       | 🚫        | The horizontal coordinate where to draw the point |
| `y`       | 🚫        | The vertical coordinate where to draw the point   |
| `label`   | 🚫        | The text to draw on top of the point              |
| `color`   | `"black"` | The color of the point, it can be a name or hexa  |
| `axis`    | `"false"` | Draw the horizontal and vertical coordinate lines |

### \<line>

| attribute | default   | description                                      |
| --------- | --------- | ------------------------------------------------ |
| `to`      | 🚫        | The point where the line/segment ends            |
| `from`    | `"0,0"`   | The point where the line/segment starts          |
| `label`   | 🚫        | Text to draw on the middle of the line           |
| `color`   | `"black"` | The color of the line, it can be a name or hexa  |
| `width`   | `"1.75"`  | The stroke width of the line to draw             |
| `dashed`  | `"false"` | Show as dashes (true) or as a solid line (false) |

### \<vector>

### \<label>

### \<text>

## Examples

## Environments

### Javascript

```
npm i plane-graph
```

### React

### Vue

### Node.js

You can run this on the Node.js side to generate static SVGs as well. To do so, you'll need to install `jsdom` on your own and then use it like this:

```js
import { JSDOM } from "jsdom";
import graph from "plane-graph";

// Make some of these variable accessible from anywhere
const dom = new JSDOM();
global.window = dom.window;
global.document = window.document;
global.DOMParser = window.DOMParser;

// Render the HTML to SVG
const svg = graph(`
  <plane-graph width="200" height="200">
    <point label="point" x="7" y="7"></point>
    <line label="line" from="0,0" to="4,8"></line>
    <vector label="vector" to="8,4"></vector>
  </plane-graph>
`);

console.log(svg);
// <svg width="200" height="200" viewBox="...">...</svg>
```
