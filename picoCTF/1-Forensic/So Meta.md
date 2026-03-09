### So Meta
### Descripcion
Find the flag in this [picture](https://challenge-files.picoctf.net/c_fickle_tempest/8e74516a5167183bf254f082a836fe7b925c25d6899feeffb68f78b1549a1224/pico_img.png).
### Solucion
```
┌──(kali㉿kali)-[~]
└─$ sudo apt install exiftool -y

[sudo] password for kali: 
Sorry, try again.
[sudo] password for kali: 
Note, selecting 'libimage-exiftool-perl' instead of 'exiftool'
libimage-exiftool-perl is already the newest version (13.50+dfsg-1).
libimage-exiftool-perl set to manually installed.
The following packages were automatically installed and are no longer required:
  curlftpfs                liblab-gamut1           libsphinxbase3t64
  libann0                  libmjpegutils-2.1-0t64  libswscale8
  libaudio2                libmpeg2encpp-2.1-0t64  libvdpau-va-gl1
  libavfilter10            libmplex2-2.1-0t64      pocketsphinx-en-us
  libavformat61            libmupdf25.1            python3-aiocache
  libcdt5                  libpocketsphinx3        python3-aiomcache
  libcgraph6               libpostproc58           python3-fs
  libconfig-inifiles-perl  librubberband2          python3-wapiti-arsenic
  libfuse2t64              libsimdutf27            python3-yaswfp
  libgav1-1                libsnmp40t64            ruby-unf-ext
Use 'sudo apt autoremove' to remove them.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 0
                                                                             
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/8e74516a5167183bf254f082a836fe7b925c25d6899feeffb68f78b1549a1224/pico_img.png
--2026-03-09 14:26:21--  https://challenge-files.picoctf.net/c_fickle_tempest/8e74516a5167183bf254f082a836fe7b925c25d6899feeffb68f78b1549a1224/pico_img.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.61, 3.161.44.103, 3.161.44.84, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png   0%       0  --.-KB/s  pico_img.png 100% 106.25K   304KB/s  pico_img.png 100% 106.25K   304KB/s    in 0.3s    

2026-03-09 14:26:22 (304 KB/s) - ‘pico_img.png’ saved [108795/108795]

                                     
┌──(kali㉿kali)-[~]
└─$ exiftool pico_img.png

ExifTool Version Number         : 13.50
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2025:11:21 14:10:56-05:00
File Access Date/Time           : 2026:03:09 14:26:22-04:00
File Inode Change Date/Time     : 2026:03:09 14:26:22-04:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : picoCTF{s0_m3ta_9a8b5aa1}
Image Size                      : 600x600
Megapixels                      : 0.360
```

picoCTF{s0_m3ta_9a8b5aa1}
### Notas
### Referencias