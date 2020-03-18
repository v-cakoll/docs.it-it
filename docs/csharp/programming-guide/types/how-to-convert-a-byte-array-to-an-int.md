---
title: Come convertire una matrice di byte in un int - Guida per programmatori C
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
ms.openlocfilehash: 9f477649dba1b42d7a10d521c010977707daf3ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75698755"
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a>Come convertire una matrice di byte in un int (Guida per programmatori C

Questo esempio mostra come usare la classe <xref:System.BitConverter> per convertire una matrice di byte in un valore [int](../../language-reference/builtin-types/integral-numeric-types.md) e di nuovo in una matrice di byte. Può essere necessario ad esempio convertire i byte in un tipo di dati predefinito dopo la lettura dei byte dalla rete. Oltre al metodo [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) nell'esempio, nella <xref:System.BitConverter> tabella seguente sono elencati i metodi della classe che convertono i byte (da una matrice di byte) in altri tipi incorporati.

|Tipo restituito|Metodo|
|-------------------|------------|
|`bool`|[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))|
|`char`|[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))|
|`double`|[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))|
|`short`|[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))|
|`int`|[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))|
|`long`|[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))|
|`float`|[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))|
|`ushort`|[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))|
|`uint`|[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))|
|`ulong`|[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))|

## <a name="example"></a>Esempio

In questo esempio viene inizializzata una matrice di byte, viene invertita la matrice se l'architettura del computer è little-endian, ovvero il byte meno significativo viene `int`archiviato per primo, quindi viene chiamato il metodo [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) per convertire quattro byte nella matrice in un oggetto . Il secondo argomento [di ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifica l'indice iniziale della matrice di byte.

> [!NOTE]
> L'output può variare a seconda dell'endianness dell'architettura del computer.

[!code-csharp[csProgGuideTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#22)]

## <a name="example"></a>Esempio

In questo esempio viene chiamato il metodo <xref:System.BitConverter.GetBytes%28System.Int32%29> della classe <xref:System.BitConverter> per convertire un valore `int` in una matrice di byte.

> [!NOTE]
> L'output può variare a seconda dell'endianness dell'architettura del computer.

[!code-csharp[csProgGuideTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#23)]

## <a name="see-also"></a>Vedere anche

- <xref:System.BitConverter>
- <xref:System.BitConverter.IsLittleEndian>
- [Tipi](./index.md)
