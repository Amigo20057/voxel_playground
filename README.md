# Voxel Playground (Three.js)

An interactive 3D voxel editor that generates geometry using a user-defined function `voxel(x, y, z)`.

This project allows you to create procedural 3D shapes (spheres, shells, patterns, etc.) directly in the browser using JavaScript.

---

## Features

- Generate voxels using code (`x, y, z`)
- Custom color support
- Built-in examples (sphere, shell, chess pattern, etc.)
- Camera controls (rotate, zoom, pan)
- Coordinate rulers (X and Y axes)
- Adjustable grid size
- Quick execution via `Ctrl + Enter`

---

## How It Works

You define a function:

```js
return x === 0 && y === 0 && z === 0 ? RED : null;
```

### Rules

- `x, y, z` are voxel coordinates
- Return:
  - a color string (e.g. `"#ff0000"`) to render a voxel
  - `null` to leave the space empty

---

## Coordinate System

```
X → right
Y → up
Z → forward
```

The coordinate range depends on the grid size:

```
SIZE = 7  →  -3 .. 3
SIZE = 9  →  -4 .. 4
```

---

## Colors

You can return any valid color:

```js
return RED;
```

Example with condition:

```js
return x === 0 ? GREEN : null;
```

---

## Examples

### Sphere

```js
return Math.sqrt(x * x + y * y + z * z) <= 3 ? "#44ffee" : null;
```

### Chess Pattern

```js
return (x + y + z) % 2 === 0 ? "#ffffff" : "#222222";
```

### Shell

```js
return Math.max(Math.abs(x), Math.abs(y), Math.abs(z)) === 3 ? "#ff8833" : null;
```

---

## Controls

| Action        | Input       |
| ------------- | ----------- |
| Rotate camera | Left mouse  |
| Zoom          | Mouse wheel |
| Pan           | Right mouse |


---

## Configuration

You can modify:

- Grid size (SIZE)
- Voxel generation code
- Colors

---

## Technologies

- Three.js
- CodeMirror
- Vanilla JavaScript
- HTML5 Canvas (rulers)

---

## Getting Started

Open `index.html` in your browser:

```bash
open index.html
```

Alternatively, run via a local development server.


