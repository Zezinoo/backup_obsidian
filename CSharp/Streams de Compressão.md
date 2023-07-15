---
tags:
  - Csharp
---
Write no stream para comprimir , read para descomprimir
```cs
System.Io.Compression
```
Utilizamos com decorator
```cs
using (Stream s ...)
using (Stream ds = new DeflateStream(s, CompressionMode,Compress))
	for (byte i = 0, i < 100 , 1++)
		ds.WriteByte(i);
```
[[Stream Adapters]]]
# Memory Stream
Mesmas funcionalidades da stream , mas sem usar arquivos, guarda as coisas em memória.