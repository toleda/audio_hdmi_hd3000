Use audio_hdmi_hd3000
============
OS X AMD/Nvidia/HD3000 HDMI Audio dsdt edits

This guide enables OS X HDMI audio on Intel based motherboards with a bootable clean install of OS X.  Supported HDMI audio graphics systems are AMD discrete graphics cards (HD5xxx, HD6xxx and HD7xxx), Nvidia discrete graphics cards (4xx, 5xx, 6xx and 7xx) and Intel HD3000 integrated graphics systems.  The Optimized AppleHDA.kext supports HDMI audio and Realtek audio codecs (ALC885, ALC887, ALC888, ALC889, ALC892, ALC898) for onboard audio.  The native ML AppleHDA.kext supports only HDMI audio when configured properly. In Mountain Lion, the Optimized AppleHDA.kext supports 2 Audio_IDs for HDMI and Realtek onboard audio:
Audio_ID: 1 supports AMD/Nvidia HDMI and 3, 5 and 6 port ALC8xx onboard audio  
Audio_ID: 3 supports HD3000/HD4000 HDMI and 3, 5 and 6 port ALC8xx onboard audio

Note
1. Native ML AppleHDA.kext, use Audio_ID: 1, for HDMI audio/no onboard audio
2. Integrated and Discrete HDMI audio, use Audio_ID:3, for HDMI audio and Realtek on board audio

OS X versions supported
1. Mavericks.10.9 and newer
2. Mountain Lion/10.8.2 and newer

More Information
1. Mountain Lion: Optimized AppleHDA for Realtek ALC8xx
http://www.tonymacx86.com/audio/76202-mountain-lion-optimized-applehda-realtek-alc8xx.html#post472375
2. Mountain Lion HDMI Audio - AMI DSDT
http://www.tonymacx86.com/hdmi-audio/70762-mountain-lion-hdmi-audio-ami-dsdt.html
3. Mountain Lion HDMI Audio - Award DSDT
http://www.tonymacx86.com/hdmi-audio/70758-mountain-lion-hdmi-audio-award-dsdt.html

Two ML HD3000 HDMI audio enabling techniques - select one
1. ML: HD3000 HDMI Audio dsdt (with dsdt edits) 
2. ML: HD3000 HDMI Audio ssdt (with native dsdt)

ML HD3000 HDMI Audio dsdt edits
1. MaciASL - http://sourceforge.net/projects/maciasl/?source=navbar
2. Configuration: MaciASL/Preferences/Sources/+/  (copy/paste URL, don't click)
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

ML: HD3000 HDMI Audio ssdt
1. https://github.com/toleda/audio_hdmi_hd3000/tree/master/ssdt_6series
2. Copy Downloads/audio_ssdt-hdmi.. . ./SSDT-1.aml to Extra
2a. If Extra/SSDT.aml is present, install SSDT-1.aml as is: Extra/SSDT-1.aml
2b. If no Extra/SSDT.aml, rename SSDT-1.aml to SSDT.aml and install as: Extra/SSDT.aml
2c. The 1st SSDT is SSDT, 2nd is SSDT-1, 3rd is SSDT-2, etc.; no gaps
3. Enable ssdt
3a. Chameleon/Chimera: Add DropSSDT=Yes to org,chameleon.Boot.plist
3b. Clover: Set DropOem=true to config.plist/ACPI/SSDT
4. Rebuild kernel cache
5. Restart

Problem Reporting
1. Motherboard/BIOS version/processor/graphics/OS and version
2. Copy of dsdt (if edited)
3. Copy of HDMI audio SSDT (if installed)
4. Copy of IORegistryExplorer

Troubleshooting/Post w/attachments 2-4, above
1. Mavericks/10.9
1a. http://www.tonymacx86.com/hdmi-audio/112469-mavericks-hdmi-audio-applehda.html
1b. http://www.insanelymac.com/forum/topic/292999-mavericks-applehda-hdmi-audio/
2. Mountain Lion/10.8
2a.http://www.tonymacx86.com/hdmi-audio/70762-mountain-lion-hdmi-audio-ami-dsdt.html
2b. http://www.insanelymac.com/forum/topic/291103-mountain-lion-hdmi-audio/

Guides:
1. HD3000/Sandy Bridge/2rd Generation Core Processors/6 Series motherboards
1a. [Guide]- HD3000-hdmi_audio_dsdt_edits_v1.1.pdf.zip
1b. Patches (Note: for A3, Find: 0x01, 0x00, 0x00, 0x00/Replace: 0x03, 0x00, 0x00, 0x00)
    IB1. AMI-EFI-Clean Compile - fix native dsdt compiler errors for successful dsdt edits
    SB2. AMI-EFI-HD3000-AMD-Nvidia-6_Series-A1 - AMD/Nvidia/HD3000 HDMI audio dsdt edits
    SB3. AMI-BIOS-HD3000-AMD-Nvidia-6_Series-A1 - AMD/Nvidia/HD3000 HDMI audio dsdt edits
    SB4. Award-BIOS-HD3000-AMD-Nvidia-6_Series-A1 - AMD/Nvidia/HD3000 HDMI audio dsdt
         edits
    SB5. HD3000-on-7_Series_MB - HD3000 MEI dsdt edit
1c. ssdts
    audio_ssdt-hdmi-ami_hd3k-amd-nvidia-3_v2.zip
    audio_ssdt-hdmi-award_hd3k-amd-nvidia-3_v1.zip

toleda
https://github.com/toleda/audio_hdmi_hd3000
Patches
README.txt