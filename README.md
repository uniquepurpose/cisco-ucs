# cisco-ucs
A terrible journey to get these old servers up to date.

## UCS C210 M2
Firmware ISO: https://software.cisco.com/download/home/283862069/type/283850974/release/1.4(3z09)
ucs-c200-huu-1.4.3z09.iso
SHA512: bdf57175a4a844a9c27ccd70d640ca7da364ea2d736e0e22757db129a286107b0a7970f812e203f2e1e74bbff215649766d3f038a1b8cb6274ca55350a6916aa
MD5: d915919c73dba0c3e2955b7a646381e8

1.) use Rufus to copy ISO to thumbdrive using DD.
2.) boot from thumbdrive, enter "linux" on GRUB.
3.) if you can accept the EULA with "y" on your keyboard: be happy. if you can't: continue.

KVM:
1.) setup a windows 7, install Java JRE 1.6.0 (140_8)-
2.) Install Flash 32 and notice, that this won't help.
3.) connect with SSH: ssh -oKexAlgorithms=+diffie-hellman-group1-sha1 -oHostKeyAlgorithms=+ssh-rsa admin@[IP of CIMC]
4.) these commands:
scope kvm
set enabled yes
top
scope ipmi
set enables yes
top
scope sol
set enabled yes
top
commit

5.) go to https://github.com/Kris-Sekula/UCS-KVM and follow instructions to run the KVM java application.

## UCS C240 M3
Firmware ISO: https://software.cisco.com/download/home/284296254/type/283850974/release/3.0(4s)
ucs-c240-huu-3.0.4s.iso
SHA512: b1a38e22cc328ad60c54c8148a9f1fbdd43ae8a4100a7c8f547350bb62c6718bb5dc04b669f135267a9d81e2cefe1e43e7445ae45a1e40a61423d3d1515ff9a4
MD5: ac49f94fbe61676c3fce300601c4777d

Couldn't get to run the KVM java application using the above tricks.

1.) use Rufus to copy ISO to thumbdrive using ISO, not DD.
2.) run "dir d:" (d = letter of thumbdrive) and note the serial number.
3.) edit D:\isolinux\isolinux.cfg and replace "CDLABEL=<PARTIAL NAME>" with "UUID=<FAT Serial #>" (source: https://community.cisco.com/t5/unified-computing-system-knowledge-base/cisco-standalone-c-series-host-update-utility-usb-image-utility/tac-p/4450170/highlight/true#M1196)
