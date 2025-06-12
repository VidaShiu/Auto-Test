# Automated test framework (UART test)

This project is a modular, automated device test platform that supports users to enter device serial numbers, select test plans, and automatically complete all steps.

## Usage(Methods)

1. Run 'GUI.py', enter serial numbers and select test items

2. The program will automatically start testing according to the plans and commands defined in YAML

3. After the test is completed, test statistics and response records will be output

## File description

- 'library/*.yml': command data and test plan

- 'core/*.py': test main control logic and verification

- 'comm/*.py': UART serial communication processing

- 'gui/*.py': interface operation module

## Dependent modules

## System module architecture

1. GUI.py

用戶介面，輸入測試機序號、選擇測試項目

執行控制流程啟動

2. Process_Control_0212.py

核心主控邏輯

載入 test plan、逐項執行命令

驅動通訊與資料比對模組

3. Command_Line_0212.yml

定義各種可測試命令、預期回應與條件驗證

4. Test_Case.yml / Test_Plan_List.yml

定義測試組合，如 Smoke Test、Regression Test 等

每個測試計畫對應指令步驟清單

5. UART_communication_0211.py

串接 UART 傳送與接收封包

封裝 send/receive 基本操作

6. Serial_Port_Monitoring_0212.py

背景持續監聽 UART 接收資料

用於異步事件與延遲回應的支援

7. Conditional_0212.py

根據 command 設定條件驗證回應資料（格式、比對、範圍）

8. Statistic_0212.py

紀錄測試步驟、統計結果

可擴充輸出報表格式（CSV / TXT）
