---
marp: true
theme: gaia
class: invert
paginate: true
style: |
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
header: "*Introduction to Raspberry Pi* :pie:"
---
<!-- _header: "" -->
# Introduction to Raspberry Pi :pie:

By: Hedron Hackerspace

![](https://www.arm.com/-/media/global/Why%20Arm/partner/Partner%20Ecosystem/catalog/raspberry-pi/rasberry-pi-logo.png?rev=d8bda285533b4dbf9690d02a764dbf10&revision=d8bda285-533b-4dbf-9690-d02a764dbf10)
<!-- _footer: "Rev. 1.0" -->
---

# What is a Single Board Computer (SBC)?

**Technical definition:**
*A computer that is entirely contained on one single PCB*

**Common characteristics:**

* ARM or RISC-V SoC (can contain x86)
* Broken out GPIO header pins (26-pin or 40-pin is standard)
* Runs some distribution of Linux (ie. Debian, Ubuntu, etc.)

---
<!-- _footer: "Touchscreen device, overclocking, ..." -->
# What are SBC's typically used for?

**Short answer:** Pretty much anything

<div class=columns>
<div>

* Home computing
* Software development
* Retro gaming
* Server host
* Security

</div>
<div>

* Homelabs/NAS
* Robotics
* Edge AI/ML
* 3D printer manager
* Home automation

</div>
</div>

***And much, much more...***

---

# Why the Raspberry Pi?

* Community and support
* Documentation
* Open source
* Efficient (<10W when stress tested)
* Cheap hardware*

![bg right w:600](hero.webp)

<!-- _footer: "* - Cheap when in stock" -->
---

# Who is the Raspberry Pi Foundation?

* UK based company, only 1 official Pi store in the Netherlands
* Named 'Raspberry Pi' in congruence with other fruit based companies
* "Computing for everyone"
* Specialize in low cost, educational computers
* Became *the* company for Linux/ARM SBCs
* Make SBCs, MCUs, and accessories (and magazine)
* Most recent Raspberry Pi 5 started preorders this October

---

# Raspberry Pi 4 Model B Specs

* CPU: BCM2711
  * 4x Cortex-A72 cores @ 1.5GHz
* GPU: VideoCore VI
  * 500MHz base <!-- , 700MHz OC -->
  <!-- * H264/H265, OpenGL ES 3.1, Vulkan 1.0 -->
* RAM: 1GB, 2GB, 4GB, 8GB
  <!-- * LPDDR4-3200 -->
* 40-pin GPIO header
* 2-lane MIPI CSI/DSI ports

![bg right w:600](https://assets.raspberrypi.com/static/raspberry-pi-4-labelled-f5e5dcdf6a34223235f83261fa42d1e8.png)

---

# Raspberry Pi 5 Specs

* CPU: BCM2712
  * 4x Cortex-A76 cores @ 2.4GHz
  * Cryptography extensions
* GPU: VideoCore VII
  * 800MHz base <!-- , 1GHz OC -->
  <!-- * H264/H265, OpenGL ES 3.1, Vulkan 1.2 -->
* RAM: 4GB and 8GB
  <!-- * LPDDR4X-4267 -->
* A **TON** of other peripherals

![bg right w:600](https://assets.raspberrypi.com/static/c671804c05a51efc4e3c2a1bdcbafbcf/e58b5/raspberry-pi-5.png)

---

# Raspberry Pi Zero W Specs

* CPU: BCM2835 (32-bit)
  * 1x ARM11 core @ 1GHz
* GPU: VideoCore IV
  * 250MHz base <!-- , 400MHz OC -->
  <!-- * OpenGL ES 2.0 -->
* RAM: 512MB
* 40-pin GPIO header
* WiFi 2.4/5GHz, BT 4.1/BLE
* MIPI CSI camera connector

![bg right w:600](https://images.prismic.io/rpf-products/9371b539-77d4-47f1-b89b-aa65b23c9833_RPI+ZERO+W+ANGLE+2+REFRESH_.jpg?auto=compress%2Cformat&fit=max)

---

# Raspberry Pi Zero 2W Specs

* CPU: RP3A0-AU
  * 4x Cortex-A53 cores @ 1GHz
  <!-- * H264, MPEG-4 -->
* GPU: VideoCore IV
* RAM: 512MB (unfortunately)
* WiFi 2.4GHz, BT 4.2/BLE
* MIPI CSI camera connector

![bg right w:600](zero2-close-up.webp)

---

# Why is the Pi Pico/W not listed?

* Pico is a microcontroller board
  * Fundamentally different
  * Does not run Linux (or any kind OS)
  * Runs single Python or C++ programs
* Learn more in the upcoming Arduino/Microcontroller classes
  * Hosted by yours truly

---

# Other SBC Brands and Vendors

<div class=columns>
<div>

#### <u>SBC Brands:</u>

* Orange/Mango/Banana Pi
* BeagleBone
* Nvidia
* Coral
* Asus
* Khadas
* FriendlyElec
* Milk-V

</div>
<div>

#### <u>Vendors:</u>

* Adafruit
* SparkFun
* PiShop.us
* PiHut
* Pimironi
* Chicago Elecronics
* CanaKit
* Vilros

</div>
</div>

---

# What is Linux :penguin:?

* Free and open source OS
* Supports many different ISAs (instruction set architectures)
  * x86
  * ARM
  * RISC-V
* Very different from Windows
  * Terminal is almost a necessity
  * Much less application compatibility
  * Significantly less bloat/background activity

---

# Time to setup the Pi

**You will need:**

1. Your Pi of choice (>3B or Zero W)
2. MicroSD card and adapter (recommended >=32GB)
3. Power adapter for your Pi (5-25W)
4. Computer or laptop with Pi Imager installed

* GUI setup: Monitor, keyboard, and mouse
* Headless setup: Ethernet or USB data cable to computer
<!-- _footer: "Continue to next section: **1_Basic_Setup**" -->
