# UT330B
Operating system independent controller for the Uni-Trend UT330 family of temperature and humidity loggers.

I've blogged about this software on my blog: https://blog.engora.com/2020/02/reverse-engineering-sensor.html

What the software does
======================

The [Uni-Trend UT330B](https://www.uni-trend.com/html/product/Environmental/Environmental_Tester/UT330-USB/UT330B.html) is a battery-powered USB temperature and humidity logger. Off-the-shelf, it only comes with Windows control software. This project provides Python code to control the device from any operating system.

IT should work with other members of the UT330 family - and has been tested with at least UT330A and UT330B.

This project is a complete package, including software, a test script, a demo UI (written in Bokeh), and full documentation. 
 
<img src="https://github.com/MikeWoodward/UT330B/blob/master/Documentation/chart.png"/> 

<img src="https://github.com/MikeWoodward/UT330B/blob/master/Documentation/ui.png"/> 

Acknowledgements
================

Many thanks to [Philip Gladstone](https://github.com/pjsg) for his tremendous help with this project.

Installation notes
==================

The project uses uses pyserial __version 3.01 or later__. This version uses Bokeh version 3.0.3. See the Documentation section for instructions for how to use the software.

The easiest is to simply use uv to run:
    uv run bokeh serve UT330BUI --show

This must run with read/write access to the `/dev/ttyUSB0` device. By default on Ubuntu this device is in the `dialout` group, so simplest is to add your user to that group, restart, and then execute the above as yourself.

Oddities
========

I updated this software in February 2020. For some unknown reason, the UT330B device won't accept date settings in February 2020, and won't function in February 2020. I think this is a device issue (maybe firmware?) but I can't confirm it - perhaps something to do with 2020-02. If anyone has any insight, I'd love to hear it.
