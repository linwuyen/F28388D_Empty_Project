# F28388D_Empty_Project

TI C2000 F28388D empty-project baseline for starting CPU1, CPU2, CM, and CLA firmware work.

## Repository Classification

- **Purpose:** public reusable F28388D project template.
- **Status:** baseline/template repository.
- **Scope:** build configuration, device initialization, SysConfig integration, and placeholder application structure.
- **Production status:** not production firmware and not an ASR5K source of truth.

## Specifications

- **MCU:** Texas Instruments C2000 F28388D
- **IDE:** Code Composer Studio v12 or newer
- **SDK:** TI C2000Ware / DriverLib
- **ABI:** EABI
- **Configuration:** TI SysConfig

## Build Configurations

- `CPU1_RAM` / `CPU2_RAM`: debug execution from RAM.
- `CPU1_FLASH` / `CPU2_FLASH`: standalone execution from on-chip Flash.

## Pin Mapping

This is an empty template. Pin assignments must be defined for the target board before hardware use.

| Pin Name | GPIO | Peripheral | Hardware Connection | Notes |
| --- | --- | --- | --- | --- |
| `PIN_X` | `GPIO_XX` | UART / SPI / PWM | TBD | Replace for the target board |

## Starting a New Project

1. Create a new repository from `F28388D_Empty_Project` or copy the project directory.
2. Rename the CCS projects for the target application.
3. Import them with `File > Import > C/C++ > CCS Projects`.
4. Verify the configured C2000Ware and compiler paths.
5. Update the `.syscfg` files for the target package, clocks, pins, and peripherals.
6. Implement application logic and validate both RAM and Flash builds.

## Working Rules

- Keep generated build output out of version control.
- Record required CCS, compiler, C2000Ware, and SysConfig versions.
- Do not use this template as evidence that a target board or application has passed hardware validation.
