# Sentinel

**Sentinel** is a cross-platform USB missile launcher face-tracking solution. It will attempt to track faces, continually point the missile launcher at the clearest face, and optionally shoot foam missiles.

Impress your friends! Intimidate your enemies!

![Demonstration of Sentinel](https://raw.github.com/AlexNisnevich/sentinel/master/demonstration.jpg)

1\.  [Hardware Requirements](#hardwarerequirements)  
2\.  [Software Requirements and Installation](#softwarerequirementsandinstallation)  
2.1\.  [Linux](#linux)  
2.2\.  [Windows](#windows)  
2.3\.  [Mac OS X](#macosx)  
3\.  [Usage](#usage)  

<a name="hardwarerequirements"></a>

## 1\. Hardware Requirements
- **[Dream Cheeky brand USB missile launcher](http://www.amazon.com/Dream-Cheeky-908-Electronic-Reference/dp/B004SAYO46)** (tested with the Thunder model, should also work with the Storm model)
- small **webcam** attached to USB missile launcher (tested with Logitech C270)

<a name="softwarerequirementsandinstallation"></a>

## 2\. Software Requirements and Installation

<a name="linux"></a>

### 2.1\. Linux
If you're on Ubuntu 12.04+ or Debian (tested with Linux Mint Debian), you can simply run the included installation script:
```
> sudo install/ubuntu_debian.sh
```

Otherwise (or if the script doesn't work for you), install the following dependencies:

- **Python** 2.7, 32-bit
- **libusb** 1.0 (in Ubuntu/Debian, `sudo apt-get install libusb-dev`)
- **PyUSB** 1.0 (https://github.com/walac/pyusb)
- **OpenCV** 2.3+ with Python bindings
  - In Ubuntu 12.04+ or latest Debian, `sudo apt-get install python-opencv` will install the correct version
  - In older versions of Ubuntu, you can follow [these instructions](http://jayrambhia.wordpress.com/2012/06/20/install-opencv-2-4-in-ubuntu-12-04-precise-pangolin/) or use [this bash script](https://github.com/jayrambhia/Install-OpenCV/blob/master/Ubuntu/2.4/opencv2_4_3.sh) (tested with 11.10)
  - In ArchLinux, `pacman -S python2-numpy` then `pacman -S opencv 2.4.0_a-4`
- **streamer** (in Ubuntu/Debian, `sudo apt-get install streamer`)
- **ImageMagick** (in Ubuntu/Debian, `sudo apt-get install imagemagick`)

After installing all of the software requirements, you can run Sentinel:
```
> sudo ./sentinel.py
```

<a name="windows"></a>

### 2.2\. Windows

Install the following dependencies:

- **Python** 2.7, 32-bit
- **libusb-win32** (http://sourceforge.net/projects/libusb-win32/files/)
   - After installing, plug in USB missile launcher, launch *[libusb path]\bin\inf-wizard.exe*, and create and run an INF driver file for the USB rocket launcher using the wizard
- **PyUSB** 1.0 (https://github.com/walac/pyusb)
- **NumPy** (http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy)
- **OpenCV** 2.3+ with Python bindings (http://sourceforge.net/projects/opencvlibrary/files/opencv-win/2.3.1/OpenCV-2.3.1-win-superpack.exe/download)
   - After installing, copy the contents of *[opencv path]\build\python\2.7* (it should contain *cv.py* and *cv2.pyd*) to *C:\Python27\Lib\site-packages*

After installing all of the software requirements, you can run Sentinel from Python IDLE or from the command line:
```
> C:\Python27\python sentinel.py
```

<a name="macosx"></a>

### 2.3\. Mac OS X

If you have [Homebrew](http://mxcl.github.com/homebrew/), you can simply run the included installation script:
```
> sudo install/mac_osx.sh
```

Otherwise (or if the script doesn't work for you), install the following dependencies:

- **Python** 2.7, 32-bit (if not pre-installed)
- **libusb** 1.0 (`sudo port install libusb` or `sudo brew install libusb-devel +universal`)
- **PyUSB** 1.0 (https://github.com/walac/pyusb)
- **NumPy** (`pip install numpy`)
- **OpenCV** 2.3+ with Python bindings (`sudo port -v install opencv +python27` or `sudo brew install opencv`)

After installing all of the software requirements, you can run Sentinel:
```
> sudo python ./sentinel.py
```

<a name="usage"></a>

## 3\. Usage

```
Usage: sentinel.py [options]

Options:
  -h, --help            show this help message and exit
  -d, --disarm          track faces but do not fire any missiles
  -r, --reset           reset the turret position and exit
  --nd, --no-display    do not display captured images
  -c NUM, --camera=NUM  specify the camera # to use. Default: 0
  -s WIDTHxHEIGHT, --size=WIDTHxHEIGHT
                        image dimensions (recommended: 320x240 or 640x480).
                        Default: 320x240
  -b SIZE, --buffer=SIZE
                        size of camera buffer. Default: 2
  -v, --verbose         detailed output, including timing information
```
