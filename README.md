    #blink(第一个HAL_delay延时点灯)
板卡：STM32F103C8T6，HSE=8 MHz，系统时钟=72 MHz
接线：PA13/SWDIO，PA14/SWCLK，GND；单一3.3 V供电
LED：PC13，低电平点亮
打开：firmware/MDK-ARM/blink.uvprojx
构建：Keil Build，下载后复位
现象：LED亮250 ms、灭250 ms
    #rm_f103_blink（第二个非阻塞式点灯）
板卡：STM32F103C8T6，HSE=8 MHz，系统时钟=72 MHz
接线：PA13/SWDIO，PA14/SWCLK，GND；单一3.3 V供电
代码：使用TIM2计时器进行周期性中断，以此来控制LED灯的闪烁，采用非阻塞式方法。
LED：PC13，低电平点亮
打开：firmware/MDK-ARM/rm_f103_blink.uvprojx
构建：Keil Build，下载后复位
现象：LED亮250 ms、灭250 ms
    # rm_3(外部按键通过 EXTI 中断控制 LED 灯开关)
板卡：STM32F103C8T6，HSE=8 MHz，系统时钟=72 MHz
接线：PA13/SWDIO，PA14/SWCLK，GND；单一3.3 V供电
LED：PC13，低电平点亮
打开：firmware/MDK-ARM/rm_f103_blink.uvprojx
构建：Keil Build，下载后复位
说明：采用外部按钮的EXTI中断方式实现LED的点亮和熄灭，并且采用HAL_Delay进行消抖
现象：LED按下按钮后改变状态
