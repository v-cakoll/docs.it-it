---
title: Come convertire una matrice di byte in una guida per C# programmatori int
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
ms.openlocfilehash: a553d8778997a2323c54c72be8e68aff590a7c7d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635054"
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a>Come convertire una matrice di byte in un int (C# guida per programmatori)

Questo esempio mostra come usare la classe <xref:System.BitConverter> per convertire una matrice di byte in un valore [int](../../language-reference/builtin-types/integral-numeric-types.md) e di nuovo in una matrice di byte. Può essere necessario ad esempio convertire i byte in un tipo di dati predefinito dopo la lettura dei byte dalla rete. Oltre al metodo [ToInt32 (Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) nell'esempio, nella tabella seguente sono elencati i metodi della classe <xref:System.BitConverter> che convertono i byte (da una matrice di byte) ad altri tipi incorporati.

|Tipo restituito|Metodo|
|-------------------|------------|
|`bool`|[ToBoolean (byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))|
|`char`|[ToChar (byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))|
|`double`|[ToDouble (byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))|
|`short`|[ToInt16 (byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))|
|`int`|[ToInt32 (byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))|
|`long`|[ToInt64 (byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))|
|`float`|[ToSingle (byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))|
|`ushort`|[ToUInt16 (byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))|
|`uint`|[ToUInt32 (byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))|
|`ulong`|[ToUInt64 (byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))|

## <a name="example"></a>Esempio

Questo esempio Inizializza una matrice di byte, inverte la matrice se l'architettura del computer è Little-endian (ovvero il byte meno significativo viene archiviato per primo), quindi chiama il metodo [ToInt32 (byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) per convertire quattro byte nella matrice in un `int`. Il secondo argomento di [ToInt32 (Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifica l'indice iniziale della matrice di byte.

> [!NOTE]
> L'output può variare a seconda dell'aspetto dell'architettura del computer.

[!code-csharp[csProgGuideTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#22)]

## <a name="example"></a>Esempio

In questo esempio viene chiamato il metodo <xref:System.BitConverter.GetBytes%28System.Int32%29> della classe <xref:System.BitConverter> per convertire un valore `int` in una matrice di byte.

> [!NOTE]
> L'output può variare a seconda dell'aspetto dell'architettura del computer.

[!code-csharp[csProgGuideTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#23)]

## <a name="see-also"></a>Vedere anche

- <xref:System.BitConverter>
- <xref:System.BitConverter.IsLittleEndian>
- [Tipi](./index.md)
