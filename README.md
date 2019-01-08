
# buildenv-omr

## Makefile Usage
```
Usage:
	FLAGS:
		TARGET_ARCH="target architecture"      (default: x86_64)
			allows you to change the target architecture to build to 

		OWNER="docker repo"                    (default: omr_builder)
			to change the repo the docker images are built to 

		UBUNTU_V="ubuntu version number"       (default: 16.04)
			to change the repo the docker images are built to 

		GCC_V="gcc version number"             (default: 4.9) 
			to change the gcc version, might break so, thread carefully

		OMRDIR="ubuntu version number"         (default: /workspace/omr) 
			to change the location of the omr root directory 

		BUILD_ROOT_DIR="/path/to/base/build"   (default: build)
			to change the base directory to store all the builds (cross, native etc..) 

		CROSS_BUILD="/path/to/cross/build"     (default: build/cross_build) 
			to change the directory to store the cross compiled build 

		NATIVE_BUILD="/path/to/native/build"   (default: build/native_build) 
			to change the directory to store the native compiled build 


	CMD:
		build	
			build the omr binaries based on the flags

		[x86_64 arm aarch64 i386 ppc64le s390x]	
			To build one of the diplayed Docker container for this architecture

		all	
			To build all the docker architecture

		clean 
			delete everything in here and do a make fresh

		fresh 
			delete built binaries in build
```
## buildOMR.sh wrapper Usage

NB. it is recommended you use the make file since it wraps all the script needs in one tidy package
```

Usage:
    ./buildOMR.sh [cmake extra args] ... 
    Necessary Variables:
        SOURCE="path/to/omr/source
        DEST="path/to/omr/build/directory"

    To cross compile set 
        TOOLCHAIN="path/to/toolchain"
        TARGET_ARCH="arch"

        N.B when cross compiling we build the native architecture depency @ ${DEST}/../cross_build_dependency
```
## Other

