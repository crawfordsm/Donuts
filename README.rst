=======
Donuts
=======

.. image:: https://travis-ci.org/jmccormac01/Donuts.svg?branch=master
    :target: https://travis-ci.org/jmccormac01/Donuts
.. image:: https://landscape.io/github/jmccormac01/Donuts/master/landscape.svg?style=flat
   :target: https://landscape.io/github/jmccormac01/Donuts/master
   :alt: Code Health
.. image:: https://coveralls.io/repos/github/jmccormac01/Donuts/badge.svg?branch=master 
   :target: https://coveralls.io/github/jmccormac01/Donuts?branch=master
.. image:: https://badges.gitter.im/jmccormac01/Donuts.svg?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge
   :target: https://gitter.im/jmccormac01/Donuts

A science frame autoguiding and image alignment algorithm with sub-pixel precision, capable of guiding on defocused stars. 

Motivation
----------

We operate and have access to several telescopes (NGTS, NITES, Warwick 1m, 1.5m San Pedro Martir) that require precise autoguiding. Sometimes we must defocus the telescope for various reasons, but we'd still like to autoguide. Donuts was designed to allow this. It had to be simple, fast and accurate. It works well as an autoguiding algorithm for equatorial telescopes (no field rotation). 

The process for aligning apertures for photometry is essentially the reverse. Rather than correcting the telescope pointing, the apertures must track the drift of the stars. Donuts can therefore be used to track the stellar positions for CCD photometry also. 

By default Donuts measures frame-to-frame translational offsets (X and Y) using all the stars in the image. This can be adjusted in the settings to select a specific region of interest (for extremly wide or distorted fields). 

The algorithm has its limitations. It currently does not deal with rotation and large drifts, where the field moves by approx. half a FOV or more. Our paper describing the details can be found here:

http://adsabs.harvard.edu/abs/2013PASP..125..548M

Example
-------

Below is an sample of 10 nights autoguiding residuals from NGTS while using Donuts. The upper plot shows the frame to frame error, while the bottom shows the drift which would have occured, if not for Donuts. Aligning photometry apertures is essentially the same process and similar performance is expected under that scenario. We routinely achieve an autoguiding RMS 1/20 pixels with NGTS. 

.. image:: AgResiduals_802_March2016.png


Installation
------------

This package is currently pre-alpha. We don't recommend using it just yet :)
 

Contributors
------------

`James McCormac <https://github.com/jmccormac01>`_.
`Simon Walker <https://github.com/mindriot101>`_.


License
-------

MIT License

Copyright (c) 2016 James McCormac & Simon Walker

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


