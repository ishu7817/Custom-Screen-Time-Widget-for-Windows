Cinematic Screen Time Widget
A dark, cinematic-style screen time dashboard designed for Windows, built to run seamlessly inside Lively Wallpaper.

Features
Cinematic Aesthetic: A dark, moody, anime styled widget that can blend into your desktop wallpaper.

Smart Data Parsing: Automatically identifies and separates your active Chrome tabs!! (e.g., Pinterest vs. Gemini vs. VS Code) so you can see what you were actually working on instead of clumping them all as "Chrome.exe."

Live Updates: Refreshes your stats every 60 seconds.



Install these: 
ActivityWatch (chill, completely free and open source): Install and run this in the background. It is the thing that tracks your time locally.
Here's the link: https://activitywatch.net/downloads/

Lively Wallpaper (Free- Microsoft Store): Install this to host the widget on your desktop.
Here's the link: https://rocksdanister.github.io/lively/


Installation Guide
Create a new folder on your computer...like, screenTimeWidget.

Download the Screen-Time-Widget.html file from this repo and move it into that folder.

Crucial: Move your preferred background image and the widget image (or the images already included in the repo) into this same folder. If you chose a different image, rename it as "wallpaper.jpg" (for the image you want as wallpaper) and "widget.jpg (for the image you want on the widget) or replace the filenames (widget.jpg and wallpaper.jpg) with the actual file names in the file  (use Ctrl + F to search for specific text, like "wallpaper")




Add to Lively:

Open Lively Wallpaper.

Click the + (Add) button.

Drag and drop your folder (or select the HTML file manually) into the Lively window. It will detect the HTML file and turn it into a live wallpaper.



Verify ActivityWatch:

Ensure ActivityWatch is running: click the arrow in your taskbar, right-click the ActivityWatch icon, and select Open Dashboard. If you see data moving there, the widget will pick it up automatically!


⚠️ Crucial Step: Enable CORS
This is mandatory. If the widget says "Connection blocked," it’s because ActivityWatch is protecting your data from being accessed by the browser. You need to "unlock" it:


1. Open your File Explorer.

2. Click on This PC in the left sidebar.

3. Open your Local Disk (C:).

4. Open the Users folder.

5. Open the folder with your username (the one you log into your PC with).

6. Look for a folder named AppData.
Note: If you don't see AppData, it is hidden! Click the "View" tab at the top of File Explorer -> Show -> check "Hidden items".

7. Now, follow this chain:

>Local
>activitywatch
>>aw-server

Inside aw-server, you should see the aw-server.ini or aw-server.toml file. Right-click it and select Open with -> Notepad.

Once you are inside the file:
select all the code there (ctrl + a) and paste this exact code there: 




[server]
host = 127.0.0.1
port = 5600
cors_allowed_origins = ["*"]



Customization
Change Background: Simply swap the image file in your folder (keep the name same) or if you want a different name, replace the filenames (widget.jpg and wallpaper.jpg) with the actual file names in the file (use Ctrl + F to search for specific text, like "wallpaper")


Troubleshooting
Widget says "Connection blocked": Make sure ActivityWatch is actually running! The widget needs the local server at 127.0.0.1:5600 to be active.

Data not appearing: Give ActivityWatch a few minutes to record your initial movements; it won't show data for the last 5 minutes if you haven't done anything on the PC yet.

