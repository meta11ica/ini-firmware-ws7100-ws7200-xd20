# ini-firmware-ws7100-ws7200-xd20
Generate corresponding INI file for the BIN firmware for Huawei AX3 and Honor Router 3

In order to push a .bin firmware through the Multicast Upgrade Tool (MUT) from Huawei you need two files :
- the .bin firmware
- a .ini file which is a collection of metadata of rhe firmware (file name, checksum of the firmware and checksum of the ini file)

If you upgrade directly from the Router's GUI, you only need the .bin file and you DON'T need this tool.
However, if you throw only the .bin file to Multicast Upgrade Tool MUT, you will have the error "ini file error".

Firmwares as well as the MUT tool the can be found across the internet.

You need a Python interpreter installed in your PC to run the Python script.

There're two scripts :
- generate_ini_file.py : which is CLI based.
The usage is :
**python generate_ini_file.py somefirmwarefile.bin**

This will generate a .ini file with the same filename in the working folder

- generate_ini_file_gui.py : which is GUI based.

Usage :
**python generate_ini_file_gui.py**

A window will open with a single button to select the firmware file, then the script will generate the .ini file and put it in the same folder as the .bin file



The Tool will take the following information from the firmware and put them in the .ini :
- IMAGE_NAME : the firmware file name
- IMAGE_SIZE : the size in bytes of the firmware
- FIRMWARE_CRC_SUM : the crc32 of the firmware
- INI_CRC_SUM : the crc32 of the ini file

I didn't tweak the variable "PARTITIONS" as it seems consistent for the AX3 (Global WS7100-20 and Chinese WS7100-10), AX3 PRO and Honor 3 (XD-20).
So make sure it's OK for you.


95% of the script is developed by ChatGPT
