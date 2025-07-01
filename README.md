# RISC-V-CPU
📌 專案簡介

本專案為一個簡易可運作的 RISC-V 處理器核心模擬器，使用 Verilog HDL 實作，支援多種 RISC-V 指令類型與模組化設計。專案涵蓋指令擴展模組（如 Type-M、CSR、例外中斷）、ISA 測試驗證與匯流排整合，並符合 SoC 設計中核心與外部組件協作的基本架構。此專案為 SoC 課程的期末專題成果。

🛠 使用技術

Verilog HDL

RISC-V RV32I 指令集 + 基本擴展（M、CSR）

模組化 CPU 架構（Core / IF / ID / EX / MEM / WB）

BUS 設計

Exception / Interrupt 控制邏輯

指令測試驗證（ISA test）

模擬工具（ModelSim / GTKWave）


📦 支援的指令類型

類型	          說明
I-type	        整數立即數指令（如 ADDI, LW）
R-type	        寄存器操作（如 ADD, SUB）
U/S/L-type	    上下位元組與記憶體存取指令
B/J-type	      分支與跳躍控制（如 BEQ, JAL）
M-type	        乘除法指令（如 MUL, DIV）
CSR-type	      控制狀態暫存器指令

🧠 模組化設計架構

Hart 模組：支援多核心（多執行緒）處理設計

Instruction Fetch（IF）：實作 PC 控制與指令讀取

Decode / Register File：指令解碼與暫存器讀取

Execute / ALU：算術邏輯單元，支援擴展運算

Memory Access：讀寫資料記憶體模組

BUS 系統：匯流排連接記憶體與週邊

CSR 與中斷控制：實作例外處理與狀態保存

🧪 測試驗證方式

使用 ISA 測試集 驗證指令功能正確性

每類型指令單獨模擬（I, R, B, J, M, CSR）

使用 waveform（GTKWave）觀察執行流程與暫存器變化

Exception/Interrupt 模組支援簡易例外流程模擬

💬 結果與討論

這次專案從設計每條 RISC-V 指令的處理流程開始，到模組間的資料流整合與中斷控制邏輯的實作，讓我更深入理解硬體執行單元的運作原理。也學會了如何從 top-down 架構設計、逐層模擬驗證，到與真實測試集對照來確認邏輯正確性。這對我未來想往嵌入式、SoC 或硬體加速器方向發展是一大助力。


實作程式碼連結：
https://drive.google.com/drive/folders/1j5zibXC7CNZuv3HX4JV-7GPS4c8y2O7z?usp=drive_link
