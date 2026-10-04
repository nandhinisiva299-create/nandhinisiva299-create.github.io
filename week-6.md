# WEEK 6 – LASER CUTTING & 3D PRINTING

> **Digital Fabrication Lab Portfolio**  
> *Transforming 2D digital artwork and 3D geometric models into physical functional prototypes.*

---

## 🔥 PART 1: LASER CUTTING

Laser cutting is a high-precision **subtractive manufacturing** process. In this activity, we selected a 2D design, prepared and converted the artwork into compatible vector toolpaths, configured the cutting layers and power parameters inside **RDWorks**, and executed the cut using the CO2 laser machine.

### 🔄 Process Pipeline
```
Image Selection ➔ Image Conversion/Preparation ➔ RDWorks Setup ➔ Laser Cutting ➔ Final Model
```

---

### 📸 Step-by-Step Practical Experience & Photo Layout

#### Step 1 – Selecting the Image
| **Explanation (LEFT)** | **Photo / Graphic (RIGHT)** |
| :--- | :--- |
| **Design Selection & Criteria**<br>We began by selecting a high-contrast graphic design suitable for laser cutting. The design was assessed for clear boundary outlines, enclosed loops, and vectorization feasibility to guarantee sharp contours during laser translation. | ![Original Selected Image](assets/laser-step1.png)<br>*Caption: Photo of the original selected 2D design ready for conversion.* |

---

#### Step 2 – Preparing the Design
| **Photo / Graphic (LEFT)** | **Explanation (RIGHT)** |
| :--- | :--- |
| ![Prepared Vector Design](assets/laser-step2.png)<br>*Caption: Vectorized contours and cleaned cut paths in DXF format.* | **Image Conversion & Path Cleaning**<br>The raw image was converted into vector paths (DXF/AI). We adjusted thresholds, traced high-resolution contours, eliminated redundant overlapping vectors, and ensured all cutting profiles formed closed geometric loops. |

---

#### Step 3 – RDWorks
| **Explanation (LEFT)** | **Photo / Graphic (RIGHT)** |
| :--- | :--- |
| **Importing & Layer Configuration in RDWorks**<br>The cleaned vector design was imported into **RDWorks**. Inside the workspace, we arranged the orientation relative to machine origin $(0,0)$, set distinct speed and power parameters for cutting vs engraving layers, and simulated the laser path. | ![RDWorks Interface Setup](assets/laser-step3.png)<br>*Caption: Screenshot of design layout and parameter configuration in RDWorks.* |

---

#### Step 4 – Laser Cutting
| **Photo / Graphic (LEFT)** | **Explanation (RIGHT)** |
| :--- | :--- |
| ![Laser Cutting in Action](assets/laser-step4.png)<br>*Caption: Active CO2 laser beam cutting through the workpiece with air assist.* | **Machine Setup & Execution**<br>The file was sent to the laser cutter. We positioned the material on the honeycomb bed, calibrated the focal height using the focus gauge, activated the exhaust ventilation and air assist, and executed the cutting job. |

---

#### Step 5 – Final Laser-Cut Model
| **Explanation (LEFT)** | **Photo / Graphic (RIGHT)** |
| :--- | :--- |
| **Completed Physical Model & Inspection**<br>After ventilating the chamber, the completed part was removed. The edges exhibited crisp vertical cuts with zero charring or burrs, perfectly matching the original digital vector geometry. | ![Final Laser Cut Part](assets/laser-step5.png)<br>*Caption: Final laser-cut physical prototype evaluated for edge accuracy.* |

---

## 🖨️ PART 2: 3D PRINTING

3D printing is an **additive manufacturing** technique that builds 3-dimensional objects layer by layer. For this activity, we sourced a functional 3D CAD design from **Printables.com**, downloaded the **STL mesh geometry**, configured infill, speeds, and layer heights in **Bambu Studio**, and produced the physical object on a 3D printer.

### 🔄 Process Pipeline
```
Printables.com ➔ STL File Download ➔ Bambu Studio Import ➔ Model Preparation & Slicing ➔ 3D Printing ➔ Final Model
```

---

### 📸 Step-by-Step Practical Experience & Photo Layout

#### Step 1 – Selecting the 3D Model
| **Explanation (LEFT)** | **Photo / Graphic (RIGHT)** |
| :--- | :--- |
| **Model Discovery on Printables.com**<br>We explored **Printables.com** to select a community-tested 3D model designed for FDM printing. The model was chosen based on functional utility, overhang angles, self-supporting geometry, and dimensional fit. | ![Printables.com Model Selection](assets/print-step1.png)<br>*Caption: Screenshot of the selected functional 3D model on Printables.com.* |

---

#### Step 2 – STL File
| **Photo / Graphic (LEFT)** | **Explanation (RIGHT)** |
| :--- | :--- |
| ![STL Mesh Wireframe](assets/print-step2.png)<br>*Caption: 3D surface geometry encoded in triangular STL mesh format.* | **Acquiring the STL Geometry**<br>The model was downloaded in **STL (Standard Tessellation Language)** format. We verified that the triangular mesh was non-manifold and watertight, ready for layer-by-layer planar slicing. |

---

#### Step 3 – Bambu Studio
| **Explanation (LEFT)** | **Photo / Graphic (RIGHT)** |
| :--- | :--- |
| **Importing STL into Bambu Studio**<br>The STL file was imported onto the virtual build plate in **Bambu Studio**. We matched the machine profile with our printer, selected a 0.4mm nozzle, and applied calibrated PLA filament thermal presets. | ![Bambu Studio Workspace](assets/print-step3.png)<br>*Caption: Screenshot of the 3D model imported and oriented in Bambu Studio.* |

---

#### Step 4 – Preparing & Slicing
| **Photo / Graphic (LEFT)** | **Explanation (RIGHT)** |
| :--- | :--- |
| ![Bambu Studio Slicing Preview](assets/print-step4.png)<br>*Caption: Bambu Studio G-code toolpath visualization showing layers and Gyroid infill.* | **Slicing & Toolpath Generation**<br>We set a **0.20mm Standard layer height**, **15% Gyroid infill** for omnidirectional strength, and generated tree supports for delicate cantilevers. Bambu Studio sliced the model and computed the print time and material usage. |

---

#### Step 5 – 3D Printing
| **Explanation (LEFT)** | **Photo / Graphic (RIGHT)** |
| :--- | :--- |
| **Additive Manufacturing Process**<br>The sliced G-code was sent to the printer. With the hotend at 220°C and bed at 55°C, the direct-drive extruder precisely laid down layers of molten filament onto the textured PEI build plate. | ![3D Printing in Progress](assets/print-step5.png)<br>*Caption: 3D printer actively depositing fused filament layers.* |

---

#### Step 6 – Final 3D Model
| **Photo / Graphic (LEFT)** | **Explanation (RIGHT)** |
| :--- | :--- |
| ![Final 3D Printed Part](assets/print-step6.png)<br>*Caption: Final 3D printed physical prototype with smooth surface finish.* | **Post-Processing & Inspection**<br>Once cooled, the part was popped off the spring steel plate and support interfaces were cleaned. Caliper inspection confirmed high dimensional accuracy and seamless inter-layer adhesion. |

---

## 🎯 WEEK 6 LEARNING OUTCOME

This week provided practical, end-to-end exposure to modern **digital design to physical manufacturing** workflows:

1. **Subtractive vs Additive Mastery:**
   - **Laser Cutting (RDWorks):** Understood 2D vector preparation (DXF), laser speed/power modulation, and focal calibration for clean planar cuts.
   - **3D Printing (Bambu Studio):** Understood 3D polygonal meshes (STL), slicer parameters (layer height, gyroid infill, support generation), and thermal extrusion dynamics.

2. **Core Takeaway:**  
   The precision and quality of physical fabrication depend fundamentally on meticulous **digital file preparation** and software pre-processing before sending jobs to the machine.
