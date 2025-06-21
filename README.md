# Tekst-tv

Sider til tekst-tv-tjenesten tekst-tv.dk

# Bygge en Raspberry Pi model B tekst-tv box

1. Hent Raspberry Pi OS Lite (version unden grafisk desktop) fx [denne](https://downloads.raspberrypi.com//raspios_lite_arm64/images/raspios_lite_arm64-2025-05-13/2025-05-13-raspios-bookworm-arm64-lite.img.xz)
2. Brænd den på et SD-kort. Gøre nemt med Raspberry Pi Imager, hentes [her](https://www.raspberrypi.com/software/)
3. Boot Raspberyy Pi'en
4. Opdater med `sudo apt -y update && sudo apt -y upgrade`
5. Udkommentér videocore 3D driver:
   1. `sudo nano /boot/config.txt`
   2 Udkommentér linjen: `dtoverlay=vc4-kms-v3d`, så den ser således ud: `#dtoverlay=vc4-kms-v3d`
6. Slå Composite output til:
   1. `sudo raspi-config` og vælg Display Options > Composite
7. Slå overscan compensation fra:
   1. Display Options > Underscan sættes til ‘No’
8. Reboot
9. Installér VBIT:  `curl https://raw.githubusercontent.com/peterkvt80/vbit2/master/getvbit2 | bash`
10. Vent en rum tid
11. Installer custom service i vbit-config: https://github.com/thomasboevith/tekst-tv.git
