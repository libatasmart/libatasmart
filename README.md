# ATA S.M.A.R.T. reading and parsing library

[![Build](https://github.com/libatasmart/libatasmart/actions/workflows/build.yml/badge.svg)](https://github.com/alibatasmart/libatasmart/actions/workflows/build.yml)
[![CodeQL](https://github.com/libatasmart/libatasmart/actions/workflows/codeql.yml/badge.svg)](https://github.com/libatasmart/libatasmart/actions/workflows/codeql.yml)

As the name suggests libatasmart only does ATA S.M.A.R.T., there is no support for SCSI harddisks.
SCSI S.M.A.R.T. is a very different system, support for it should be implemented in a separate library "libscsismart" if there should ever be demand for it.

This library is supposed to be lean and small and thus supports only a subset of the S.M.A.R.T. functionality.
If you need full control over all S.M.A.R.T. functionality of your hardware please refer to Buce Allen's smartmontools.

This runs on Linux only. Patches to port it to other operating systems are welcome.

Libatasmart supports classic ATA/IDE disks (i.e. /dev/hda) as well as ATA disks that are connected through a SCSI layer (SAT) (such as a SATA /dev/sda).
USB disks generally don't support SAT and thus generally cannot be queried for S.M.A.R.T. data.

The code is licensed under LGPLv2.1+.

## Acknowledgments

This library is inspired by Bruce Allen's smartmontools and by Emmanuel Varagnat's hddtemp. However libatasmart is completely new code, not a single line has been copied from those two projects.
The original author of this code is Lennart Poettering.
