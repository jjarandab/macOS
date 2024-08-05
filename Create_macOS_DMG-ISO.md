# Create macOS DMG-ISO

1. Download [MacOS](https://support.apple.com/en-us/102662) installer from the Mac App Store (Mojave in this case)

2. On macOS Terminal, create a disk image DMG
   
   `hdiutil create -o /tmp/Mojave -size 6000m -volname Mojave -layout SPUD -fs HFS+J`

3. Mount the DMG
   
   `hdiutil attach /tmp/Mojave.dmg -noverify -mountpoint /Volumes/Mojave`

4. Create the macOS installer application on the mounted DMG
   
   `sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/Mojave --nointeraction`

5. Unmount the DMG
   
   hdiutil detach /volumes/Install\ macOS\ Mojave

6. Convert the DMG to an CDR
   
   `hdiutil convert /tmp/Mojave.dmg -format UDTO -o ~/Desktop/Mojave.cdr`

7. Rename the CDR to ISO; move DMG file to desktop
   
   `mv ~/Desktop/Mojave.cdr ~/Desktop/Install macOS Mojave.iso 
   mv ~/tmp/Mojave.dmg ~/Desktop/Install macOS Mojave.dmg`
