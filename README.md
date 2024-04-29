# library-horizon-pool

This repository contains the Horizon pool used in our PCB designs.

## Description

The pool serves as a centralized database to manage electronic design components in a systematic and organized manner.

## Pool Structure

Components are stored in individual JSON files within specific directories (e.g., `/symbols`, `/entities`, `/units`, `/parts`), adhering to Horizon EDA's system:

- **Entities**: Represent the netlist aspect of parts, composed of units defining logical pins.
- **Packages**: Detail the physical footprint on PCBs, including pad shapes and layers specified by padstacks.
- **Symbols**: Used in schematics, visually representative of entities or units.
- **Padstacks**: Configure physical pad details in packages, covering dimensions and layers such as solder mask and paste.
- **Parts**: Linked to entities and packages, capable of inheriting properties to reduce redundancy.


## Getting Started

The pool is provided ready to use, all that is required is to clone it and add it to Horizon's managed pools:



## Contributing

Contributions to pool are welcome! Please be aware of these points:
- Packages are required to have a 3D model, if the model doesn't exist in the pool please consider contributing to our [3D model archive](https://github.com/ygn-effects/library-eda-3d-models). We won't accept randomly sourced models to avoid licensing issues.
- Always try to use existing primitives (entities/units) if possible.
- Use the following naming conventions:
    - kebab-case should be used for filenames.
    - Parts filenames should be the part's MPN.
    - Packages filenames should adhere to the following conventions:

`<footprint-type>-<category>-<component>-<specifics>-<...>`

- Where:
    - **footprint-type** can be either:
        - **th**: for through-hole components.
        - **smd**: for surface-mounted devices.
    - **category**: typically the component's family (resistor, ic, switch...).
    - **specifics**: this is optional and depends on the modeled part's package type:
        - **generic package**: any noteworthy detail that allows to quickly identify the correct model. Specifics can contain multiple sections (see the example below).
        - **specific model**: use the MPN of illustrated part.


To contribute a component:

1. Open an issue using the Component request template.
    - Fill in the issue and include a screenshot of any reference used to create the package or symbol.
2. Fork the repository.
3. Create a new branch for your contribution.
4. Add your files following the existing structure and naming conventions.
5. Submit a pull request with a clear description of your additions.

## Issue Template

[Here, you would link to your issue template or describe how to use it.]

## Naming Conventions

[Here, you would outline any specific naming conventions for the units, symbols, entities, and packages.]

## License

This project is open source and available under the [license name]. Please see the LICENSE.md file for full details.
