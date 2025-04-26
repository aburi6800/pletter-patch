
# Pletter unpacker for z88dk

original:  
https://github.com/nanochess/Pletter/tree/master  
Copyright (c) 2002-2003 Team Bomba  

z88dk patch:  
Copyright (C) 2025 aburi6800  

<br>

## Patch to asm source

Apply the patch to the original unpack.asm.  

```shell
patch unpack.asm unpack.patch
```

<br>

## Import compressed data

Compressed data is imported by including it in an asm file.  

Example:
```asm
SECTION rodata_user
PUBLIC _COMPDATA

_COMPDATA:
INCBIN "COMPDATA.BIN"
```

<br>

## Use from C

It can be run from the C source by including `unpack.h`.  

Example:
```C
#include "../include/unpack.h"

// Compless data
extern uint8_t COMPDATA[];

void main()
{
    unpack(COMPDATA, dist);
}
```

<br>

## Use from asembller

See the original documentation for information on how to call from the assembler.  
