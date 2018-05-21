---
title: Tabella dei tipi incorporati (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 120347e5bff7f0d6c7120af0cb250936ca39ea16
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="built-in-types-table-c-reference"></a>Tabella dei tipi incorporati (Riferimenti per C#)
La tabella seguente include le parole chiave per i tipi predefiniti di C#, che rappresentano gli alias dei tipi predefiniti nello spazio dei nomi <xref:System>.  
  
|Tipo C#|Tipo .NET Framework|  
|--------------|-------------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[object](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[string](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a>Note  
 Tutti i tipi nella tabella, ad eccezione di `object` e `string`, sono detti tipi semplici.  
  
 Le parole chiave per i tipi C# e i relativi alias sono intercambiabili. Ad esempio, è possibile dichiarare una variabile integer, usando le seguenti dichiarazioni:  
  
```csharp  
int x = 123;  
System.Int32 x = 123;  
```  
  
 Per visualizzare il tipo effettivo di qualsiasi tipo in C#, usare il metodo di sistema `GetType()`. Ad esempio, l'istruzione seguente consente di visualizzare l'alias di sistema che rappresenta il tipo di `myVariable`:  
  
```csharp  
Console.WriteLine(myVariable.GetType());  
```  
  
 È anche possibile usare l'operatore [typeof](../../../csharp/language-reference/keywords/typeof.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Tipi valore](../../../csharp/language-reference/keywords/value-types.md)  
 [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md)  
 [Tabella di formattazione dei risultati numerici](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)  
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
 [Tabelle di riferimento per i tipi](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
