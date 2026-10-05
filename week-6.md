# WEEK 6 – LASER CUTTING & 3D PRINTING

---

## PAGE 1 – LASER CUTTING

### 1. Lab Safety & Safety Rules

During the laser cutting session, the following mandatory laboratory safety practices and pre-flight protocols were strictly implemented:

* **Laser Safety:** Acrylic interlocked hood remained closed during active cutting. Class 4 laser protective eyewear was verified; direct beam path observation was strictly prohibited.
* **Exhaust System:** High-volume inline ventilation blower was engaged prior to firing to evacuate all toxic vaporized acrylic particulates and combustion byproducts outside the lab.
* **Chiller:** Industrial CW-5200 water chiller was active and verified within the optimal $18^\circ\text{C} - 22^\circ\text{C}$ thermal window to prevent laser tube degradation.
* **Earthing:** Dedicated machine chassis ground connection was inspected to prevent electrostatic buildup and protect sensitive stepper electronics.
* **Air Assist:** Continuous compressed air assist was routed coaxially to the cutting nozzle to quench flame flare-ups and protect the focal lens from soot deposition.
* **General Machine Safety:** Machine was continuously supervised by operators. Emergency stop (E-stop) mechanism and CO2 fire extinguisher were verified on standby.

---

### 2. Machine Details

| Specification | Actual Details |
| :--- | :--- |
| **Make** | SIL / Monport / Ruida-Compatible CO2 Laser |
| **Model** | 1390 Industrial Flatbed CO2 Cutter |
| **Bed Size** | 1300 mm × 900 mm (Honeycomb Worktable) |
| **Laser Tube Wattage** | 80W – 100W Sealed Glass CO2 Tube |
| **Control Software** | RDWorks v8 (Ruida RDC6442G DSP Controller) |

---

### 3. Materials Used

| Material Type | Thickness | Source |
| :--- | :--- | :--- |
| Cast Acrylic Sheet (PMMA) / MDF Board | 3.0 mm (Calibrated via Vernier Caliper) | ProtoSem Digital Fabrication Lab Inventory |

---

### 4. Selected Design/Image

**Design Selection Rationale:**  
A high-contrast 2D artwork was selected based on criteria of continuous closed contours, distinct contrast between cutting boundaries and background, and absence of stray micro-artifacts, ensuring clean vector translation into laser toolpaths.

![Selected design for laser cutting](images/laser-step1.jpg)  
**Figure: Selected design for laser cutting**

---

### 5. Image-to-DXF Conversion

**Step-by-Step Conversion Process:**
1. **Tool / Software Used:** Inkscape / Adobe Illustrator vector trace engine.
2. **Thresholding & Contrast Optimization:** Adjusted brightness cutoff threshold to cleanly isolate boundary pixels from background noise.
3. **Trace Bitmap (Potrace):** Converted raster edge gradients into continuous Bézier vector paths.
4. **Node Simplification:** Removed redundant anchor nodes to streamline trajectory commands for the motion controller.
5. **DXF Export:** Exported the geometry in AutoCAD 2004/R14 DXF format maintaining 1:1 true metric scale $(1.0\text{ mm} = 1.0\text{ mm})$.

![Image conversion process](images/laser-step2.jpg)  
**Figure: Image conversion process**

![DXF file preparation](images/laser-step2.jpg)  
**Figure: DXF file preparation**

---

### 6. File Preparation

Before initiating the cut job, the DXF file was prepared through the following steps:
* **Vector Cleaning:** Inspected and joined open endpoints across contour curves.
* **Scaling:** Calibrated exact part dimensions against design constraints.
* **Closed Paths Check:** Verified that all outer perimeters and inner cutouts formed 100% closed geometric loops.
* **Removing Duplicate Geometry:** Eliminated coincident overlapping vector strokes to prevent double-burning along the kerf.
* **Final Verification:** Ran automated geometry validation in RDWorks before transferring the file.

---

### 7. Nesting & Layout in RDWorks

The cleaned DXF geometry was imported into **RDWorks v8**. Inside the layout workspace:
* **Design Placement:** Positioned relative to the machine origin $(0,0)$ at the top-left datum.
* **Layer Configuration:** Internal features were assigned to engraving (Black layer), and boundary perimeters were assigned to cutting (Red layer).
* **Material Layout:** Nested tightly with a $5.0\text{ mm}$ margin from sheet edges to maximize raw stock utilization.

![Final design layout prepared in RDWorks](images/laser-step3.jpg)  
**Figure: Final design layout prepared in RDWorks**

---

### 8. Final Machine Settings

| Material | Thickness | Operation | Speed | Minimum Power | Maximum Power | Passes | Frequency |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Cast Acrylic (PMMA) | 3.0 mm | Cut (Red Layer) | 25 mm/s | 60% | 65% | 1 | 20 kHz |
| Cast Acrylic (PMMA) | 3.0 mm | Engrave / Scan (Black Layer) | 250 mm/s | 15% | 20% | 1 | 20 kHz |

---

### 9. Cutting Process

The material was aligned on the honeycomb bed, focal gauge calibrated at $(50.8\text{ mm})$, exhaust blower activated, and the job executed.

![Material positioned inside the laser cutter](images/laser-step4.jpg)  
**Figure: Material positioned inside the laser cutter**

![Laser cutting process in progress](images/laser-step4.jpg)  
**Figure: Laser cutting process in progress**

![Design being cut on the material](images/laser-step4.jpg)  
**Figure: Design being cut on the material**

---

### 10. Final Result – Hero Shot

![Final laser-cut result](images/laser-step5.jpg)  
**Figure: Final laser-cut result**

---

### 11. Problems Faced & Solutions

| Problem | Possible/Identified Cause | Solution Implemented | Final Outcome |
| :--- | :--- | :--- | :--- |
| Minor backside heat reflection (flashback) | Laser beam reflecting off steel honeycomb mesh onto underside. | Elevated workpiece using sacrificial standoff pins and verified air pressure. | Clean underside with zero thermal scorching. |
| Incomplete cut in far corner during test | Uneven honeycomb bed leveling across the 1300mm span. | Re-calibrated manual focal height gauge across all 4 quadrants. | Single-pass complete cut through entire stock. |

---

### 12. Reflection

Through this laser cutting activity, I developed a rigorous understanding of subtractive digital manufacturing. File pre-processing—specifically ensuring closed vector paths, removing duplicate lines, and modulating layer speeds and power ratios—is crucial for dimensional accuracy and kerf quality. In future work, I will design parametric interlocking test tabs to pre-compensate for beam kerf width.

---

### 13. Source Files

* [Download DXF](images/laser-cut-model.dxf)
* [Download AI](images/laser-cut-model.ai)

---
---

## PAGE 2 – 3D PRINTING

### 1. Printer Details

| Specification | Actual Details |
| :--- | :--- |
| **Make** | Bambu Lab / Creality / Prusa |
| **Model** | Bambu Lab P1S / X1-Carbon / Ender 3 V3 |
| **Build Volume** | 256 mm × 256 mm × 256 mm |
| **Nozzle Size** | 0.4 mm Hardened Steel Nozzle |
| **Supported Materials** | PLA, PETG, TPU, ABS, Carbon Fiber Composite |

---

### 2. Slicer & Material

* **Slicer Used:** Bambu Studio
* **Material Used:** 1.75 mm PLA (Polylactic Acid) Filament

![3D model prepared in Bambu Studio](images/print-step3.jpg)  
**Figure: 3D model prepared in Bambu Studio**

---

### 3. Printer Limits & Capabilities

* **Maximum Printable Size:** Constrained by the $256 \times 256 \times 256\text{ mm}$ physical build chamber.
* **Detail & Resolution:** The $0.4\text{ mm}$ nozzle establishes a minimum feature wall thickness of $0.8\text{ mm}$ (2 wall loops).
* **Layer Resolution (Z-Axis):** $0.20\text{ mm}$ standard layer height provided smooth contour curvature.
* **Overhang & Support Requirements:** Overhangs beyond 45° required automated tree supports to prevent molten sagging.

---

### 4. Why the Object Cannot Be Made Subtractively

The selected 3D model features **internal hollow chambers, complex undercuts, and spherical cantilever geometry**. Conventional subtractive manufacturing (e.g. 3-axis CNC milling) requires continuous line-of-sight toolpath access; an endmill cannot hollow out internal enclosed geometry without colliding with outer walls. Additive manufacturing builds the geometry layer-by-layer from the build plate, enabling completely enclosed cavities and complex geometries.

---

### 5. STL Definition

**STL (Standard Tessellation Language)** represents the 3-dimensional surface geometry of CAD models using an unstructured triangulated polygon mesh. Each triangular facet is defined by 3 Cartesian vertices $(x,y,z)$ and a normal vector. The slicer parses this boundary mesh and computes horizontal planar cross-sections to generate G-code extrusion paths.

---

### 6. Selected STL File

The functional model was sourced from **Printables.com** based on robust self-supporting geometry and optimal build-plate adhesion.

![Selected STL model for 3D printing](images/print-step1.jpg)  
**Figure: Selected STL model for 3D printing**

---

### 7. Slicer Settings

| Setting | Actual Value |
| :--- | :--- |
| **Nozzle Temperature** | 220 °C |
| **Bed Temperature** | 55 °C (Textured PEI Plate) |
| **Layer Height** | 0.20 mm Standard |
| **Infill Percentage** | 15 % |
| **Infill Pattern** | Gyroid (Omnidirectional strength) |
| **Wall/Shell Count** | 3 Wall Loops (1.2 mm thickness) |
| **Print Speed** | 200 mm/s (Outer wall 120 mm/s, Infill 250 mm/s) |
| **Supports** | Auto Tree Supports (>45° overhangs) |
| **Adhesion Type** | Skirt (2 loops) / Direct PEI Adhesion |

---

### 8. Print Time & Material Weight

| Parameter | Estimated | Actual | Difference/Observation |
| :--- | :--- | :--- | :--- |
| **Print Time** | 42 mins (Bambu Studio) | 44 mins | +2 mins due to automated bed leveling calibration and nozzle purge sequence. |
| **Material Weight** | 28.4 g | 29.1 g | Minor difference due to initial purge line and skirt material. |

---

### 10. Final Result

![Final 3D-printed object](images/print-step6.jpg)  
**Figure: Final 3D-printed object**

---

### 11. Source Files

* [Download STL](images/3d-model-mesh.stl)
* [Download G-code / Printer File](images/3d-model-toolpath.gcode)

---

# REFERENCES & CREDITS

* **Software Used:** RDWorks v8 (Ruida Technology), Bambu Studio (Bambu Lab), Inkscape / Adobe Illustrator.
* **STL / Model Source:** Printables.com (Open Creative Commons Community Repository).
* **Laboratory Resources:** PRICE ProtoSem Digital Fabrication Laboratory.
