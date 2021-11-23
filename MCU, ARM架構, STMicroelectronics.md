[[Terminology]]

---

簡稱 ST，常聽到的型號是 SMT32 開頭的，例如威潤就是用 STM32F103/303/L151，32 代表 暫存器 32bits，越高一次可以處理越多事情

STM32 同時也是 ARM架構 常會用到的晶片，ARM 有再細分很多種，cortex-xxx 之類的，威潤用的是 cortex-m4 架構 (除了 ARM架構以外，INTEL 可以說是另一種架構)

有些 MCU 在採購前就是根據是要用在哪個架構下去採購，STM32F103就比較初階是用在 cortex-M3

有了MCU以後，還要考慮要不要嵌入 FreeRTOS，FreeRTOS 勉強算是一種OS。並不是 MCU 一定要放 FreeRTOS，是比較需要多工用途的才要。多工指的是一個 TASK 還沒做完就要切去另一個 TASK，再切回來的概念。有的設計中雖然有MCU，但他的工作相對單純 (例如只讀CAN後回傳，那他就不需要多工，也就不需要嵌入 FreeRTOS)

MCU 身上會有很多腳位，根據不同的規格會有留不同的 PIN 腳給 RD 開發。之前常聽到的 GPS、GSM、BLE、SD Card…都會吃掉對應的一些腳位

常聽到的傳輸腳位有：
- SPI
- I2C
- UART
- GPIO
- SDIO
- CAN

例如 MCU 雖然自己身上也會有 FLASH，但有可能會再接外部的FLASH，就會吃到 SPI 腳位。SD卡是吃 SDIO 或是 SPI。UART 也是常聽到的腳位之一

GPIO 也是會接到 MCU 身上，只是 GPIO 算是比較基本的功能，例如要抓 UART 來處理 GPIO 也是可以，就是比較浪費，通常不會這樣設計

CPU 和 MCU 的差別是，MCU 已經包含 CPU 了，MCU 裡除了 CPU 還有 FLASH、RAM…依照上述所講的ARM架構而定，而 CPU 就只是 CPU

SOC 是 System On a Chip ，指的是除了 MCU 以外，其它的模組也一起被併進來成為一個晶片。舉例來說，以前的車機總是會有 GSM、GPS 模組，那就有可能有個 SOC 晶片是 MCU+GSM+GPS ，也因為這樣 MCU 有些腳位就會被吃掉，只剩不多，但開發的人變得比較輕鬆，可以直接在 MCU 上啟用他要的 GSM、GPS 功能

