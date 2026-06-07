# koumi - 3D Frame Structure Analysis

**koumi** is a browser-based 3D frame structure analysis tool using the stiffness matrix method.  
No installation required — just open `koumi.html` in any modern browser.

🔗 **[Try it online](https://31jothi-lang.github.io/koumi/koumi.html)**

---

## Features

- 3D frame visualization with interactive rotation and zoom
- Seismic load analysis (inverse triangle, uniform, top-floor distribution)
- Node load input (Fx, Fy, Fz) for any node
- Deformation diagram with adjustable magnification
- Story drift calculation
- Member stress diagram (axial force, shear, bending moment)
- Result export as text file

## Background

This tool is a JavaScript port of **ana_3d**, a 3D frame analysis program originally written in F-BASIC/FreeBASIC around 2003 by the author (*tecnica de vida*).

The core engine faithfully implements:
- **SUB1**: Member stiffness matrix (12×12) with coordinate transformation
- **draw1.SUB**: 3D projection using R1/R2/R3 rotation angles
- Cholesky-based solver → replaced with Gaussian elimination

## Usage

1. Set number of spans (X, Y) and stories
2. Set span length and story height
3. Click **▶ Generate & Analyze**
4. Apply seismic loads or node loads
5. Rotate the model by dragging, zoom with mouse wheel
6. Click **Stress** and select a member to view the stress diagram

## Theory

The stiffness matrix method (Direct Stiffness Method) is used:

```
[K]{u} = {F}
```

- **K**: Global stiffness matrix (assembled from 12×12 member matrices)
- **u**: Displacement vector (6 DOF per node: Ux, Uy, Uz, θx, θy, θz)
- **F**: Load vector

## License

MIT License — free to use, modify, and distribute with attribution.

## Author

Copyright (c) 2026 Hiroshi  
Original program: *ana_3d* (F-BASIC version, 2003) — *tecnica de vida*
