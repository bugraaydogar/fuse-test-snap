
# Simple FuseFS Snap

This is a simple fusefs application created for testing purpose.
The source code has been taken from the following link
https://github.com/libfuse/libfuse/blob/master/example/hello.c

## Build and Install

    ```
    $ snapcraft --use-lxd
    $ sudo snap install fuse-test-snap_0.1_amd64.snap --dangerous
    ```

## Connect Interface

    ```
    $ sudo snap connect fuse-test-snap:fuse-support :fuse-support
    ```

## Run

Dive into the snap environment and start the application

    ```
    $ sudo snap run --shell fuse-test-snap.fuse-test
    $ cd $SNAP
    $ ./main -f $SNAP_COMMON
    ```

Stop it with Ctrl+C and you will have the following error.

    ```
    $ fuse: failed to unmount /var/snap/fuse-test-snap/common: Operation not permitted
    ```

Dmesg has the following error message;

    ```
    $ audit: type=1326 audit(1658834457.974:4715): auid=1000 uid=0 gid=0 ses=5 subj=? pid=469555 comm="main" exe="/snap/fuse-test-snap/x1/main" sig=0 arch=c000003e syscall=166 compat=0 ip=0x7f4229ef416b code=0x50000
    ```


