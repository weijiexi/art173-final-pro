# Project - RGB Matrix 
  <p align="center" ><a href="https://www.youtube.com/watch?v=lxISwvN1Cic" >
  <img src="https://ucb-courses-materials.s3.us-east-2.amazonaws.com/images/art173_final+_peoject_img.png" width="400" height="280" style="width: 400px; height: 280px;">
  </a></p> 
## Controlling RGB LED display with Raspberry Pi GPIO

A demo to use a 32x32 RGB LED panels with the Raspberry Pi.

The LED-matrix library is (c) Henner Zeller [h.zeller@acm.org](h.zeller@acm.org), licensed with GNU General Public License Version 2.0 (which means, if you use it in a product somewhere, you need to make the source and all your modifications available to the receiver of such product so that they have the freedom to adapt and improve).

The RGBMatrix class provided in `include/led-matrix.h` does what is needed to control these. You can use this as a library in your own projects or just use the demo binary provided here which provides some useful examples.

## Let's do it

This documentation is split into parts that help you through the process

If you have an Adafruit HAT or Adafruit Bonnet, you can choose that with a command line option described below
Run a demo. You find that in the examples-api-use/ directory:

The following is a demo to use [adafruit Bonnet](https://learn.adafruit.com/adafruit-rgb-matrix-bonnet-for-raspberry-pi/overview) with a 32x32 RGB LED panels with the Raspberry Pi.

**1. building `led-image-viewer` and `video-viewer` run `demo examples`**

```bash
curl https://raw.githubusercontent.com/adafruit/Raspberry-Pi-Installer-Scripts/main/rgb-matrix.sh >rgb-matrix.sh
sudo bash rgb-matrix.sh
```

-   **Building `led-image-viewer`**

```bash
sudo apt-get update
sudo apt-get install pkg-config libavcodec-dev libavformat-dev libswscale-dev
make video-viewer
```

-   **Building `video-viewer`**

```bash
sudo apt-get update
sudo apt-get install libgraphicsmagick++-dev libwebp-dev -y
make led-image-viewer
```

**2.  view images and videos**


```bash
cd ~/rpi-rgb-led-matrix/utils/
```

-   **view images**

```bash
sudo ./led-image-viewer --led-no-hardware-pulse --led-gpio-mapping="adafruit-hat" -f -w3  *.jpg 
```

-   **view videos**

```bash
sudo ./video-viewer --led-no-hardware-pulse --led-gpio-mapping="adafruit-hat" -f 1.mp4
```

-   **demo examples**

```bash
cd ~/rpi-rgb-led-matrix/examples-api-use/
```


```bash
sudo ./demo  --led-rows=32 --led-cols=32 -D6
```
## Ref:  

**pins layout**

-   [Raspberry Pi Pinout](https://pinout.xyz/)

-   [GPIO and the 40-pin Header](https://www.raspberrypi.com/documentation/computers/raspberry-pi.html)

-   [HUB75 Pinout](https://www.google.com/imgres?imgurl=https%3A%2F%2Fhackster.imgix.net%2Fuploads%2Fimage%2Ffile%2F146125%2Fidc-hub75-connector.jpg%3Fauto%3Dcompress%252Cformat%26w%3D740%26h%3D555%26fit%3Dmax&tbnid=TDTiTN1TQVEzeM&vet=12ahUKEwjD-MfBhcyCAxWKGEQIHScKAHAQMygMegQIARBu..i&imgrefurl=https%3A%2F%2Fwww.hackster.io%2Faleksand1975%2Fhub75-led-display-driver-777bac&docid=63DavVdH8vuVcM&w=487&h=555&q=hub75e%20pinout&hl=en&ved=2ahUKEwjD-MfBhcyCAxWKGEQIHScKAHAQMygMegQIARBu)

**documentation**

-   [Adafruit's Raspberry Pi Lesson 6. Using SSH](https://learn.adafruit.com/adafruits-raspberry-pi-lesson-6-using-ssh)
-   [ssh remote host identification has changed [closed]](https://stackoverflow.com/questions/20840012/ssh-remote-host-identification-has-changed)
-   [Adafruit RGB Matrix Bonnet for Raspberry Pi](https://www.adafruit.com/product/3211)

-   [hzeller/rpi-rgb-led-matrix](https://github.com/hzeller/rpi-rgb-led-matrix)

