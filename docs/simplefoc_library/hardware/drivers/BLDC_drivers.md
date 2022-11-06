---
layout: default
title: 无刷直流电机驱动器
nav_order: 1
description: "Arduino Simple Field Oriented Control (FOC) library ."
permalink: /bldc_drivers
parent: 驱动板
grand_parent: 支持的硬件
grand_grand_parent: Arduino <span class="simple">Simple<span class="foc">FOC</span>library</span>
---

# 无刷直流电机驱动器

这个库将与大多数3相无刷直流电机驱动器兼容。如 [<i class="fa fa-file"></i> L6234](https://www.st.com/en/motor-drivers/l6234.html), [<i class="fa fa-file"></i> DRV8305](https://www.ti.com/product/DRV8305), [<i class="fa fa-file"></i> DRV8313](https://www.ti.com/product/DRV8313)  甚至 [<i class="fa fa-file"></i> L293](http://www.ti.com/lit/ds/symlink/l293.pdf). 

开发这款通用且简单的无刷直流驱动器<span>Simple<span>FOC</span>Shield</span>的动机之一，是因为目前低成本的无刷直流驱动板仍然很难找到，这使得我们对硬件的选择受到了很大的限制。不过好在各种开源社区已经开始在这个方向不断发展，无刷直流电机成为爱好社区的标准指日可待！😃

选择什么样的无刷直流驱动器，直接取决于你正在使用的无刷直流电机。对于无刷直流驱动器驱动器的选型，我们可以将其分为两组：

- [低功率无刷直流电机驱动器](#low-power-boards---gimbal-motors-) - 云台电机 (R>10Ω)
- [高性能无刷直流电机驱动器](#high-performance-boards) - 大功率无刷直流电机(R<1Ω)

# 低功率板（云台电机）

以下的一些无刷直流驱动板是为云台电机专门设计的。云台电机通常极对数大于10，内阻&gt;10Ω。它们在低速时具有非常稳定的性能。云台电机非常通用，能够高质完美的替代步进电机和直流伺服电机。

示例 | 描述 | 规格                                                         | 链接 | 价格 
---- | ---- | ---- | --- | --- 
[<img src="https://simplefoc.com/assets/img/v1.jpg" style="height:100px">](https://simplefoc.com/simplefoc_shield_product)| Arduino<br> <span class="simple">Simple<span class="foc">FOC</span>Shield</span> v1| - L6234 芯片 <br> - 8-24V <br> - up to 5 Amps <br> - 1 电机 <br>- Arduino Shield <br> - Encoder+I2C Pullups | [More info](https://simplefoc.com/simplefoc_shield_product) | 15€
[<img src="https://simplefoc.com/assets/img/v2.jpg" style="height:100px">](https://simplefoc.com/simplefoc_shield_product)| Arduino<br> <span class="simple">Simple<span class="foc">FOC</span>Shield</span> v2| - L6234 芯片 <br> - 8-24V <br> - up to 5 Amps <br> - 1 电机 <br>- Arduino Shield <br> - Encoder+I2C Pullups <br> - 在线电流检测 <br> - 板载电压调节器 | [SimpleFOC store](https://simplefoc.com/simplefoc_shield_product_v2) <br> [Aliexpress](https://fr.aliexpress.com/item/1005002496275228.html?spm=a2g0o.productlist.0.0.51b44925t9nr53&algo_pvid=42a7dd52-305b-4cb0-af17-60a892aaad3a&algo_exp_id=42a7dd52-305b-4cb0-af17-60a892aaad3a-0&pdp_ext_f=%7B%22sku_id%22%3A%2212000020877377792%22%7D#feedback) <br> [Ebay](https://www.ebay.com/itm/165027599242?hash=item266c69538a:g:bZIAAOSw8QJg9mvD)| ~20€
[<img src="extras/Images/mini.png" style="height:100px">](https://github.com/simplefoc/SimpleFOCMini) | <span class="simple">Simple<span class="foc">FOC</span>Mini</span> v1 | - DRV8313 芯片<br> - 8-30V <br> - up to 2.5 Amps <br> - 3.3V LDO onboard <br> - 1 电机 <br> - 21x26mm | [SimpleFOC store](https://simplefoc.com/shop)<br><i>（即将上架）</i> | 5-7€
[<img src="extras/Images/l6234.jpg" style="height:100px">](https://www.ebay.com/itm/L6234-Breakout-Board/153204519965?hash=item23abb3741d:g:LE4AAOSwe35bctgg) | Drotek L6234<br> breakout board | - L6234 芯片 <br> - 1 电机 <br> - 25x25mm | [Drotek](https://store-drotek.com/212-brushless-gimbal-controller-l6234.html)<br> [Ebay](https://www.ebay.fr/itm/L6234-Breakout-Board-/153204519965) | 30€
[<img src="extras/Images/dual_simplefoc.jpg" style="height:100px">](https://github.com/ToanTech/Deng-s-foc-controller) | Deng FOC controller<br> breakout board | - L6234 芯片 <br> - 8-24V <br> - up to 5 Amps <br> - 2 电机 <br> - 39x56mm | [Aliexpress](https://store-drotek.com/212-brushless-gimbal-controller-l6234.html)<br> [Ebay](https://www.ebay.com/itm/373690016017?hash=item5701a92111:g:YkYAAOSwF8ZhHgi3) | 35-50€

或者，你也可以找到集成无刷直流驱动器和单片机的云台电机控制板。

| 示例                                                         | 描述        | 规格                                                        | 链接                                                         | 价格 |
| ------------------------------------------------------------ | ----------- | ----------------------------------------------------------- | ------------------------------------------------------------ | ---- |
| [<img src="extras/Images/pinout.jpg" style="height:100px">](https://www.ebay.com/itm/HMBGC-V2-0-3-Axle-Gimbal-Controller-Control-Plate-Board-Module-with-Sensor/351497840990?hash=item51d6e7695e:g:BAsAAOSw0QFXBxrZ:rk:1:pf:1) | HMBGC V2.2  | - 4599 mosfet<br> - 2 电机  <br> - 50x30mm <br> - Atmega328 | [Ebay](https://www.ebay.com/itm/HMBGC-V2-0-3-Axle-Gimbal-Controller-Control-Plate-Board-Module-with-Sensor/351497840990?hash=item51d6e7695e:g:BAsAAOSw0QFXBxrZ:rk:1:pf:1) | 20€  |
| [<img src="extras/Images/bgc_30.jpg" style="height:100px">](https://fr.aliexpress.com/item/4000411471994.html?spm=a2g0o.productlist.0.0.5d047d57y4zGC4&algo_pvid=861ada4b-b12f-4019-be84-fae9870a12ed&algo_expid=861ada4b-b12f-4019-be84-fae9870a12ed-1&btsid=0ab6f83a15906954691168349e30d7&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_) | BGC 3.0     | - 4599 mosfet<br> - 2 电机  <br> - 50x50mm <br> - Atmega328 | [Aliexpress](https://fr.aliexpress.com/item/4000411471994.html?spm=a2g0o.productlist.0.0.5d047d57y4zGC4&algo_pvid=861ada4b-b12f-4019-be84-fae9870a12ed&algo_expid=861ada4b-b12f-4019-be84-fae9870a12ed-1&btsid=0ab6f83a15906954691168349e30d7&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_) | 10€  |
| [<img src="extras/Images/bgc31.jpg" style="height:100px">](https://www.ebay.com/itm/BGC-3-1-MOS-Large-Current-Two-Axis-Brushless-Gimbal-Controller-Driver-Alexmos/302692769869?hash=item4679e5204d:g:m9AAAOSweHtdzM8o) | BGC 3.1     | - l6234<br> - 2 电机  <br> - 50x50mm <br> - Atmega328       | [Ebay](https://www.ebay.com/itm/BGC-3-1-MOS-Large-Current-Two-Axis-Brushless-Gimbal-Controller-Driver-Alexmos/302692769869?hash=item4679e5204d:g:m9AAAOSweHtdzM8o) | 10€  |
| [<img src="extras/Images/strom.jpg" style="height:100px">](https://www.ebay.com/itm/Storm32-BGC-32Bit-3-Axis-Brushless-Gimbal-Controller-V1-32-DRV8313-Motor-Driver/174343022855?hash=item2897a76907:g:20YAAOSwbEhfBo28) | Storm32 BGC | - DRV8313 <br> - 3 电机  <br> - 50x50mm <br> - Stm32f103    | [Ebay](https://www.ebay.com/itm/Storm32-BGC-32Bit-3-Axis-Brushless-Gimbal-Controller-V1-32-DRV8313-Motor-Driver/174343022855?hash=item2897a76907:g:20YAAOSwbEhfBo28) | 25€  |

最后，运行云台电机最便宜的解决方案之一是使用双直流电机驱动器，如:

| 示例                                                         | 描述                 | 规格                                                         | 链接                                                         | 价格 |
| ------------------------------------------------------------ | -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---- |
| [<img src="extras/Images/l298n.jpg" style="height:100px">](https://www.ebay.com/itm/L298N-DC-Stepper-Motor-Driver-Module-Dual-H-Bridge-Control-Board-for-Arduino/362863436137?hash=item547c58a169:g:gkYAAOSwe6FaJ5Df) | Stepper driver L298N | - L298N  芯片<br> - 1 电机 <br>- 5V-35V <br> - 2A(MAX single bridge) | [Ebay](https://www.ebay.com/itm/L298N-DC-Stepper-Motor-Driver-Module-Dual-H-Bridge-Control-Board-for-Arduino/362863436137?hash=item547c58a169:g:gkYAAOSwe6FaJ5Df) | 2€   |
<blockquote class="warning">
<p class="heading">L298N 的局限性</p>
L298N 基于双极晶体管技术，具有较长的晶体管上升时间，会使得电机无法平稳运行。
我们建议仅在闭环模式下使用基于L298N的电路板，因为位置传感器能够减少由驱动器带来的噪音。
此外，虽有一定性能限制，但作为熟悉大电流 FOC 的廉价方案，它也可以是初学者不错的选择。
</blockquote>




## 高性能驱动板
<span>Simple<span>FOC</span>library</span>基本支持任何可以使用3路PWM或6路PWM信号控制的无刷直流电机驱动器。到目前为止([version 1.3.1](https://github.com/simplefoc/Arduino-FOC/releases))，库还没有实现电流控制环。电机力矩通过电压直接控制([更多信息](voltage_torque_control))

以下是经测试，与library库兼容的驱动板：

示例|描述|规格|链接|价格
---- | ---- | ---- | --- | --- 
[<img src="extras/Images/drv8302.png" style="height:100px">](https://fr.aliexpress.com/item/4000126430773.html?spm=a2g0o.productlist.0.0.702a312aXmzuUK&algo_pvid=50131a88-ac88-4755-bb71-978c07ec461e&algo_expid=50131a88-ac88-4755-bb71-978c07ec461e-5&btsid=0b0a119a15957548552557385e6f5e&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_)| DRV8302 driver | - DRV8302 芯片 <br> - 1 电机 <br>- 45V/27A <br> - BEMF/电流检测  <br> - 失效保护 | [Aliexpress](https://fr.aliexpress.com/item/4000126430773.html?spm=a2g0o.productlist.0.0.702a312aXmzuUK&algo_pvid=50131a88-ac88-4755-bb71-978c07ec461e&algo_expid=50131a88-ac88-4755-bb71-978c07ec461e-5&btsid=0b0a119a15957548552557385e6f5e&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_) | 30€
[<img src="extras/Images/drv8301.png" style="height:100px">](https://fr.aliexpress.com/item/4000203180955.html?spm=a2g0o.productlist.0.0.39871962xgolNI&algo_pvid=a86f85ad-3d0b-46cd-a05a-cb7c89e92c9e&algo_expid=a86f85ad-3d0b-46cd-a05a-cb7c89e92c9e-4&btsid=0b0a01f815957554085321097e9fdf&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_)| DRV8301 driver | - DRV8301 芯片<br> - 1 电机 <br>- 45V/27A <br> - BEMF/电流检测  <br> - 失效检测 <br> - SPI 配置 | [Aliexpress](https://fr.aliexpress.com/item/4000203180955.html?spm=a2g0o.productlist.0.0.39871962xgolNI&algo_pvid=a86f85ad-3d0b-46cd-a05a-cb7c89e92c9e&algo_expid=a86f85ad-3d0b-46cd-a05a-cb7c89e92c9e-4&btsid=0b0a01f815957554085321097e9fdf&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_) | 45€
[<img src="extras/Images/B-G431B-ESC1_SPL.jpg" style="height:100px">](https://www.st.com/en/evaluation-tools/b-g431b-esc1.html)| B-G431B-ESC1 | - STM32G431CB 芯片 <br> - On-board ST-LINK/V2-1 <br> - 1 电机 <br>- 30V/40A <br> - 低压侧电流检测<br> - 失效保护 | [STM webiste](https://www.st.com/en/evaluation-tools/b-g431b-esc1.html) <br> [Mouser](https://eu.mouser.com/ProductDetail/STMicroelectronics/B-G431B-ESC1/?qs=%2Fha2pyFaduj9HtQf9%2FgsBmvGqEl7EbEPOyTxg06xIidkuUIykXhpkA%3D%3D) | 16€
[<img src="extras/Images/SHIELD_IFX007T.jpg" style="height:100px">](https://www.infineon.com/cms/en/product/evaluation-boards/bldc-shield_ifx007t/)| Infineon <br> BLDC-SHIELD_IFX007T shield | -  IFX007T 半桥<br> - 1 电机 <br>- 40V/30A <br> - BEMF/低压侧电流检测 <br> - 失效保护 | [Infineon](https://www.infineon.com/cms/en/product/evaluation-boards/bldc-shield_ifx007t/) | 40€
[<img src="https://simplefoc.com/assets/img/dagor/Dagor_iso.png" style="height:120px">](https://github.com/byDagor/Dagor-Brushless-Controller)| [@byDagor](https://github.com/byDagor) <br> Dagor Brushless Controller | -  DRV8305 驱动器 <br> - 1 电机 <br>- 25V/40A <br> - 电流检测  <br> - 集成传感器<br> - 基于Esp32 <br> - 失效保护 | [simplefoc shop](https://simplefoc.com/shop)<br> <i>alpha batch sold out</i> | 40€
[<img src="extras/Images/powershield.jpg" style="height:120px">](https://github.com/simplefoc/Arduino-SimpleFOC-PowerShield)| Arduino<br> <span class="simple">Simple<span class="foc">FOC</span><span class="power">Power</span>Shield</span> | -  BTN8982 半桥 <br> - 1 电机 <br>- 40V/30A<br> - 失效保护 <br> <b>Release v1:</b> <br> - 在线电流检测  <br> - I2C/Hall/Encoder pullups*<br> - 2x Stackable* |  [fabricate](https://github.com/simplefoc/Arduino-SimpleFOC-PowerShield)  | ~20€
[<img src="extras/Images/high_perf_new.png" style="height:100px">](https://github.com/ChenDMLSY/FOC-SimpleFOC-MotorDriveDevelopmentBoard)| FOC-SimpleFOC-MotorDriveDevelopmentBoard | - IR2103 驱动器<br> - 1 电机 <br>- 36V/20A <br> - 低侧电流检测 | [Aliexpress](https://fr.aliexpress.com/item/1005002852603523.html?spm=a2g0o.productlist.0.0.76861dc3dEgETJ&algo_pvid=48101b3f-ba22-40b0-b6de-421d79a675b8&algo_exp_id=48101b3f-ba22-40b0-b6de-421d79a675b8-2&pdp_ext_f=%7B%22sku_id%22%3A%2212000022467783080%22%7D) [Ebay](https://www.ebay.com/itm/373689972247?hash=item5701a87617:g:i0IAAOSwrKlhHf~r) | 30€
[<img src="extras/Images/odrive.jpg" style="height:100px">](https://odriverobotics.com/shop/odrive-v36)| ODRIVE V3.6 | - STlink programmer needed <br> - 2 电机 <br>- 12-48V <br> - 60A (峰值120A) <br> - 低侧电流检测 | [Aliexpress](https://www.aliexpress.com/item/1005002349959313.html?spm=a2g0o.productlist.0.0.6248381eOCYTRO&algo_pvid=30554e7d-0b77-44fc-a790-e35040ce3de9&algo_exp_id=30554e7d-0b77-44fc-a790-e35040ce3de9-0&pdp_ext_f=%7B%22sku_id%22%3A%2212000020231141543%22%7D) <br> [ODive shop](https://odriverobotics.com/shop) | 70-100€ <br> 200€

<blockquote class="warning">
<p class="heading">IFX007T and BTN8982 芯片局限性</p>
IFX007T 和 BTN8982 基于较老的晶体管技术，具有较长的晶体管上升时间，会使得电机无法平稳运行。
我们建议仅在闭环模式下使用基于这些芯片的电路板，因为位置传感器能够减少由驱动器带来的噪音。
此外，虽有一定性能限制，但作为熟悉大电流 FOC 的廉价方案，它也可以是初学者不错的选择。
</blockquote>

