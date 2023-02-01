
# Get Started with Yocto

A summary of all things one might need to work with Yocto Project.



## Commands

All hints for CLIs like bitbake, bitbake-layers, devtool etc. used within common Yocto Project development


| Description | Commands |
| :-------- |:-----------|
| Populate Classic SDK | `bitbake -c populate_sdk <IMAGE_NAME>`|
| Start build from scratch | `cd $BUILD_DIR && rm -Rf tmp sstate-cache`|
| Supported HW Boards | `ls sources/meta-<hardware>*/recipes*/conf/machine/*.conf`|
| Find a package in a layer | `cd sources && find --name "*busybox*"`|
| Find a recipe in a layer | `cd sources && find --name "*busybox*.bb*"`|
| Create a new layer | `yocto-layer create <layer_name>`|
| Add custom layer | `bitbake-layers add-layer /path/to/your_meta-layer`|
| Remove custom layer | `bitbake-layers remove-layer /path/to/your_meta-layer`|
|Search recipe | `bitbake-layers show-recipes "gdb*"`|
| `devshell` | `bitbake -c devshell <target>`|
| List tasks for a recipe | `bitbake -c listtasks <target>`|
| Force a build| `bitbake -f <target>`|
| Force-run a specific task | `bitbake -c compile -f <target>`|
| Display debug information| `bitbake -DDD <target>`|

## Configuration

All variables that can be added to files like bblayers.conf or local.conf or other configuration files in Yocto.

| Description | Commands |
| :-------- |:-----------|
| Add systemd | `DISTRO_FEATURES_append = " systemd" && VIRTUAL-RUNTIME_init_manager = "systemd"`|
| Remove sysvinit | `DISTRO_FEATURES_BACKFILL_CONSIDERED = "sysvinit" && VIRTUAL-RUNTIME_initscripts = ""`|
| Add gcc | `EXTRA_IMAGE_FEATURES ?= "tools-sdk"`|
| Persistent Bitbake server | `BB_SERVER_TIMEOUT= "n" # n in seconds`|
| Download Directory | `DL_DIR ?= "${BSP_DIR}/downloads/"`|
|Configuring a Pre-mirror | `INHERIT += "own-mirrors" && SOURCE_MIRROR_URL = "http://example.com/source-mirror"`|
|Terminal for dev(py)shell | `OE_TERMINAL = screen"`|
|Add Real-Time Kernel  | `PREFERRED_PROVIDER_virtual/kernel = "<RT_Kernel_Image_name_from_Meta-Layer>"`|



	

# Documentation / Websites

http://layers.openembedded.org/layerindex/branch/master/layers/

https://docs.yoctoproject.org/

