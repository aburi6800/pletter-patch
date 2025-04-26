[ [English](README.md) | [日本語](README.ja.md) ]

---

# Pletter unpacker for z88dk

オリジナル:  
https://github.com/nanochess/Pletter/tree/master  
Copyright (c) 2002-2003 Team Bomba  

z88dk用パッチ:  
Copyright (C) 2025 aburi6800  

<br>

## .asmソースへのパッチ

元のunpack.asmにパッチを適用します。  

例：
```shell
patch unpack.asm unpack.patch
```

<br>

## 圧縮データのインポート

圧縮されたデータは、次のようにして.asmファイルにインポートします。  

例：
```asm
SECTION rodata_user
PUBLIC _COMPDATA

_COMPDATA:
INCBIN "COMPDATA.BIN"
```

<br>

## Cプログラムからの使用方法

`unpack.h`をインクルードして使用します。  

例:
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

## アセンブラプログラムからの使用方法

アセンブラプログラムからの呼び出し方については、オリジナルのドキュメントを参照。  
