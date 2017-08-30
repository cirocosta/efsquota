```

  sys_write(fd, buf, size)

  =>  touches `vfs` interface in the kernel

      =>  with a probe on `VFS` the first
          write on that subdirectory triggers
          accounting for that session.

      =>  once accounting has been initiated,
          each `write` has its `size` captured
          and added to the map shared with
          userspace.

      =>  limitting is enforced when the sum gets
          bigger than the desired.

```
