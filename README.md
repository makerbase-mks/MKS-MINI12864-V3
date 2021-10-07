# MKS-MINI12864-V3
  Where to buy it: https://www.aliexpress.com/store/group/LCD/1047297_516922172.html?spm=a2g0o.store_pc_groupList.pcShopHead_8325768.1_2_1
  
  ## Brief introduction
  ![MINI12864](https://github.com/makerbase-mks/MKS-MINI12864-V3/blob/main/hardware/Image/MKS_MINI12864_V3.png)
  
  MKS MINI 12864 V3 Smart Display has RGB back light, support change back light color online by lcd, support Robin Nano V2 V3, sgen-l V1 V2, Gen-l. Both Marlin 2.x and Klipper firmware support it
  
  MKS MINI 12864 V3 是一款智能小巧，支持RGB调节背光颜色的显示屏，支持MKS主板以及市面上大多具有EXP1,EXP2的主板；并且Marlin2.0和Klipper固件都已经支持。
  
  The [sch and size](https://github.com/makerbase-mks/MKS-MINI12864-V3/tree/main/hardware/MKS%20MINI12864%20V3.0_001), refer to hardware path file
  
  ## Compare between MKS MINI12864 V3 and V1.x/V2.x
  | ITEMS      |  MKS MINI12864 V3  | MKS MINI12864 V1.x/V2.x |
  |------------|--------------------|-------------------------|
  | LCD Driver |   ST7567 | ST7565R |
  | RGB LED | Support(Driver: WS2811) | No support |
  | BackLights | RGB LED backlight | White LED |
  | Backlight adjustment | Online by LCD or M150 R* G* U* | No support |
  | Logic level | 3.3V or 5V | 3.3V or 5V |
  | Firmware settings | Enable: MKS_MINI_12864_V3 and NEOPIXEL_LED | Enable: MKS_MINI_12864 |
  | Text display | Black background, white text | White background, black text |
  
  
  ## Features
  - Support Marlin2.0 and Klipper firmware
  - Support LCD online adjustment of backlight
  - Support Gcode backlight setting, such as: M150 R100 G100 U100
  - Support color change in different states during printing
  - Compatible with 3.3V and 5V logic signals at the same time
  - SPI communication to host micro-controller
  - Use self-imposed SD card socket
  - Has vertical and side SD slot version
  
  ## PinOut
  ![pinout](https://github.com/makerbase-mks/MKS-MINI12864-V3/blob/main/hardware/Image/MKS_MINI12864_V3_PINOUT.png)
  ![EXP1 EXP2](https://github.com/makerbase-mks/MKS-MINI12864-V3/blob/main/hardware/Image/MKS_MINI12864_V3_EXP1_EXP2.png)
  
  ## Connect
  - Connect to MKS board by EXP1 and EXP2
  - Connect to other board by EXP1 and EXP1, but cable need Rotate 180°
  
  ## Firmware Config
  - Marlin2.0
    - in Configuration.h file
      - Enable: #define MKS_MINI_12864_V3
	  - Enable: #define NEOPIXEL_LED
	
  - Klipper firmware
    - The method 1: Copy **mks_mini_12864_v3.cfg config** to printer.cfg file
	- The method 2: Copy **mks_mini_12864_v3.cfg file** to same as path with printer.cfg, in printer.cfg add **[include mks_mini_12864_v3.cfg]**
  
  - Tips: If you use FYSTC Mini12864 or BTT mini12864 on MKS board, same method as MKS MINI12864 V3.
  
  ## Lights Settings
  - Malin2.0
    - Change color by lcd online: **Lights -> Light Presets**
    - Gcode set color: 
      - **M150 R255 G0 U0**  # Red
	  - **M150 R0 G255 U0**  # Green
	  - **M150 R0 G0 U255**  # Blue
	  - Other colors are set according to the value of R G U
	
  - Klipper
    - In **mks_mini_12864_v3.cfg** file, set the value of **initial_RED** , **initial_GREEN** , **initial_BLUE** 
  
  ## Other
  - [mks_mini_12864_v3.cfg](https://github.com/makerbase-mks/Klipper-for-MKS-Boards/blob/main/MKS%20Lcd%20Config/mks_mini_12864_v3.cfg)
  
  ## FAQ
  - About how to use the FYSETC Mini 12864 v2.1, BTT Mini 12864 v1.0 on Robin E3/E3D board. [Click here](https://github.com/makerbase-mks/MKS-Robin-E3-E3D/wiki/FYSETC_BTT_MINI12864)
