# Curie Open Development Kit - M

### Contents

  - x86: Zephyr
  - ARC: Arduino sketches or `*.cpp`

### Supported Platforms
 - Ubuntu 14.04 - 64 bit

### Installation
```
mkdir -p ~/CODK && cd $_
git clone https://github.com/01org/CODK-M.git
cd CODK-M
make clone
sudo make install-dep
make setup
source ../zephyr/zephyr-env.sh
```

### Compile
- x86: `make compile-x86`
- ARC: `make compile-arc`
- Both: `make compile`

### Upload

##### Using USB/DFU
- x86: `make upload-x86-dfu`
- ARC: `make upload-arc-dfu`
- Both: `make upload`

##### Using JTAG
- x86: `make upload-x86-jtag`
- ARC: `make upload-arc-jtag`
- Both: `make upload-jtag`

Default app blinks the pin-13 LED on Arduino 101 board

### Debug
Connect JTAG and open three terminal tabs

##### Tab 1: Debug Server
`make debug-server`

##### Tab 2: Firmware
`make debug-x86`    
`(gdb) target remote localhost:3334`

##### Tab 3: Software
`make debug-arc`    
`(gdb) target remote localhost:3333`
