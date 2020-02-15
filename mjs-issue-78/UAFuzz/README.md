- Reproduce: `valgrind ./mjs -f PoC`
~~~
==5273== Invalid read of size 1
==5273==    at 0x804A9F9: skip_whitespaces (mjs.c:5790)
==5273==    by 0x804AA19: cur (mjs.c:5794)
==5273==    by 0x804B4F4: parse_array (mjs.c:5938)
==5273==    by 0x804B810: parse_value (mjs.c:5976)
==5273==    by 0x804BCE0: doit (mjs.c:6058)
==5273==    by 0x804CF8E: json_walk (mjs.c:6434)
==5273==    by 0x805AE11: mjs_json_parse (mjs.c:11963)
==5273==    by 0x805B018: mjs_op_json_parse (mjs.c:12012)
==5273==    by 0x8055E16: mjs_execute (mjs.c:9541)
==5273==    by 0x8056726: mjs_exec_internal (mjs.c:9758)
==5273==    by 0x8056813: mjs_exec_file (mjs.c:9781)
==5273==    by 0x805B1FC: main (mjs.c:12051)
==5273==  Address 0x42256db is 155 bytes inside a block of size 902 free'd
==5273==    at 0x402E2CC: realloc (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==5273==    by 0x80492D2: mbuf_resize (mjs.c:4924)
==5273==    by 0x8061183: mjs_mk_string (mjs.c:13706)
==5273==    by 0x805AA9F: frozen_cb (mjs.c:11870)
==5273==    by 0x804AF55: parse_string (mjs.c:5884)
==5273==    by 0x804B7CA: parse_value (mjs.c:5970)
==5273==    by 0x804B4C3: parse_array (mjs.c:5936)
==5273==    by 0x804B810: parse_value (mjs.c:5976)
==5273==    by 0x804BCE0: doit (mjs.c:6058)
==5273==    by 0x804CF8E: json_walk (mjs.c:6434)
==5273==    by 0x805AE11: mjs_json_parse (mjs.c:11963)
==5273==    by 0x805B018: mjs_op_json_parse (mjs.c:12012)
==5273==  Block was alloc'd at
==5273==    at 0x402E2CC: realloc (in /usr/lib/valgrind/vgpreload_memcheck-x86-linux.so)
==5273==    by 0x80492D2: mbuf_resize (mjs.c:4924)
==5273==    by 0x8061183: mjs_mk_string (mjs.c:13706)
==5273==    by 0x805584B: mjs_execute (mjs.c:9418)
==5273==    by 0x8056726: mjs_exec_internal (mjs.c:9758)
==5273==    by 0x8056813: mjs_exec_file (mjs.c:9781)
==5273==    by 0x805B1FC: main (mjs.c:12051)
~~~

