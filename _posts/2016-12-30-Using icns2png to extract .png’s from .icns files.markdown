---
layout: post
title:  "Using icns2png to extract .png’s from .icns files"
date:   2016-12-30 12:00:00
tags: [munki, macos]
---

Munki’s Managed Software Center wouldn’t look nearly as good without [Product Icons](https://github.com/munki/munki/wiki/Product-Icons). Getting these icons can be tedious, but it doesn’t have to be!

The majority of app icons come in the [Apple Icon Image format (.icns)](https://en.wikipedia.org/wiki/Apple_Icon_Image_format). Converting them to a .png can be done by opening the .icns file in Apple’s built-in [Preview.app](https://en.wikipedia.org/wiki/Preview_(macOS)) and going to File > Export > choosing “PNG” from the format list > clicking Save. From there you can resize the image to Munki’s preferred resolution of 350x350px directly in Preview.app, or in another image editor such as Photoshop. OR you can use _icns2png_!

If you haven’t already, install [Homebrew](http://brew.sh). Once that’s done, launch Terminal and type `brew install libicns` to install _icns2png_.

With that out of the way, let’s convert Spotify’s icon from an .icns to a .png image. Launch Terminal and enter:

`icns2png -x /Applications/Spotify.app/Contents/Resources/Icon.icns -o ~/Desktop/`

The command above will extract the Spotify icon in different sizes to your Desktop. Now resize it, copy it over to your repo’s icons directory, and give yourself a high-five and you’re all set!

One more thing: Here’s how to extract a .png from an .icns file, and resize the image to 350x350px in one line:

`icns2png -x -s 512x512 /Applications/Spotify.app/Contents/Resources/Icon.icns -o ~/Desktop/;sips -Z 350 *.png`

Now go make your Managed Software Center look better than it currently does!