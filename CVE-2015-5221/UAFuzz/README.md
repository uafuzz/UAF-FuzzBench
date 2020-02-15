- Reproduce: `valgrind ./jasper -f PoC -t mif -F /dev/null -T jpg`
~~~
==9860== Invalid read of size 4
==9860==    at 0x80826DD: jas_tvparser_destroy (jas_tvp.c:111)
==9860==    by 0x80782A1: mif_process_cmpt (mif_cod.c:587)
==9860==    by 0x8077F6D: mif_hdr_get (mif_cod.c:497)
==9860==    by 0x8077446: mif_decode (mif_cod.c:166)
==9860==    by 0x804AC8D: jas_image_decode (jas_image.c:372)
==9860==    by 0x8049620: main (jasper.c:229)
==9860==  Address 0x42d6b70 is 0 bytes inside a block of size 16 free'd
==9860==    at 0x402D358: free (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==9860==    by 0x80825A5: jas_free (jas_malloc.c:111)
==9860==    by 0x80826FE: jas_tvparser_destroy (jas_tvp.c:114)
==9860==    by 0x807823B: mif_process_cmpt (mif_cod.c:573)
==9860==    by 0x8077F6D: mif_hdr_get (mif_cod.c:497)
==9860==    by 0x8077446: mif_decode (mif_cod.c:166)
==9860==    by 0x804AC8D: jas_image_decode (jas_image.c:372)
==9860==    by 0x8049620: main (jasper.c:229)
==9860==  Block was alloc'd at
==9860==    at 0x402C17C: malloc (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==9860==    by 0x808258F: jas_malloc (jas_malloc.c:106)
==9860==    by 0x8082669: jas_tvparser_create (jas_tvp.c:96)
==9860==    by 0x807805C: mif_process_cmpt (mif_cod.c:536)
==9860==    by 0x8077F6D: mif_hdr_get (mif_cod.c:497)
==9860==    by 0x8077446: mif_decode (mif_cod.c:166)
==9860==    by 0x804AC8D: jas_image_decode (jas_image.c:372)
==9860==    by 0x8049620: main (jasper.c:229)
~~~
