---
layout: post
title:  "Deleting a APFS Container"
date:   2017-12-22 12:00:00
tags: [macos]
---

1. Boot up from a bootable macOS installer USB
2. In the menu bar, click on Utilities and then Terminal
3. Type `diskutil apfs list` to list the APFS Container(s)
	* More information on APFS Containers can be found here.
4. Type `diskutil apfs deleteContainer disk1`

*Note*: Your container might not be named “disk1”