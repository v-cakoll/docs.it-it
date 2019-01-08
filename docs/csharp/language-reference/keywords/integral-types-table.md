---
title: Tabella dei tipi integrali - Riferimenti per C#
ms.custom: seodec18
description: Panoramica dei tipi integrali C# incorporati
ms.date: 08/20/2018
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
ms.openlocfilehash: 7f8e4a9dabb3e24293ae7fcc724e8787dd6d4cf5
ms.sourcegitcommit: 49af435bfdd41faf26d38c20c5b0cc07e87bea60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2018
ms.locfileid: "53396786"
---
# <a name="integral-types-table-c-reference"></a>Tabella dei tipi integrali (Riferimenti per C#)

La tabella seguente elenca le dimensioni e gli intervalli dei tipi integrali, che costituiscono un sottoinsieme dei tipi semplici.  
  
|Tipo|Intervallo|Dimensione|  
|----------|-----------|----------|  
|[sbyte](sbyte.md)|Da -128 a 127|Valore intero con segno a 8 bit|  
|[byte](byte.md)|Da 0 a 255|Intero senza segno a 8 bit|  
|[char](char.md)|Da U+0000 a U+ffff|Carattere Unicode a 16 bit|  
|[short](short.md)|Da –32,768 a 32,767|Valore intero a 16 bit con segno|  
|[ushort](ushort.md)|Da 0 a 65.535|Intero senza segno a 16 bit|  
|[int](int.md)|da -2.147.483.648 a 2.147.483.647|Valore intero a 32 bit con segno|  
|[uint](uint.md)|Da 0 a 4.294.967.295|Intero senza segno a 32 bit|  
|[long](long.md)|Da -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807|Numero intero con segno a 64 bit|  
|[ulong](ulong.md)|Da 0 a 18.446.744.073.709.551.615|Intero senza segno a 64 bit|  

## <a name="remarks"></a>Note
  
Se il valore rappresentato da un valore letterale Integer supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione [CS1021](../../misc/cs1021.md).

Usare la struttura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> per rappresentare un intero con segno arbitrariamente grande.
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tabelle di riferimento per i tipi](reference-tables-for-types.md)
- [Tabella dei tipi a virgola mobile](floating-point-types-table.md)
- [Tabella dei valori predefiniti](default-values-table.md)
- [Tabella di formattazione dei risultati numerici](formatting-numeric-results-table.md)
- [Tabella dei tipi incorporati](built-in-types-table.md)
- [Dati numerici in .NET](../../../standard/numerics.md)
