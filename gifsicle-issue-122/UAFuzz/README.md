- Reproduce: `valgrind ./gifsicle PoC test.gif -o /dev/null`
~~~
==8590== Invalid free() / delete / delete[] / realloc()
==8590==    at 0x402D358: free (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==8590==    by 0x804F096: Gif_DeleteImage (giffunc.c:529)
==8590==    by 0x804EF69: Gif_DeleteStream (giffunc.c:502)
==8590==    by 0x80644DF: blank_frameset (support.c:1741)
==8590==    by 0x806DF71: main (gifsicle.c:2180)
==8590==  Address 0x4295e40 is 0 bytes inside a block of size 207 free'd
==8590==    at 0x402D358: free (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==8590==    by 0x8051CDA: read_gif (gifread.c:898)
==8590==    by 0x8051E22: Gif_FullReadFile (gifread.c:929)
==8590==    by 0x806A9C8: input_stream (gifsicle.c:735)
==8590==    by 0x806DE54: main (gifsicle.c:2144)
==8590==  Block was alloc'd at
==8590==    at 0x402C17C: malloc (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==8590==    by 0x402E370: realloc (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==8590==    by 0x804DE45: Gif_Realloc (fmalloc.c:19)
==8590==    by 0x8051247: suck_data (gifread.c:671)
==8590==    by 0x8051B45: read_gif (gifread.c:853)
==8590==    by 0x8051E22: Gif_FullReadFile (gifread.c:929)
==8590==    by 0x806A9C8: input_stream (gifsicle.c:735)
==8590==    by 0x806DE54: main (gifsicle.c:2144)
~~~
