本プログラムは、オリジナル版「**TOYOSHIKI Tiny BASIC for Arduino**」のSRAM節約修正したバージョンです。  

固定データ（キーワード、エラーメッセージ、固定文字列）をフラッシュメモリに配置することにより、オリジナル版に比べてSRAMのグローバルメモリの消費を712バイト削減しました。  

以下コンパイル時の消費メモリに関するメッセージの内容です。  

**オリジナル**  

```
最大32256バイトのフラッシュメモリのうち、スケッチが7986バイト（24%）を使っています。
最大2048バイトのRAMのうち、グローバル変数が1481バイト（72%）を使っていて、ローカル変数で567バイト使うことができます
```

**修正版**  

```
最大32256バイトのフラッシュメモリのうち、スケッチが8120バイト（25%）を使っています。
最大2048バイトのRAMのうち、グローバル変数が769バイト（37%）を使っていて、ローカル変数で1279バイト使うことができます
```



オリジナル版配布サイト <https://github.com/vintagechips/ttbasic_arduino>  
関連情報 電脳伝説 Vintagechips - 豊四季タイニーBASIC確定版  



以下はオリジナル版のドキュメントです。  

------

﻿TOYOSHIKI Tiny BASIC for Arduino

The code tested in Arduino Uno R3.<br>
Use UART terminal, or temporarily use Arduino IDE serial monitor.

Operation example

&gt; list<br>
10 FOR I=2 TO -2 STEP -1; GOSUB 100; NEXT I<br>
20 STOP<br>
100 REM Subroutine<br>
110 PRINT ABS(I); RETURN

OK<br>
&gt;run<br>
2<br>
1<br>
0<br>
1<br>
2

OK<br>
&gt;

The grammar is the same as<br>
PALO ALTO TinyBASIC by Li-Chen Wang<br>
Except 3 point to show below.

(1)The contracted form of the description is invalid.

(2)Force abort key<br>
PALO ALTO TinyBASIC -> [Ctrl]+[C]<br>
TOYOSHIKI TinyBASIC -> [ESC]<br>
NOTE: Probably, there is no input means in serial monitor.

(3)Other some beyond my expectations.

(C)2012 Tetsuya Suzuki<br>
GNU General Public License
