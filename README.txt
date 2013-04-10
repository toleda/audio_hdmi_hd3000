Use audio_hdmi_hd3000
============
OS X AMD/Nvidia/HD3000 HDMI Audio dsdt edits

This guide enables OS X HDMI audio on Intel based motherboards with a bootable clean install of OS X.  Supported HDMI audio graphics systems are AMD discrete graphics cards (HD5xxx and HD6xxx), Nvidia discrete graphics cards (4xx, 5xx and 6xx) and Intel HD3000 integrated graphics systems.  The Optimized AppleHDA.kext supports HDMI audio and Realtek audio codecs (ALC885, ALC887, ALC888, ALC889, ALC892 and ALC898) for onboard audio.  The native ML AppleHDA.kext supports only HDMI audio when configured properly. In Mountain Lion, the Optimized AppleHDA.kext supports 2 Audio_IDs for HDMI and Realtek onboard audio:
Audio_ID: 1 supports AMD/Nvidia HDMI and 3, 5 and 6 port ALC8xx onboard audio  
Audio_ID: 3 supports HD3000/HD4000 HDMI and 3, 5 and 6 port ALC8xx onboard audio

Note
1. Native ML AppleHDA.kext, use Audio_ID: 1, for HDMI audio/no onboard audio
2. Integrated and Discrete HDMI audio, use Audio_ID:3, for HDMI audio and Realtek on board audio

More Information
1. Mountain Lion: Optimized AppleHDA for Realtek ALC8xx
http://www.tonymacx86.com/audio/76202-mountain-lion-optimized-applehda-realtek-alc8xx.html#post472375
2. Mountain Lion HDMI Audio - AMI DSDT
http://www.tonymacx86.com/hdmi-audio/70762-mountain-lion-hdmi-audio-ami-dsdt.html
3. Mountain Lion HDMI Audio - Award DSDT
http://www.tonymacx86.com/hdmi-audio/70758-mountain-lion-hdmi-audio-award-dsdt.html

ML HD3000 HDMI Audio dsdt edits
1. MaciASL - http://sourceforge.net/projects/maciasl/?source=navbar
2. Configuration: MaciASL/Preferences/Sources/+/
3. URL: https://raw.github.com/toleda/audio_hdmi_hd3000/master
4. Download/ZIP: https://github.com/toleda/audio_hdmi_hd3000

Usage
1. If no dsdt. extract dsdt, MaciASL/File/New from ACPI/DSDT
2. MaciASL/File/Open dsdt
3. MaciASL/Patch/toleda_hdmi_hd3000/Select Patch/es
4. MaciASL/Patch/Apply (Repeat, as necessary) 
5. MaciASL/Patch/Close
6. MaciASL/Compile
7. MaciASL/File/Save As…/ACPI Machine Language Binary/dsdt.aml

Installation - edited dsdt.aml to Extra
1. MaciASL/File/Save As…/ACPI Machine Language Binary/Extra/dsdt.aml (add extension)

Guides:
1. Sandy Bridge/HD3000/2rd Generation Core Processors/6 Series motherboards
1a. [Guide] ML-Sandy_Bridge-HD3000-6_series-hdmi_audio_dsdt_edits (AMI/Award dsdt)
1b. Patches (Note: for A3, Find: 0x01, 0x00, 0x00, 0x00/Replace: 0x03, 0x00, 0x00, 0x00)
    IB1. AMI-EFI-Clean Compile - fix native dsdt compiler errors for successful dsdt edits
    SB2. AMI-EFI-HD3000-AMD-Nvidia-6_Series-A1 - AMD/Nvidia/HD3000 HDMI audio dsdt edits
    SB3. AMI-BIOS-HD3000-AMD-Nvidia-6_Series-A1 - AMD/Nvidia/HD3000 HDMI audio dsdt edits
    SB4. Award-BIOS-HD3000-AMD-Nvidia-6_Series-A1 - AMD/Nvidia/HD3000 HDMI audio dsdt
         edits
    SB5. HD3000-on-7_Series_MB - HD3000 MEI dsdt edit
1c. Troubleshooting/AMI/Post to http://www.tonymacx86.com/hdmi-audio/70762-mountain-lion-hdmi-audio-ami-dsdt.html
1d. Troubleshooting/Award/Post to http://www.tonymacx86.com/hdmi-audio/70758-mountain-lion-hdmi-audio-award-dsdt.html

2. Ivy Bridge/HD4000/3rd Generation Core Processors/7 Series motherboards/AMI EFI
github.com/toleda/audio_hdmi_hd4000

3. Nehalem/1st Generation Core Processors/5 Series motherboards (No HD Graphics)
github.com/toleda/audio_hdmi_5series

toleda
https://github.com/toleda/audio_hdmi_hd3000
Patches
README.txt