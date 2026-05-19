# YellowKey
YellowKey Bitlocker Bypass Vulnerability

Been a while since I saw a bitlocker bypass around, my turn.

This is one of the most insane discoveries I ever found, almost feels like **backdoor** but what do you know, maybe I'm just insane.

How to reproduce : 
1. Copy the FsTx folder to "**YourUSBStick:**\System Volume Information\FsTx" as is and make sure to use a filesystem that's compatible with Windows (NTFS is preferable but I think FAT32/exFAT should work)
2. Plug the USB stick in your target windows computer with bitlocker protection turned on.
3. Reboot to Windows Recovery Environment Agent (you can do that by holding SHIFT and clicking on the restart button using your mouse)
4. Once you click on the restart button, lift your finger off the SHIFT key and hold CRTL and do NOT lift your finger off it.
5. If you did everything properly, a shell will spawn with unrestricted access to the bitlocker protected volume.

<img width="1370" height="777" alt="shell" src="https://github.com/user-attachments/assets/eda6c823-4a6b-4aec-bad2-b9afad640dd6" />

## POC

[Download POC Video](poc.mp4)

Now why would I say this is a **backdoor** ? The component that is responsible for this bug is not present anywhere (even in the internet) except inside WinRE image and what makes it raise suspicions is that it's a component that's ONLY present in the WinRE image and not present in the main OS installation.

A huge thanks to MORSE, MSTIC and Microsoft GHOST for making this public disclosure possible ;)
