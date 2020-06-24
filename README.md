# Quick start on ESP 8266 with Micropython Support

# ESP8266 Micropython firmware
Download link: http://micropython.org/download/esp8266/

### Installing esptool
```
pip install esptool
```

### Check flash size:
```
esptool.py --port /dev/cu.usbserial-1420 flash_id
```
### Flash firmware
```
esptool.py --port /dev/cu.usbserial-1420 flash_id
```
Erase first, this is important step due to previous fw may have bigger size.
```
esptool.py --port /dev/cu.usbserial-1420 erase_flash
```

Flash the Micropython firmware
```
esptool.py --port /dev/cu.usbserial-1420 --baud 460800 write_flash --flash_size=detect -fm dio 0 esp8266-20191220-v1.12.bin
```

### Test with REPL
```
screen /dev/cu.usbserial-1420 115200
```
Then enter
```
import esp
esp.check_fw()
```
The return must be true.

