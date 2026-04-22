# cisco-ucs

## UCS C210 M2
tbd
## UCS C240 M3
Firmware ISO: https://software.cisco.com/download/home/284296254/type/283850974/release/3.0(4s)
ucs-c240-huu-3.0.4s.iso
SHA512: b1a38e22cc328ad60c54c8148a9f1fbdd43ae8a4100a7c8f547350bb62c6718bb5dc04b669f135267a9d81e2cefe1e43e7445ae45a1e40a61423d3d1515ff9a4
MD5: ac49f94fbe61676c3fce300601c4777d

1.) use Rufus to copy ISO to thumbdrive using ISO, not DD.
2.) run "dir d:" (d = letter of thumbdrive) and note the serial number.
3.) edit D:\isolinux\isolinux.cfg and replace "CDLABEL=<PARTIAL NAME>" with "UUID=<FAT Serial #>" (source: https://community.cisco.com/t5/unified-computing-system-knowledge-base/cisco-standalone-c-series-host-update-utility-usb-image-utility/tac-p/4450170/highlight/true#M1196)
