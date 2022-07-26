---
header:
    header: /assets/images/posts/2022-07-25-some-ubuntu-customizations/stock-photo.jpg
    teaser: /assets/images/posts/2022-07-25-some-ubuntu-customizations/stock-photo.jpg
    og_image: /assets/images/posts/2022-07-25-some-ubuntu-customizations/stock-photo.jpg
    overlay_image: /assets/images/posts/2022-07-25-some-ubuntu-customizations/stock-photo.jpg
tags: 
    - Tracking
excerpt: "This post keeps track of some running customizations I like to use on Ubuntu."
---

This post keeps track of some running customizations I like to use on Ubuntu.

## Gogh
[`Gogh`](https://github.com/Gogh-Co/Gogh) is an awesome CLI tool for implementing aesthetically pleasing terminal colour schemes. The default terminal for Ubuntu is Gnome, and this package will work right out of the box for Ubuntu. I'm a sucker for the `gruvbox` theme for most of my applications. I think the `BelafonteNight` and the `Azu` dark themes are really nice too. 

## Setting up the `/opt/` directory
If you find yourself running certain executables all the time, but you don't want to `cd` back to the location of those executables everytime you want to run them, you should move those executables (or at least put in a symlink) into the `/opt/` directory. This directory refers to 'optional' software. Then, add the following line to your `.bashrc` file (which is located in your home directory, or `~/`):

```bash
export PATH=$PATH:/opt/
```

Then, restart the terminal. Now, you'll be able to call any executables that are in your `/opt/` directory, from anywhere on the terminal!