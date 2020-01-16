# Singularity dependencies
Dependency information for various tools/OS in singularity containers

## ubuntu:16.04

Use `apt-get install -y`

* Basics

  __wget__ __unzip__ __zip__ __xvfb__

* ImageMagick/convert/montage

  __ghostscript__ __imagemagick__

  Fix imagemagick policy to allow PDF output (https://usn.ubuntu.com/3785-1/):
 
  `sed -i 's/rights="none" pattern="PDF"/rights="read | write" pattern="PDF"/' /etc/ImageMagick-6/policy.xml`

* Matlab

  __openjdk-8-jre__


## centos:7.5.1804

Use `yum -y install`

* Freesurfer and Freeview

  __bc__ __libgomp__ __libicu__ __mesa-dri-drivers__ __mesa-libGLU__ __perl__ __tcsh__

