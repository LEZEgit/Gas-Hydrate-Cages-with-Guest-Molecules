## Overview

This repository contains the code and assets developed for the **Schematic Assignment for PEE201 course**, focusing on schematic generation and molecular modeling related to gas hydrate structures and biosurfactant mechanisms.

The project includes:

* Editable diagrams of gas hydrate cage structures
* Guest molecule placement inside various hydrate structures (sI, sII, sIII)
* Surfactant and biosurfactant schematic components
* Utility scripts and files supporting the generation and modification of these schematics

## Features

### Hydrate Structure Modeling

* CH₄ molecules placed in **sI (structure I)** cages
* CO₂ molecules placed in **sI** cages
* C₂H₆ molecules placed in **sII (structure II)** cages (under progress)
* C₃H₈ molecules placed in **sII** cages (under progress)
* Mixed **Methane + Neohexane** molecules placed in **sIII (structure III)** cages (under progress)

***

### Genice2 Command Reference

The `.cif` files for the hydrate structures are generated using the `genice2` command-line utility. The structure codes used in this project are:

| Structure Type | Code (genice2) |
| :--- | :--- |
| Structure I (sI) | CS1 |
| Structure II (sII) | CS2 |
| Structure III (sIII) | sIII (or RHO) |

#### 1. Generating Empty Structures (Framework Only)

This generates the pure water lattice without any guest molecules.

##### General Syntax:
```bash
genice2 [STRUCTURE_CODE] --format cif > [FILENAME].cif
```
##### Example: Empty sIII structure
```bash
genice2 CS3 --format cif > sIII_empty.cif
````

#### 2\. Generating Structures with a Single Guest Atom

This command fills all available cages with the specified guest molecule (e.g., $\text{CH}_4$).

##### General Syntax:
```bash
genice2 [STRUCTURE_CODE] [GUEST_MOLECULE] --format cif > [FILENAME].cif
```
##### Example: Methane-filled sI structure
```bash
genice2 CS1 CH4 --format cif > sI_CH4_filled.cif
```

#### 3\. Generating a Supercell (Larger Lattice Size)

Use the `-r` or `--rep` option to generate a supercell, which is a repeated block of the unit cell along the X, Y, and Z dimensions. This is useful for simulations.

##### General Syntax:
```bash
genice2 [STRUCTURE_CODE] [GUEST_MOLECULE] -r [FACTOR] [FACTOR] [FACTOR] --format cif > [FILENAME].cif
```
##### Example: 2x2x2 Methane-filled sII supercell
```bash
genice2 CS2 CH4 -r 2 2 2 --format cif > sII_CH4_2x2x2.cif
```

**(Note: For mixed guests, manual editing of the resulting CIF file, as described in project documentation, is required.)**

-----

## How to Use

1.  Clone the repository:
    ##### Copy the command below and paste it in your terminal
    ```bash
    git clone [https://github.com/LEZEgit/Gas-Hydrate-Cages-with-Guest-Molecules/](https://github.com/LEZEgit/Gas-Hydrate-Cages-with-Guest-Molecules/)
    ```

3.  Navigate into the project directory and open the required scripts or diagrams.
4.  Open Avogadro software and click on "OPEN" button.
5.  Select the required .cif file from the cloned directory.
6.  Click "Open" or "OK".
7.  The model will be rendered in the app.
8.  You can now use the app to enable bond preview or modify the view of atoms, change color per atom or anything supported by Avogadro.

9.  Editable diagrams can be opened in:

      * **draw.io**
      * **Figma**
      * **Illustrator**
      * or any compatible vector editor.

10.  Scripts can be executed or modified based on your environment setup.

## Requirements

Depending on what you’re generating:

  * Avogadro (for rendering the .cif files)
  * Python (if using structure-generation scripts)

## References

The conceptual background and references for hydrate structures and biosurfactant mechanisms were based on the material from:

  * MDPI Fire Journal, Article 7(7), p.240
  * Additional hydrate and surfactant literature as provided in the assignment

## License

This project is part of an academic assignment. Use and modify freely unless your instructor has stricter rules.


