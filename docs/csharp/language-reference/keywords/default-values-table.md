---
title: Tabella dei valori predefiniti (Riferimenti per C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d034c1daf495c50e299fec4c5bf399652dad08ce
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2017
---
# <a name="default-values-table-c-reference"></a>Tabella dei valori predefiniti (Riferimenti per C#)
La tabella seguente mostra i valori predefiniti dei tipi valore restituiti dai costruttori predefiniti. I costruttori predefiniti vengono richiamati con l'operatore `new`, in questo modo:

```csharp
int myInt = new int();
```

L'istruzione precedente ha lo stesso effetto dell'istruzione seguente:

```csharp
int myInt = 0;
```

Tenere presente che l'uso di variabili non inizializzate in C# non è consentito.

|Tipo valore|Valore predefinito|
|----------------|-------------------|
|[bool](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[byte](../../../csharp/language-reference/keywords/byte.md)|0|
|[char](../../../csharp/language-reference/keywords/char.md)|'\0'|
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|M 0|
|[double](../../../csharp/language-reference/keywords/double.md)|0.0D|
|[enum](../../../csharp/language-reference/keywords/enum.md)|Valore prodotto dall'espressione (E)0, dove E è l'identificatore di enumerazione.|
|[float](../../../csharp/language-reference/keywords/float.md)|0.0F|
|[int](../../../csharp/language-reference/keywords/int.md)|0|
|[long](../../../csharp/language-reference/keywords/long.md)|0L|
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|0|
|[short](../../../csharp/language-reference/keywords/short.md)|0|
|[struct](../../../csharp/language-reference/keywords/struct.md)|Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.|
|[uint](../../../csharp/language-reference/keywords/uint.md)|0|
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|0|
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|0|

## <a name="see-also"></a>Vedere anche
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Tabella dei tipi valore](../../../csharp/language-reference/keywords/value-types-table.md)  
 [Tipi valore](../../../csharp/language-reference/keywords/value-types.md)  
 [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabelle di riferimento per i tipi](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
