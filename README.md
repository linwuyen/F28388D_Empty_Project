# F28388D_Empty_Project

Public reusable TI C2000 F28388D empty-project baseline.

This repository is intended as a clean starting point for new F28388D CPU1 / CPU2 / CM / CLA firmware work. It is a template-style project, not evidence that any target board or application has passed hardware validation.

## Repository Role

- **Purpose:** public reusable F28388D project template.
- **Status:** baseline/template repository.
- **Visibility:** public.
- **Scope:** build configuration, device initialization, SysConfig integration, and placeholder application structure.
- **Production status:** not production firmware and not an ASR5K source of truth.

## Target Platform

- **MCU:** Texas Instruments C2000 F28388D
- **IDE:** Code Composer Studio v12 or newer
- **SDK:** TI C2000Ware / DriverLib
- **ABI:** EABI
- **Configuration:** TI SysConfig

## Intended Use

Use this repository when you need:

- a clean CCS import baseline
- a new F28388D firmware starting point
- a minimal structure before adding board-specific peripherals
- a reference project before creating application-specific repositories

Do not use it as:

- a validated hardware board support package
- a production firmware release
- a replacement for a project-specific bring-up repository
- proof that any target board pinout is correct

## Build Configurations

Typical configurations:

- `CPU1_RAM` / `CPU2_RAM`: debug execution from RAM.
- `CPU1_FLASH` / `CPU2_FLASH`: standalone execution from on-chip Flash.

Actual configuration names may depend on the imported CCS project settings.

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
6. Implement application logic.
7. Validate both RAM and Flash builds.
8. Record the board, wiring, and toolchain versions before hardware testing.

## Working Rules

1. Keep generated build output out of version control.
2. Record required CCS, compiler, C2000Ware, and SysConfig versions.
3. Do not commit board-specific secrets, credentials, or private hardware documents.
4. Do not claim hardware validation until the target board has been tested.
5. Promote application work into a dedicated project repository when it becomes more than a template.
