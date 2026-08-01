# AutoCAD Project 3 — Commercial Office Space Layout

## Project Overview

This project focuses on the design and documentation of a professional **Commercial Office Space Layout** in Autodesk AutoCAD.

The project demonstrates five core CAD skills:

* External References (XREF)
* Dynamic Blocks
* Attribute-driven furniture
* Automated Bill of Materials (BOM) extraction
* Practical office space planning with clear circulation and egress

The workflow covers the development of the architectural shell, creation of reusable furniture blocks, XREF integration, furniture placement, attribute extraction, BOM generation, annotation, and final plotting.

---

## Objectives

The main objectives of this project are to:

* Develop a complete architectural shell for a commercial office.
* Create dynamic furniture blocks for desks, chairs, meeting tables, and cabinets.
* Add attributes to furniture blocks for item identification and cost information.
* Reference the architectural shell using an **XREF Overlay**.
* Arrange furniture according to functional office zones.
* Maintain clear circulation and egress paths.
* Calculate and document office occupancy.
* Extract furniture information using AutoCAD Data Extraction.
* Generate a structured Bill of Materials.
* Produce a professionally annotated and plot-ready final layout.

---

## Software Used

* Autodesk AutoCAD
* Microsoft Excel
* PDF Plotting

### File Formats

* `.DWG` — AutoCAD drawings
* `.XLSX` — Bill of Materials
* `.PDF` — Final plotted layout
* `.MD` — Project documentation

---

## Project Deliverables

The project submission consists of the following files:

| File                      | Description                                                                                      |
| ------------------------- | ------------------------------------------------------------------------------------------------ |
| `Architectural Shell.dwg` | Architectural walls, doors, windows, columns, staircase, corridors, entrance, and emergency exit |
| `Office Layout.dwg`       | Furniture arrangement and space planning using the architectural shell as an XREF                |
| `Dynamic Blocks.dwg`      | Dynamic desk, chair, meeting table, and cabinet blocks with attributes                           |
| `Bill of Materials.xlsx`  | Extracted furniture information, quantities, costs, and subtotals                                |
| `Final PDF Layout.pdf`    | Final plotted and annotated office layout                                                        |
| `README.md`               | Project documentation                                                                            |

---

## Project Workflow

### 1. Architectural Shell

The architectural shell was developed first as a separate AutoCAD drawing.

The shell includes:

* Exterior walls
* Interior partitions
* Doors
* Windows
* Structural columns
* Staircase
* Corridors
* Main entrance
* Emergency exit

The architectural shell is kept separate from the furniture layout so that it can be referenced externally.

---

### 2. Dynamic Blocks

Four furniture types are developed as dynamic blocks:

* Office Desk
* Chair
* Meeting Table
* Cabinet

Dynamic parameters and actions are used to make the blocks reusable and adjustable.

The implemented block functions include:

* Linear Stretch
* Rotation
* Flip
* Visibility where applicable

Each block is tested in the Block Editor and after insertion into the drawing.

---

### 3. Furniture Attributes

Attributes are incorporated into the furniture blocks to store information required for the Bill of Materials.

Examples of the required attributes include:

**Office Desk**

* `ITEM_ID`
* `NAME`
* `LENGTH`
* `WIDTH`
* `COST`

**Chair**

* `ITEM_ID`
* `NAME`
* `QTY`
* `COST`

**Meeting Table**

* `ITEM_ID`
* `MATERIAL`
* `COST`

**Cabinet**

* `ITEM_ID`
* `CAPACITY`
* `COST`

These attributes allow furniture information to be extracted directly from the AutoCAD drawing.

---

### 4. XREF Integration

The architectural shell is referenced into `Office Layout.dwg` using:

**XATTACH → Reference Type: Overlay**

The XREF is maintained as an external reference and is **not exploded**.

A relative reference path is used so that the external reference can remain functional if the project folder is moved.

The XREF-derived geometry is maintained on a dedicated `XREF` layer.

---

### 5. Office Space Planning

Furniture is arranged according to the functional requirements of each office zone.

The planned areas include:

* Reception
* Waiting Area
* Open Workstation Area
* Manager Cabins
* Conference Room
* Pantry
* Washrooms
* Printer / Storage Area

Furniture placement considers functionality, circulation, accessibility, and emergency egress.

For the open workstation area, the project brief specifies a minimum clear aisle of approximately **900 mm (36 in)** between workstation rows.

---

## Occupancy

The project brief provides the following occupancy template:

| Category               | Count | Seats Each | Subtotal |
| ---------------------- | ----: | ---------: | -------: |
| Open Workstation Desks |    20 |          1 |       20 |
| Manager Cabins         |     3 |          1 |        3 |
| Conference Room        |     1 |         12 |       12 |
| Reception + Waiting    | 1 + 6 |      1 + 6 |        7 |
| **Total Occupancy**    |       |            |   **42** |

The final occupancy count should correspond to the actual furniture and seating arrangement shown in the completed drawing.

---

## Egress and Circulation

Clear circulation is maintained throughout the office layout.

The design considers:

* Continuous paths from work areas to exits
* Clear corridors
* Unobstructed emergency exit access
* Furniture placement outside primary walkways
* Chair swing clearance
* Cabinet door clearance

The project brief also specifies that the main entrance and emergency exit should not be located on the same wall.

---

## Bill of Materials

The Bill of Materials is generated using AutoCAD's **Data Extraction Wizard (`EATTEXT`)**.

The extraction process includes:

1. Creating a new data extraction.
2. Selecting the Office Layout drawing as the source.
3. Selecting block-based objects.
4. Selecting the required furniture blocks and attributes.
5. Adding a count/quantity column.
6. Exporting the extracted information as an Excel file.
7. Organizing the resulting data into a structured BOM.

The final BOM contains:

| Column    | Description                 |
| --------- | --------------------------- |
| Item ID   | Unique furniture identifier |
| Furniture | Furniture type/name         |
| Quantity  | Number of items             |
| Cost      | Cost per item               |
| Subtotal  | Quantity × Cost             |

The completed file is saved as:

`Bill of Materials.xlsx`

---

## Layer Organization

The drawing follows a structured layer system:

| Layer    | Purpose                         |
| -------- | ------------------------------- |
| `A-WALL` | Walls                           |
| `A-DOOR` | Doors                           |
| `A-WIND` | Windows                         |
| `A-COLS` | Structural columns              |
| `FURN`   | Furniture                       |
| `TEXT`   | Labels and notes                |
| `DIMS`   | Dimensions                      |
| `XREF`   | External reference              |
| `CENTER` | Centerlines                     |
| `HATCH`  | Floor/material hatches          |
| `CONST`  | Construction/reference geometry |

This layer organization helps maintain a clean and manageable CAD drawing.

---

## Key AutoCAD Commands

### Architectural Drawing

```text
LINE
PLINE
MLINE
OFFSET
ARC
```

### Blocks and Dynamic Blocks

```text
BLOCK
WBLOCK
BEDIT
```

### Attributes

```text
ATTDEF
BATTMAN
EATTEDIT
```

### External References

```text
XATTACH
XREF
```

### Data Extraction

```text
EATTEXT
```

### Layers

```text
LAYER
```

### Dimensions

```text
DIMLINEAR
DIMALIGNED
QDIM
```

### Geometric Constraints

```text
GCPERPENDICULAR
GCPARALLEL
GCEQUAL
GCCOINCIDENT
```

### Plotting

```text
PLOT
```

---

## Drawing Standards and Final Plot

The final layout is prepared as a professional plot-ready drawing.

The plotted sheet includes:

* Title block
* Drawing title
* Author
* Date
* Revision information
* Dimensions
* Room names
* Area labels
* Furniture labels or keyed legend
* North arrow
* Graphic scale bar
* Defined viewport scale

The viewport scale is explicitly set rather than being left on a fit-to-page setting.

The completed drawing is exported as the **Final PDF Layout**.

---

## Screenshots

The project documentation includes screenshots demonstrating the major stages of the workflow:

1. Full office layout plan
2. Dynamic block being stretched/edited in Block Editor
3. Data Extraction Wizard
4. Final Bill of Materials
5. Final plotted drawing/PDF layout

These screenshots provide visual evidence of the CAD workflow and final results.

---

## Project Highlights

This project demonstrates practical application of:

* Architectural CAD drafting
* Commercial office space planning
* Dynamic block creation
* Block attributes
* XREF management
* Layer organization
* Furniture planning
* Occupancy calculation
* Egress and circulation planning
* Automated data extraction
* Bill of Materials generation
* Professional annotation
* CAD plotting and documentation

---

## Submission Checklist

Before submission, the following items are verified:

* [ ] XREF is set to **Overlay**
* [ ] XREF has not been exploded
* [ ] Dynamic blocks work correctly after insertion
* [ ] Furniture attributes are filled in
* [ ] BOM quantities match the furniture placed in the drawing
* [ ] Egress paths remain unobstructed
* [ ] Title block information is complete
* [ ] Final PDF has been plotted
* [ ] All required project deliverables are included

---

## Author

**Kaneez Zainab**

**Project:** AutoCAD Project 3 — Commercial Office Space Layout

**Purpose:** Internship Project / CAD Portfolio

---

## Conclusion

The Commercial Office Space Layout demonstrates a complete AutoCAD workflow from architectural shell development to final documentation and plotting.

By integrating XREFs, dynamic blocks, attributes, automated data extraction, furniture planning, occupancy analysis, circulation planning, and professional drawing standards, the project provides a structured approach to developing and documenting a commercial office environment in AutoCAD.
