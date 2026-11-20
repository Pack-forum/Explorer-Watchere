EXPLORER WATCHER - launcher for Navitech QX B12 Primo (Windows CE)

FILES
  preview.html  -> open in a browser: lock screen, home, photos, settings, wallpaper
  src/main.cpp  -> launcher source (Win32 + GDI, single file, no libs)

FEATURES
  - Lock screen with big clock + date (tap to unlock; "Lock" button on the top bar)
  - Photos: finds pictures on SD card / USB automatically (up to 300, 3 folder levels deep)
      Previous / Next buttons, "Set as wallpaper" button
      BMP always works. JPG/PNG/GIF work only if the device has aygshell.dll (SHLoadImageFile);
      if not, the screen says "Cannot open this file" -> convert those pictures to BMP.
  - Settings: Wallpaper, Lock now, Photo sources
  - Wallpaper: 4 built-in gradients + your own pictures in \Storage Card\EW\Wallpapers\
      or any photo via the viewer. Choice saved in \Storage Card\EW\wallpaper.cfg
  - Tiles: icon and text are in separate areas, they cannot overlap
  - Touch calibration is NOT used or changed anywhere. No system settings are touched.

BUILD (on PC)
  1. Visual Studio 2008 (or 2005) + the Windows CE SDK of your device.
  2. New Project > Smart Device > Win32 Smart Device Project > Windows Application, Empty.
  3. Add src/main.cpp. Character Set = Unicode. Platform = your SDK (usually ARMV4I).
  4. Build.

INSTALL (safe order)
  1. Back up the original launcher exe to your PC.
  2. Copy the new exe to the micro SD and run it by hand. Test every tile.
  3. When it works, put it where the original launcher lives with the same file name.
  4. Keep the original radio / bluetooth / camera exes. "Car Apps" points to one of them
     (edit the paths at the top of main.cpp).

NOTE: not compiled/tested on a real device yet. If the compiler complains about a
function your CE version lacks, send the error and it will be fixed.
