# Rubik's Cube Simulator

An interactive 3D Rubik's Cube simulator built with Three.js. Supports 2×2 to 5×5 cubes with smooth animations.

![Rubik's Cube Simulator](assets/preview.png)

## Features

- **Multiple Cube Sizes**: 2×2, 3×3, 4×4, and 5×5 cubes
- **3D Visualization**: Realistic 3D rendering with Three.js
- **Smooth Animations**: Layer rotations with easing animations
- **Interactive Controls**: Mouse/touch drag to rotate view
- **Standard Notation**: All standard Rubik's cube moves supported
- **Scramble & Solve**: Auto scramble and solve (reverse moves)
- **Keyboard Support**: Quick moves via keyboard shortcuts

## Project Structure

```
rubiks-cube-simulator/
├── index.html              # Main HTML entry point
├── css/
│   └── styles.css          # All styles with CSS variables
├── js/
│   ├── App.js              # Main application controller
│   ├── core/
│   │   ├── constants.js    # Configuration & constants
│   │   └── RubiksCube3D.js # 3D cube logic & rendering
│   ├── ui/
│   │   └── UIController.js # DOM interactions
│   └── utils/
│       └── MoveGenerator.js # Move button generation
├── assets/                 # Images, icons, etc.
└── README.md
```

## Getting Started

### Prerequisites

- Modern web browser with ES6 module support
- Local web server (for ES modules to work)

### Running Locally

1. Clone or download the project
2. Start a local server in the project directory:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js
   npx serve
   
   # Using PHP
   php -S localhost:8000
   ```
3. Open `http://localhost:8000` in your browser

## Usage

### Mouse/Touch Controls
- **Drag** on the cube viewport to rotate the view

### Keyboard Shortcuts
| Key | Move | With Shift |
|-----|------|------------|
| R | R (Right clockwise) | R' (counter-clockwise) |
| L | L (Left clockwise) | L' |
| U | U (Up clockwise) | U' |
| D | D (Down clockwise) | D' |
| F | F (Front clockwise) | F' |
| B | B (Back clockwise) | B' |
| M | M (Middle) | M' |
| E | E (Equator) | E' |
| S | S (Standing) | S' |

### Move Notation
- **Basic Moves**: R, L, U, D, F, B
- **Prime (')**: Counter-clockwise rotation
- **Double (2)**: 180° rotation
- **Wide (w)**: Two-layer rotation (4×4+)
- **Inner (2R, 2L, etc.)**: Second layer from face (4×4+)
- **Slice (M, E, S)**: Middle layer moves (odd cubes)

## Architecture

### Core Module (`js/core/`)

**constants.js**
- Configuration values (sizes, speeds, colors)
- Move definitions and mappings
- Keyboard shortcuts

**RubiksCube3D.js**
- Three.js scene setup
- Cubelet creation and management
- Layer rotation animations
- Camera controls

### UI Module (`js/ui/`)

**UIController.js**
- DOM element caching
- Event binding
- Status and history updates

### Utils Module (`js/utils/`)

**MoveGenerator.js**
- Dynamic move button generation
- Scramble move selection
- Size-specific move sets

### App Controller (`js/App.js`)

- Coordinates all modules
- Handles user interactions
- Manages application state

## Customization

### Colors
Edit `js/core/constants.js`:
```javascript
export const COLORS = {
    front: 0x00d95f,   // Green
    back: 0x0051ff,    // Blue
    right: 0xff2b2b,   // Red
    left: 0xff8c00,    // Orange
    top: 0xffffff,     // White
    bottom: 0xffd500,  // Yellow
};
```

### Animation Speed
Edit `js/core/constants.js`:
```javascript
export const CONFIG = {
    DEFAULT_ANIMATION_SPEED: 300,  // milliseconds
    MIN_ANIMATION_SPEED: 100,
    MAX_ANIMATION_SPEED: 800,
};
```

### Styling
Edit `css/styles.css` - uses CSS custom properties for easy theming:
```css
:root {
    --bg-primary: #0a0a0f;
    --accent-cyan: #00f5ff;
    --accent-magenta: #ff00aa;
    /* ... */
}
```

## Browser Support

- Chrome 61+
- Firefox 60+
- Safari 11+
- Edge 79+

Requires ES6 modules and WebGL support.

## Dependencies

- [Three.js](https://threejs.org/) r128 - 3D rendering
- [Google Fonts](https://fonts.google.com/) - Orbitron & JetBrains Mono

## Future Improvements

- [ ] Implement actual solving algorithm (Kociemba, CFOP)
- [ ] Add undo/redo functionality
- [ ] Save/load cube state
- [ ] Timer for speedcubing practice
- [ ] Move counter statistics
- [ ] Custom color schemes
- [ ] Mobile-optimized controls
- [ ] Cube state validation

## License

MIT License - feel free to use and modify.

## Contributing

Contributions welcome! Please feel free to submit issues and pull requests.
