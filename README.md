An example program, using mprotect call to change rights on memory, writes some opcodes and launches them.  
  
void* mapWritableMemory(int length, void** deleteptr)  
Method creates about 8192 + length bytes memory, changes access rights to +rwx on length of them.  
Arguments:  
* length - count bytes to prepare  
* deleteptr - pointer to voidptr, receives address of the whole mapped memory area (not only executable area) or NULL on error  
Return value:  
* address of the first of length bytes of executable memory or NULL on error  
  
Mapped memory must be free()-d by hand, using deleteptr, not return value!  
  
It was a very interesting theme for me, but I didn't find anything like that, so I had to do that by hands.  
Daniel Rempel <danil.rempel@gmail.com>, 2014.
