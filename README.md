Video Tester - Video Quality Assessment Tool
============================================

Video Tester is a framework for video quality assessment over a real or simulated IP network. Parameter extraction is performed on the three levels involved in the video processing and transmission ---packet level, bitstream level and picture level--- in order to gather as much information as possible. Therefore, it is suitable for implementing any kind of metric: data metrics, picture metrics, packet-based metrics, bitstream-based metrics or hybrid metrics; with full-reference, reduced-reference or no-reference.

It is a Linux application programmed in Python with the aim of promoting extensibility, and the election of the GStreamer framework for video processing is due to its broad support in this area. Video Tester covers [EvalVid](http://www.tkn.tu-berlin.de/research/evalvid/) features and adds further improvements in terms of usability, extensibility, codec support, support of transmission methods and reliability in case of losses.

Features
--------

* Codec support: H.263, H.264, MPEG-4 part 2, Theora.
* Implemented metrics:
 * QoS metrics: latency, delta, jitter, skew, bandwidth, packet loss rate, packet loss distribution.
 * Bitstream metrics: stream eye, reference stream eye, gop size, I-frame loss rate.
 * Video quality metrics: PSNR, SSIM, ITU-T G.1070, MOS (PSNR to MOS mapping from EvalVid), MIV (from EvalVid).

Publications
------------

If you use this framework for your research, we would appreciate if you could cite the following reference:

  Ucar, I.; Navarro-Ortiz, J.; Ameigeiras, P.; Lopez-Soler, J.M., **Video Tester — A multiple-metric framework for video quality assessment over IP networks**, *Broadband Multimedia Systems and Broadcasting (BMSB), 2012 IEEE International Symposium on*, pp.1-5, 27-29 June 2012, DOI: [10.1109/BMSB.2012.6264243](http://dx.doi.org/10.1109/BMSB.2012.6264243), [arXiv:1301.5793](http://arxiv.org/abs/1301.5793) **[cs.MM]**

Installation
------------

Video Tester has the following dependencies:

* Python 2.7.
* GStreamer (>=1.0) + plugins: base, good, ugly, bad, libav.
* GStreamer RTSP server (>=1.0).
* PyGObject (>=3.18.2).
* Pylibpcap (>=0.6.4).
* Numpy (>=1.4.1).
* OpenCV (>=2.1) with Python bindings.
* Matplotlib (>=1.0.1).
* WxPython (>=2.8.11) + Matplotlib backend.

If you are using **Fedora**, first of all, enable the [RPM Fusion](http://rpmfusion.org) repositories. Then, these dependencies can be installed with the following command:

	$ sudo dnf install gstreamer1 gstreamer1-libav gstreamer1-plugins-base gstreamer1-plugins-good gstreamer1-plugins-ugly gstreamer1-plugins-bad-free gstreamer-plugins-bad-freeworld gstreamer1-rtsp-server pygobject2 pylibpcap numpy python2-matplotlib python2-matplotlib-wx wxPython opencv-python

Now, you can download the latest version of Video Tester. Then, follow this steps:

	$ tar xf VideoTester-x.x.x.tar.gz
	$ cd VideoTester-x.x.x
	$ sudo python setup.py install

Basic Usage
-----

VT in server mode:

	$ VT server

VT in client mode:

	$ VT client

How to specify another configuration file (by default, Video Tester looks for a `VT.conf` file in the current working directory):

	$ VT -c path/to/another.conf [server|client]

VT in client mode with GUI:

	$ VT client -g

For more information, check the [documentation](http://enchufa2.github.io/video-tester/).
