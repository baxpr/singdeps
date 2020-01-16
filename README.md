# Singularity dependencies
Dependency information for various tools/OS in singularity containers

## ubuntu:16.04

Use `apt-get install -y`

* Basics  
  __wget__ __unzip__ __zip__

* ImageMagick, convert, montage  
  __ghostscript__ __imagemagick__  
  Also fix imagemagick policy to allow PDF output (https://usn.ubuntu.com/3785-1/):  
  `sed -i 's/rights="none" pattern="PDF"/rights="read | write" pattern="PDF"/' /etc/ImageMagick-6/policy.xml`

* Matlab  
  __openjdk-8-jre__

* X, xvfb  
  __xvfb__

## centos:7.5.1804

Use `yum -y install`

* Basics  
  __wget__ __unzip__ __zip__

* Freesurfer, Freeview  
  __bc__ __libgomp__ __libicu__ __mesa-dri-drivers__ __mesa-libGLU__ __perl__ __tcsh__

* FSL  
  __epel-release__ __openblas-devel__
  
* ImageMagick  
  __ImageMagick__
  
* Matlab  
  __java-1.8.0-openjdk__

* X, xvfb  
  __xorg-x11-server-Xvfb__ __xorg-x11-xauth__ __which__

