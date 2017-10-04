# TFT 2.2 ili9341

sources :
* http://marcosgildavid.blogspot.fr/2014/02/getting-ili9341-spi-screen-working-on.html
* https://www.youtube.com/watch?v=3vuK5w8o8dg

![schema](https://www.xgadget.de/wp-content/uploads/2016/10/SPI-Display-Schaltplan.jpg)

(from https://www.xgadget.de/anleitung/2-2-spi-display-ili9341-am-raspberry-betreiben/)

enable SPI
```
$ raspi-config
```

update raspberry pi firmware
```
$ rpi-update
```

install gpio & wiring pi

load module
```
$ modprobe fbtft_device custom name=fb_ili9341 gpios=reset:25,dc:24,led:18 speed=16000000 rotate=90 bgr=1
```

send console to framebuffer
```
$ con2fbmap 1 1
```

stop sending console 
```
$ con2fbmap 1 0
```
