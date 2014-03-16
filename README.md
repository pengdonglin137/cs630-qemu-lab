# CS630 on Qemu(a virtual machine) in Ubuntu

- Author: Wu Zhangjin/Falcon <wuzhangjin@gmail.com> of [TinyLab.org](http://tinylab.org)
- Update: 2008-09-16, 2014/03/16

## Prepare

If want to do the following exercises, PLEASE install
[Qemu](http://wiki.qemu.org/Main_Page) and some other related tools in
Ubuntu/Linux system.

```
$ sudo apt-get install qemu
```

If want to do the exercises of
[CS630](http://www.cs.usfca.edu/~cruse/cs630f06/) on Qemu in Ubuntu, you need
to execute the following command to mirror the resources in the course site to
res/:

```
$ make update
```

## Usage

### "real mode" exercise

- helloworld

```
$ ./configure src/helloworld.s
$ make
$ make boot
```

- rtc

$ ./configure src/rtc.s
$ make
$ make boot

### "protected mode" exercise

- helloworld

```
$ ./configure src/pmhello.s
$ make
$ make pmboot
```

- rtc

```
$ ./configure src/pmrtc.s
$ make
$ make pmboot
```

## NOTE

In fact, some exercise not about "protected mode" also need to use the
2nd method to compile, for they begin execution with CS:IP = 1000:0002, and
need a "bootloader" to load them, or their SIZE are more than 512 bytes, can
not be put in the first 512bytes of the disk(MBR).

See more notes from NOTE.md.
