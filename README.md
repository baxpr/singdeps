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


## ubuntu:18.04

Use `apt-get install -y`

* Workaround for filename case collision in linux-libc-dev  
  https://stackoverflow.com/questions/15599592/compiling-linux-kernel-error-xt-connmark-h  
  https://superuser.com/questions/1238903/cant-install-linux-libc-dev-in-ubuntu-on-windows  
  ```
  apt-get install -y binutils xz-utils 
  mkdir pkgtemp && cd pkgtemp
  apt-get download linux-libc-dev
  ar x linux-libc-dev*deb
  tar xJf data.tar.xz
  tar cJf data.tar.xz ./usr
  ar rcs linux-libc-dev*.deb debian-binary control.tar.xz data.tar.xz
  dpkg -i linux-libc-dev*.deb
  cd .. && rm -r pkgtemp
  ```

* Basics  
  __wget__ __unzip__ __zip__

* Freesurfer, Freeview  
  (h/t https://github.com/MPIB/singularity-fsl)  
  __python-minimal__ __libgomp1__ __ca-certificates__
  __libglu1-mesa__ __libgl1-mesa-glx__ __libsm6__ __libice6__ __libxt6__  
  __libjpeg-turbo8__ __libpng16-16__ __libxrender1__ __libxcursor1__
  __libxinerama1__ __libfreetype6__ __libxft2__ __libxrandr2__ __libmng2__  
  __libgtk2.0-0__ __libpulse0__ __libasound2__ __libcaca0__ __libopenblas-base__
  __bzip2__ __dc__ __bc__

* ImageMagick, convert, montage  
  __ghostscript__ __imagemagick__  
  Also fix imagemagick policy to allow PDF output (https://usn.ubuntu.com/3785-1/):  
  `sed -i 's/rights="none" pattern="PDF"/rights="read | write" pattern="PDF"/' /etc/ImageMagick-6/policy.xml`

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
  https://fsl.fmrib.ox.ac.uk/fsldownloads/fsl-6.0.0-centos7_64.tar.gz
  
* ImageMagick  
  __ImageMagick__
  
* Matlab  
  __java-1.8.0-openjdk__

* X, xvfb  
  __xorg-x11-server-Xvfb__ __xorg-x11-xauth__ __which__

