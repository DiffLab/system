### mkinitcpio


#### 0001-Add-zstd-module-decompression.patch
***
This patch adds decompression of modules in .zstd format and you need to use [this](https://raw.githubusercontent.com/DiffLab/kernel/master/Makefile/0001-init-add-support-for-zstd-compressed-modules.patch) patch to use it. You probably use .xz compression by default so don't forget to change this when compiling the kernel. 
***
### 0002-Set-default-compressor-to-zstd.patch
***
Unlike the previous patch, this one does not require equally profound changes in the system and the use of subsequent solutions. It only changes the default compression option of initramfs from gzip to zstd.
***
