LSYFS (Less Simple,Yet Stupid Filesystem (Using FUSE))
=======================================
In this task, we have build a simple in-memory filesystem that supports the creating of new files and directories.

**Why building the filesystem in UserSpace?**
This is beacuse being in the user space is of great advantage, which could use any of the available libraries when we build our own filesystem in contrast of the kernel space which needs a deep understanding of the kernel that we are working with.

**Why building this filesystem?**
This is beacuse we can't actually build a native filesystem which can store the data directly to the disk, therefore, instead we need to use an already existing filesystem to do so.

**Requirements**
FUSE (Filesystem in Userspace)s an interface that let you write your own filesystem for Linux in the user space. Hence, to start working FUSE should be already installed in the linux box.

**What “Less Simple, Yet Stupid Filesystem (LSYSFS)” will be able to do?**
* Create new directories by implementing the function do_mkdir for the event mkdir and introducing a simple array to maintain the list of directories created by the user.

* Create new files by implementing the function do_mknod for the event mknod and introducing a simple array to maintain the list of files created by the user.

* Write to files by implementing the function do_write for the event write and introducing a simple array to maintain the contents of the files.

**Compiling & Mounting The Filesystem**
We have used GCC to compile LSYSFS using:         
----------------------------------------------------------------------------------------
gcc lsysfs.c -o lsysfs `pkg-config fuse --cflags --libs`
----------------------------------------------------------------------------------------
For the above command on the Terminal,The “pkg-config” part is going to provide the compiler the proper arguments to include “fuse” library.Now, we can mount our file system after compilation using:
---------------------------------------------------------------------------------------
./lsysfs -f [mount point]
---------------------------------------------------------------------------------------


**Demo**
-------------------------------------------------------------------------
Using the make command first to compile the Makefile.


------------------------------------------------------------------------
Then change directory to Parent Directory , then create a new directory with some name, I have named it as 'MOUNT_POINT' . Also try to come inside the directory MOUNT_DIRECTORY and using 'ls' command you will notice that it will be all empty.


-------------------------------------------------------------------------
Now to implement LSYSFS, make a new directory, I named it as 'dir0' and again it will be an empty directory which you can check by 'ls' command within the directory.
-------------------------------------------------------------------------
Similarly, for the 'MOUNT_POINT' Directory, create a new directory and for this directory i named it as 'dir1' which will again be an empty directory which you can check by 'ls' command within that.

-------------------------------------------------------------------------
Now, for creating a file within the Directory'MOUNT_POINT', we will make use of 'echo' command within a file name 'file'
and access the components of the 'file' using 'less file' command.
-----------------------------------------------------------------------

Now, we can manually check that The 'MOUNT_FOLDER' have dir0, dir1 and file . also the file contents can be seen same as that we wrote using 'echo' command.






**All Reference from:**
http://maastaar.net/fuse/linux/filesystem/c/2019/09/28/writing-less-simple-yet-stupid-filesystem-using-FUSE-in-C/




