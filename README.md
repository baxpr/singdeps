# Singularity dependencies
Dependency information for various tools/OS in singularity containers

## ubuntu 16.04

Use `apt-get install -y`

* ImageMagick/convert/montage: __ghostscript__ __imagemagick__

  Fix imagemagick policy to allow PDF output. See https://usn.ubuntu.com/3785-1/
 
  `sed -i 's/rights="none" pattern="PDF"/rights="read | write" pattern="PDF"/' /etc/ImageMagick-6/policy.xml`

* Matlab: __openjdk-8-jre__
