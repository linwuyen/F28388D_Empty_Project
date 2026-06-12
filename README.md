# 28388D_Empty Project Baseline

本專案為 TI C2000 F28388D 晶片的空專案範本，已配置好基本的編譯設定與開發基線，適用於快速啟動新的雙核（CPU1/CPU2）與 CM、CLA 的韌體開發專案。

## 專案規格 (Specifications)

- **MCU**: Texas Instruments C2000 F28388D (Delfino Dual-Core Microcontroller with CM)
- **CCS Version**: Code Composer Studio v12 或更新版本 (相容舊版 CCS v10+)
- **DriverLib**: TI C2000Ware SDK 內置驅動庫 (預設配置為 EABI 編譯)
- **SysConfig**: 支援 TI System Configuration Tool (引腳與硬體外設圖形化配置工具)

## 編譯配置 (Build Configuration)

本專案包含以下標準編譯配置：
1. **CPU1_RAM / CPU2_RAM**: 用於在 RAM 中快速執行與調試，重置後程式碼會消失。
2. **CPU1_FLASH / CPU2_FLASH**: 生產與實機部署版本，程式碼燒錄至片上 Flash 空間。

## 引腳對應表 (Pin Mapping Placeholder)

*目前為空範本，引腳分配尚未啟用，待後續子專案開發時依硬體線路定義填寫。*

| Pin Name | GPIO Num | Peripheral Function | Hardware Connection | Notes |
| --- | --- | --- | --- | --- |
| `PIN_X` | GPIO_XX | UART_RXD / SPI_SIMO | - | 待定義 |

## 如何作為新專案 Baseline (How to Use)

若要以此專案為基礎建立全新開發專案，請參考以下步驟：

1. **複製專案資料夾**：
   將 `28388D_Empty` 複製並重新命名為您的目標專案名稱。
2. **導入 CCS 整合開發環境**：
   - 開啟 Code Composer Studio。
   - 選擇 `File` -> `Import...` -> `C/C++` -> `CCS Projects`。
   - 瀏覽並選擇您複製的專案目錄導入。
3. **更換專案名稱與路徑**：
   - 在專案上按右鍵選擇 `Rename` 更改專案名稱。
   - 如有需要，可在 `Properties` -> `Resource` 中重新連結特定的 C2000Ware SDK 路徑。
4. **外設配置 (SysConfig)**：
   - 雙擊雙擊專案中的 `.syscfg` 檔案，開啟圖形配置介面來啟用如 SPI、I2C、PWM 等模組，系統會自動生成對應初始化程式碼。
5. **開始編寫代碼**：
   - 在 `main.c` 中實現您的應用邏輯。
