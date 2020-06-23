---
title: Marshalling dei dati con platform invoke
description: Eseguire il marshalling dei dati con platform invoke in .NET. Vedere un elenco di tipi di dati usati nelle API Windows e funzioni di tipo C e trovare gli equivalenti di tipo gestito .NET.
ms.date: 03/20/2019
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
ms.openlocfilehash: 27045790780c1eef9537bdf7e52deb579e2b467c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904104"
---
# <a name="marshaling-data-with-platform-invoke"></a>Marshalling dei dati con platform invoke

Per chiamare le funzioni esportate da una libreria non gestita, un'applicazione .NET Framework richiede un prototipo di funzione nel codice gestito che rappresenta la funzione non gestita. Per creare un prototipo che abiliti PInvoke per effettuare il marshalling dei dati in modo corretto, è necessario eseguire le operazioni seguenti:

- Applicare l'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> alla funzione o al metodo statico nel codice gestito.

- Sostituire i tipi di dati non gestiti con tipi di dati gestiti.

È possibile usare la documentazione fornita con una funzione non gestita per costruire un prototipo gestito equivalente, applicando l'attributo con i relativi campi facoltativi e sostituendo i tipi di dati non gestiti con quelli gestiti. Per istruzioni su come applicare l'attributo <xref:System.Runtime.InteropServices.DllImportAttribute>, vedere [Utilizzo di funzioni DLL non gestite](consuming-unmanaged-dll-functions.md).

Questa sezione fornisce esempi che dimostrano come creare prototipi di funzioni gestite per passare argomenti e ricevere valori restituiti da funzioni esportate mediante librerie non gestite. Gli esempi illustrano anche l'uso dell'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> e della classe <xref:System.Runtime.InteropServices.Marshal> per effettuare il marshalling esplicito dei dati.

## <a name="platform-invoke-data-types"></a>Tipi di dati PInvoke

La tabella seguente include un elenco di tipi di dati usati nelle API Windows e nelle funzioni di tipo C. Molte librerie non gestite contengono funzioni che passano questi tipi di dati come parametri e valori restituiti. La terza colonna indica il tipo di valore o la classe incorporata corrispondente di .NET Framework che si usa nel codice gestito. In alcuni casi, è possibile sostituire il tipo elencato nella tabella con un tipo delle stesse dimensioni.

|Tipo non gestito nelle API Windows|Tipo non gestito del linguaggio C|Tipo gestito|Descrizione|
|--------------------------------|-------------------------------|------------------------|-----------------|
|`VOID`|`void`|<xref:System.Void?displayProperty=nameWithType>|Applicato a una funzione che non restituisce un valore.|
|`HANDLE`|`void *`|<xref:System.IntPtr?displayProperty=nameWithType> o <xref:System.UIntPtr?displayProperty=nameWithType>|32 bit nei sistemi operativi Windows a 32 bit, 64 bit nei sistemi operativi Windows a 64 bit.|
|`BYTE`|`unsigned char`|<xref:System.Byte?displayProperty=nameWithType>|8 bit|
|`SHORT`|`short`|<xref:System.Int16?displayProperty=nameWithType>|16 bit|
|`WORD`|`unsigned short`|<xref:System.UInt16?displayProperty=nameWithType>|16 bit|
|`INT`|`int`|<xref:System.Int32?displayProperty=nameWithType>|32 bit|
|`UINT`|`unsigned int`|<xref:System.UInt32?displayProperty=nameWithType>|32 bit|
|`LONG`|`long`|<xref:System.Int32?displayProperty=nameWithType>|32 bit|
|`BOOL`|`long`|<xref:System.Boolean?displayProperty=nameWithType> o <xref:System.Int32?displayProperty=nameWithType>|32 bit|
|`DWORD`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|32 bit|
|`ULONG`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|32 bit|
|`CHAR`|`char`|<xref:System.Char?displayProperty=nameWithType>|Decorare con ANSI.|
|`WCHAR`|`wchar_t`|<xref:System.Char?displayProperty=nameWithType>|Decorare con Unicode.|
|`LPSTR`|`char *`|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorare con ANSI.|
|`LPCSTR`|`const char *`|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorare con ANSI.|
|`LPWSTR`|`wchar_t *`|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorare con Unicode.|
|`LPCWSTR`|`const wchar_t *`|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorare con Unicode.|
|`FLOAT`|`float`|<xref:System.Single?displayProperty=nameWithType>|32 bit|
|`DOUBLE`|`double`|<xref:System.Double?displayProperty=nameWithType>|64 bit|

Per i tipi corrispondenti in Visual Basic, C# e C++, vedere [Introduction to the .NET Framework Class Library](../../standard/class-library-overview.md#system-namespace) (Introduzione alla libreria di classi .NET Framework).

## <a name="pinvokelibdll"></a>PinvokeLib.dll

Il codice seguente definisce le funzioni della libreria fornite da Pinvoke.dll. Molti esempi descritti in questa sezione chiamano questa libreria.

### <a name="example"></a>Esempio

[!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]

[!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]
