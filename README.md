# F28388D_Empty_Project

可重複使用的 TI C2000 F28388D empty-project baseline。

這個 repo 是給新的 F28388D CPU1 / CPU2 / CM / CLA firmware work 使用的乾淨起始點。它是 template-style project，不代表任何 target board 或 application 已通過 hardware validation。

## 1. Repository 角色

- **用途：** public reusable F28388D project template。
- **狀態：** baseline / template repository。
- **可見性：** public。
- **範圍：** build configuration、device initialization、SysConfig integration、placeholder application structure。
- **正式產品狀態：** 不是 production firmware，也不是 ASR5K source of truth。

## 2. Target platform

- **MCU：** Texas Instruments C2000 F28388D
- **IDE：** Code Composer Studio v12 或更新版本
- **SDK：** TI C2000Ware / DriverLib
- **ABI：** EABI
- **Configuration：** TI SysConfig

## 3. Intended use

需要下列用途時，可使用此 repo：

- clean CCS import baseline
- new F28388D firmware starting point
- 加入 board-specific peripherals 前的 minimal structure
- 建立 application-specific repository 前的 reference project

不要把它當成：

- 已驗證的 hardware board support package
- production firmware release
- project-specific bring-up repository 的替代品
- target board pinout 正確性的證明

## 4. Build configurations

常見 configuration：

- `CPU1_RAM` / `CPU2_RAM`：從 RAM debug execution。
- `CPU1_FLASH` / `CPU2_FLASH`：從 on-chip Flash standalone execution。

實際 configuration names 可能依 imported CCS project settings 而不同。

## 5. Pin mapping

這是 empty template。實際硬體使用前，必須依 target board 定義 pin assignments。

| Pin Name | GPIO | Peripheral | Hardware Connection | Notes |
| --- | --- | --- | --- | --- |
| `PIN_X` | `GPIO_XX` | UART / SPI / PWM | TBD | Replace for the target board |

## 6. Starting a new project

1. 從 `F28388D_Empty_Project` 建立新 repository，或複製 project directory。
2. 依 target application 重新命名 CCS projects。
3. 使用 `File > Import > C/C++ > CCS Projects` 匯入。
4. 確認 C2000Ware 與 compiler paths。
5. 更新 `.syscfg` files：package、clocks、pins、peripherals。
6. 實作 application logic。
7. 驗證 RAM 與 Flash builds。
8. hardware testing 前，記錄 board、wiring、toolchain versions。

## 7. Working rules

1. generated build output 不進 version control。
2. 記錄所需 CCS、compiler、C2000Ware、SysConfig versions。
3. board-specific 資料應先整理並確認用途後再加入。
4. 未完成 target board testing 前，不要宣稱 hardware validation。
5. 當 application work 已超過 template 範圍，應 promotion 到 dedicated project repository。
