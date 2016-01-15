audio_hdmi_hd3000/ssdt-hdmi-hd3000
============
OS X Sandy Bridge/6 Series/Socket 1155 - HD3000 HDMI Audio ssdt
OS X Sandy Bridge/7 Series/Socket 1155 - HD3000 HDMI Audio ssdt

ssdt_hdmi-hd3000-6series-3
Supports Desktop/HD3000
Injects SNB/framebuffer: 0x26010000 (DP DP HDMI)
Requires Audio ID: 3

ssdt_hdmi-hd3000-7series-3
Supports Desktop/HD3000
Injects SNB/framebuffer: 0x26010000 (DP DP HDMI)
Injects MEI,  0x3A1C0000
Requires Audio ID: 3

HD 3000 HDMI audio
OS X/Desktop/HD3000 audio is native, see
[Guide]_HD3000-hdmi_audio_(dsdt_or_ssdt)
https://github.com/toleda/audio_hdmi_hd3000

HD3000 HDMI audio:
1. DP audio is native
2. HDMI audio is native (requires HDMI connector on SNB/Port 0x7)

HD3000 AirPlay Mirroring is native

Installation (included in download)
1. [Guide]-OSX_ssdt-installation

toleda
https://github.com/toleda/audio_hdmi_hd3000/ssdt-hdmi-hd3000
README.txt