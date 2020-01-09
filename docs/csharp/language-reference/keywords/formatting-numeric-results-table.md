---
title: Tabella di formattazione dei risultati numerici - Riferimenti per C#
description: Informazioni sulle stringhe in formato numerico standard di C#
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: eb93f0a4f3c66e9f7b295366a77b9fb099fc3a1e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713503"
---
# <a name="formatting-numeric-results-table-c-reference"></a>Tabella di formattazione dei risultati numerici (Riferimenti per C#)

Nella tabella seguente vengono descritti gli identificatori di formato supportati per la formattazione dei risultati numerici. Il risultato formattato nell'ultima colonna corrisponde al valore <xref:System.Globalization.CultureInfo> "en-US".

|Identificatore di formato|Descrizione|Esempi|Risultato|  
|----------------------|-----------------|--------------|------------|  
|C o c|Valuta|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|\\$2,50<br /><br /> (\\$2,50)|  
|D o d|Decimal|`string s = $"{25:D5}";`|00025|  
|E o e|Esponenziale|`string s = $"{250000:E2}";`|2,50E+005|  
|F o f|A virgola fissa|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|2.50<br /><br /> 3\.|  
|G o g|Generale|`string s = $"{2.5:G}";`|2.5|  
|N o n|Numerico|`string s = $"{2500000:N}";`|2,500,000.00|  
|P o p|Percentuale|`string s = $"{0.25:P}";`|25,00%|  
|R o r|Round trip|`string s = $"{2.5:R}";`|2.5|  
|X o x|Esadecimale|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|FA<br /><br /> FFFF|  

## <a name="remarks"></a>Note

Usare un identificatore di formato per creare una stringa di formato. La stringa di formato ha il formato seguente: `Axx`, dove

- `A` è l'identificatore di formato, che controlla il tipo di formattazione applicato al valore numerico.
- `xx` è l'identificatore di precisione, che controlla il numero di cifre nell'output formattato. Il valore dell'identificatore della precisione è compreso tra 0 e 99.

Gli identificatori di formato decimale ("D" o "d") ed esadecimale ("X" o "x") sono supportati solo per i tipi integrali. L'identificatore di formato round trip ("R" o "r") è supportato solo per i tipi <xref:System.Single>, <xref:System.Double> e <xref:System.Numerics.BigInteger>.

Le stringhe di formato numerico standard sono supportate:

- Da alcuni overload del metodo `ToString` di tutti i tipi numerici. È ad esempio possibile fornire una stringa di formato numerico ai metodi <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> e <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.

- Dalla [funzionalità di formattazione composita](../../../standard/base-types/composite-formatting.md) di .NET, che è ad esempio supportata dal metodo <xref:System.String.Format%2A?displayProperty=nameWithType>.

- [Stringhe interpolate](../tokens/interpolated.md).

Per altre informazioni, vedere [Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Formattazione di tipi](../../../standard/base-types/formatting-types.md)
- [Formattazione composita](../../../standard/base-types/composite-formatting.md)
- [Interpolazione di stringhe](../tokens/interpolated.md)
- [string](../builtin-types/reference-types.md)
