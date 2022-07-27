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

Some quick and useful customizations I recommend for Ubuntu:

## Gogh
[`Gogh`](https://github.com/Gogh-Co/Gogh) is an awesome open-sourced CLI tool for implementing aesthetically pleasing terminal colour schemes. The default terminal for Ubuntu is Gnome, and this package will work right out of the box for Ubuntu. It can be installed with just: 

```bash
bash -c "$(wget -qO- https://git.io/vQgMr)"
```

I'm a sucker for the `gruvbox` theme for most of my applications. I think the `BelafonteNight` and the `Azu` dark themes are really nice too. 

## Pinta
[Pinta](https://www.pinta-project.com/) is a simple open-sourced image editor that's basically the Linux equivalent of Microsoft paint. It's great for doing quick edits, like cropping and emphasizing certain things with shoddily drawn arrows and circles. The [official documentation](https://www.pinta-project.com/user-guide/) for Pinta is also quite good. 

## Setting up the `/opt/` directory
If you find yourself running certain executables all the time, but you don't want to `cd` back to the location of those executables everytime you want to run them, you should move those executables (or at least put in a symlink) into the `/opt/` directory. This directory refers to 'optional' software. Then, add the following line to your `.bashrc` file (which is located in your home directory, or `~/`):

```bash
export PATH=$PATH:/opt/
```

Then, restart the terminal. Now, you'll be able to call any executables that are in your `/opt/` directory, from anywhere on the terminal!

## FFmpeg
Probably the most powerful video-editing CLI, in existence. Everything can be done in FFmpeg. If writing software that calls FFmpeg, e.g. some Python module, I would most certainly not depend on a system install, but would rather specify the version of FFmpeg via some kind of package manager[^1]. For quick video edits, however, relying on a system install of FFmpeg is perfect. 

{:footnotes}
[^1]: If using Python, I'd most certainly recommend [Anaconda](https://www.anaconda.com/). Here's a [sample configuration file](https://github.com/hanhanhan-kim/vidtools/blob/master/conda_env.yaml) for an Anaconda environment that calls a specific version of OpenCV (which installs a specific version of FFmpeg), for my [`vidtools`](https://github.com/hanhanhan-kim/vidtools) module. Identical formatting can be used to directly install a specific Anaconda version of FFmpeg, instead of an installation via OpenCV). Note also the installation of the very useful [`ffmpeg-python` module](https://github.com/kkroening/ffmpeg-python).

## Kamoso
[Kamoso](https://github.com/KDE/kamoso) is an open-sourced webcam software that lets you take photos and videos with a connected webcam. It can also be used for vide conferencing, e.g. Zoom. It's also written mostly in C++, so it's super fast! It can be installed with just:

```bash
sudo apt install kamoso
```
