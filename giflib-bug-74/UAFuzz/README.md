- Reproduce: `valgrind ./gifsponge < PoC`
~~~
==2409== Invalid read of size 4
==2409==    at 0x804BEAB: EGifCloseFile (egif_lib.c:764)
==2409==    by 0x80489B1: main (gifsponge.c:77)
==2409==  Address 0x4237d10 is 72 bytes inside a block of size 76 free'd
==2409==    at 0x402D358: free (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==2409==    by 0x804BFDD: EGifCloseFile (egif_lib.c:802)
==2409==    by 0x804C96C: EGifSpew (egif_lib.c:1144)
==2409==    by 0x8048964: main (gifsponge.c:72)
==2409==  Block was alloc'd at
==2409==    at 0x402C17C: malloc (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==2409==    by 0x804AE31: EGifOpenFileHandle (egif_lib.c:92)
==2409==    by 0x80488A4: main (gifsponge.c:44)
~~~
