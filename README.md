# QDK

The project is a fork of https://github.com/qnap-dev/QDK

From v 2.3.0 onwards, the original QDK removed the requirement check for Optware packages. This fork re-introduces the requirement check for Optware packages and installs any missing Optware 
packages via opkg as prior versions of the QDK did. Optware is no longer support by QNAP, but Entware fills the gap. Since Entware provides the packages via opkg as well, is works fine with the 
version of the QDK.

# Original QDK Download Link:

https://download.qnap.com/QPKG/QDK/QDK_2.3.2.zip


# QPKG Development Guidelines
----------------------------------

# Description

QDK is used to build QPKG files/applications for QNAP Turbo NAS. A QPKG file makes it easy for anyone to install and remove packages. It also gives a package maintainer almost total control on how the package is installed on the NAS.
The major design goal of QDK is to make it easy for the package maintainer to create simple QPKG files and at the same time also support more advanced packages. QDK started out as a simple modification of the first official release of the QPKG SDK, but now supersedes it. It includes many new features like architecture check at installation, support for digital signatures, different compression algorithms, a comprehensive option to check that other required QPKG packages are installed (or that conflicting packages are not installed), and a powerful build script.
#### From QTS 4.2.0 on, no support of Optware.

# License

QDK is distributed under the GPL making it completely open and available for anyone to use.

# Installation

Download and install the QPKG file and it will automatically create the system-wide configuration file, /etc/config/qdk.conf, and when enabled it also creates a symlink for qbuild in /usr/bin. The reference manual is included in a separate zip file. There is also a document (QDK Cookbook) with solutions to different common situations that you could run into when using QDK to build QPKG packages.

# How to add icons in QPKG
Location of directory with icons for the packaged software. Default location is a directory named icons in $QDK_ROOT_DIR. 
The value must be a full path or a path relative to $QDK_ROOT_DIR. The icons shall be named ${QPKG_NAME}.gif, ${QPKG_NAME}_80.gif, and ${QPKG_NAME}_gray.gif.

* ${QPKG_NAME}.gif is the image displayed in the web interface when the QPKG is enabled. It should be a GIF image of 64x64 pixels.

* ${QPKG_NAME}_gray.gif is the image displayed in the web interface when the QPKG is disabled. It should be a GIF image of 64x64 pixels. It is usually a greyscale version of the ${QPKG_NAME}.gif image, but that is not a requirement.

* ${QPKG_NAME}_80.gif is the image displayed in the pop-up dialog (with information about the QPKG and the buttons to enable, disable, and remove). It should be a GIF image of 80x80 pixels. If no icons are included then the QPKG is given default icons at installation.


# How to create QPKG in docker 
  
https://github.com/fcwu/docker-qdk2

# How to install QDK in Ubuntu

sudo ./InstallToUbuntu.sh install

# QDK Quick Start Guide

https://www.gitbook.com/book/edhongcy/qdk-quick-start-guide/details

# Update new feature

2.3.2

        -Support Ubuntu.
        -Fixed notification log.

2.3.1

        -Change Notification level.

2.3.0

        -Support Notification Center.
        -Modify the info log error log and warning log description.

2.2.16

        -Add new platform arm_64.

2.2.15
	
	-Add "export QNAP_QPKG" in sample start script. It is for Resource Monitor to monitor the folk process.
	-Add qbuild create md5sum file.
	-Support png format.
	-Change install log order.
	

2.2.14

	-Add QNAP display name in qpkg.cfg.(The QPKG name displayed on QTS Web UI)
	-Add support maxmum QTS version limitation.
	-Fix template sample code bug.

2.2.13

	-Add QTS HTTP Proxy and set Proxy_Path function in qpkg.cfg.
	-Add Timeout (in seconds) for QPKG Enable (first integer) and Timeout for QPKG Disable function in qpkg.cfg. (second integer) (since 4.1.0)
	-Add Visible setting for If the QPKG has web UI, show this QPKG on the Main menu function in qpkg.cfg.

2.2.12
	
	-Add QTS system main volume mount check.

2.2.11

	-Modify install succeeded system logs. 

2.2.10

	-Add installation log to system logs.

2.2.9

	-Support volume select(This function work on minimum QTS 4.2.1)

2.2.8

	-Add to support minimum QTS version limitation.
	-Add QTS apache root path.

2.2.7

	-Command qbuild could use build bumber

2.2.6

	-Enhance recognition of different platforms


2.2.4

	-New platform - support arm_x31, ce53xx(TS-269H) and arm_x41(TS-x31+,TAS-x68) architecture string.
	-New option - “Web_SSL_Port” that can access Web via SSL port.
	-Bug fix: support extract QPKG that builded by previous QDK.
	-Add QPKG_DESKTOP_APP="1" option.
