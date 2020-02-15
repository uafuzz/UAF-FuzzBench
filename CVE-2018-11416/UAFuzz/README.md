- Reproduce: `valgrind ./jpegoptim PoC`
~~~
==4992== Invalid free() / delete / delete[] / realloc()
==4992==    at 0x402D358: free (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==4992==    by 0x804BC09: main (jpegoptim.c:899)
==4992==  Address 0x4995cf8 is 0 bytes inside a block of size 39,485 free'd
==4992==    at 0x402E2CC: realloc (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==4992==    by 0x804BCD1: jpeg_memory_empty_output_buffer (jpegdest.c:59)
==4992==    by 0x40C7610: ??? (in /usr/lib/i386-linux-gnu/libjpeg.so.8.0.2)
==4992==    by 0x40BBDEC: jpeg_write_marker (in /usr/lib/i386-linux-gnu/libjpeg.so.8.0.2)
==4992==    by 0x8049936: write_markers (jpegoptim.c:286)
==4992==    by 0x804B023: main (jpegoptim.c:732)
==4992==  Block was alloc'd at
==4992==    at 0x402C17C: malloc (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==4992==    by 0x804AE08: main (jpegoptim.c:681)
~~~
