# Singularity dependencies
Dependency information for various tools/OS in singularity containers

## ubuntu 16.04

Use `apt-get install -y`

* ImageMagick/convert/montage: ghostscript imagemagick
* Fix imagemagick policy to allow PDF output. See https://usn.ubuntu.com/3785-1/
  `sed -i 's/rights="none" pattern="PDF"/rights="read | write" pattern="PDF"/' /etc/ImageMagick-6/policy.xml`
* Matlab: openjdk-8-jre
