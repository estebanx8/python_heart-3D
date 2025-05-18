# Heart Animation Project

A Python-based animated heart visualization using Tkinter, mathematical transformations, and dynamic color generation.

## Features

- **Tkinter GUI**: Renders the animation in a resizable window (1000x600 pixels).
- **3D-to-2D Projection**: Uses parametric equations to simulate depth and perspective.
- **ASCII Art Style**: Renders characters (`.,-~:;=!*#$@@`) with varying brightness for a retro aesthetic.
- **Dynamic Color Generation**: Random RGB colors applied to characters for a vibrant effect.
- **Z-Buffering**: Depth management to handle overlapping elements and occlusion.
- **Real-Time Rotation**: Smooth animation updates every 80ms using trigonometry (`sin`/`cos`).

## Requirements

- Python 3.x
- `tkinter` (included in Python standard library)
- `numpy` (for array operations)

## Installation

1. Clone the repository or download `corazon.py`.
2. Install dependencies:
   ```bash
   pip install numpy 
## Usage

Run the script:
python corazon.py
A window titled "Heart Animation" will open, displaying a rotating heart with randomly colored characters.

## Code Structure

### Key Components

1. **`Heart Class`**:
   - Inherits from tkinter.Frame.
   - Manages the canvas, objects, and animation loop.

2. **`create_obj` Method**:
   - Initializes 900 text objects on the canvas.

3. **`draw` Method**:
   - Updates text character, position, and color for each object.

4. **`update` Method**:
   - Core animation logic:
     - Computes heart shape using parametric equations.
     - Applies rotation via sin/cos transformations.
     - Uses z-buffering to determine visible characters.
     - Assigns colors and ASCII characters based on depth.

### Mathematical Details
- Heart shape derived from the equation:  
  `r = 0.4 + 0.04*(0.4 + 0.4*sin(n*6 + y*2))**8`
- 3D coordinates projected to 2D with perspective scaling `(p = 1 + az/2)`.
- Depth-based character indexing: `idx = int(zbuffer[num]/maxz*13)`.

## Contribution

Contributions are welcome! Open an issue or PR for:
- Performance optimizations
- Enhanced visual effects
- Additional documentation

## License

Open-source. Credit to original author [JETG](https://github.com/estebanx8).
```

This README provides a concise yet comprehensive overview, emphasizing technical depth while remaining accessible. It highlights the core algorithms, dependencies, and structure, making it easy for developers to understand and extend the project.
