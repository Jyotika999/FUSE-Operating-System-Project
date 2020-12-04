SSFS (Simple & Stupid Filesystem (Using FUSE))
=======================================
In this task, we have build a simple in-memory filesystem that supports the creating of new files and directories.

**Why building the filesystem in UserSpace?**
This is beacuse being in the user space is of great advantage, which could use any of the available libraries when we build our own filesystem in contrast of the kernel space which needs a deep understanding of the kernel that we are working with.

**Why building this filesystem?**
This is beacuse we can't actually build a native filesystem which can store the data directly to the disk, therefore, instead we need to use an already existing filesystem to do so.

**Requirements**
FUSE (Filesystem in Userspace)s an interface that let you write your own filesystem for Linux in the user space. Hence, to start working FUSE should be already installed in the linux box.

**What’s Our Example Filesystem Going To Do?**

Nothing special nor useful! it’s a read-only filesystem, there are two files on it; namely “file54” and “file349”. The user can open these files and read their contents. I’m going to call it Simple Stupid Filesystem (SSFS).



**All Reference from:**
http://maastaar.net/fuse/linux/filesystem/c/2016/05/21/writing-a-simple-filesystem-using-fuse/



