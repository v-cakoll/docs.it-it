---
title: Tabella dei valori predefiniti (Riferimenti per C#)
description: Informazioni sui valori predefiniti dei tipi valore restituiti dai costruttori predefiniti.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
|[bool](bool.md)|`false`|
|[byte](byte.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0.0D|
|[enum](enum.md)|Valore prodotto dall'espressione (E)0, dove E è l'identificatore di enumerazione.|
|[float](float.md)|0.0F|
|[int](int.md)|0|
|[long](long.md)|0L|
|[sbyte](sbyte.md)|0|
|[short](short.md)|0|
|[struct](struct.md)|Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.|
|[uint](uint.md)|0|
|[ulong](ulong.md)|0|
|[ushort](ushort.md)|0|

## <a name="see-also"></a>Vedere anche
 [Riferimenti per C#](../index.md)  
 [Guida per programmatori C#](../../programming-guide/index.md)  
 [Tabella dei tipi valore](value-types-table.md)  
 [Tipi valore](value-types.md)  
 [Tabella dei tipi incorporati](built-in-types-table.md)  
 [Tabelle di riferimento per i tipi](reference-tables-for-types.md)
