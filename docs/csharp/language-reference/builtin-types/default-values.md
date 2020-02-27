---
title: Valori predefiniti dei C# tipi- C# Reference
description: Informazioni sui valori predefiniti dei C# tipi, ad esempio bool, Char, int, float, Double e altro.
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 93b6079b9a3bbf6d537094cab9dfb305ace7f6bf
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625865"
---
# <a name="default-values-of-c-types-c-reference"></a>Valori predefiniti dei C# tipi (C# riferimento)

La tabella seguente mostra i valori predefiniti dei tipi C#:

|Type|Valore predefinito|
|---------|------------------|
|Qualsiasi tipo riferimento|`null`|
|Qualsiasi [tipo numerico integrale incorporato](integral-numeric-types.md)|0 (zero)|
|Qualsiasi [tipo numerico a virgola mobile incorporato](floating-point-numeric-types.md)|0 (zero)|
|[bool](bool.md)|`false`|
|[char](char.md)|`'\0'` (U+0000)|
|[enum](enum.md)|Valore prodotto dall'espressione `(E)0`, dove `E` è l'identificatore di enumerazione.|
|[struct](struct.md)|Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.|
|Qualsiasi [tipo valore nullable](nullable-value-types.md)|Un'istanza per la quale la proprietà <xref:System.Nullable%601.HasValue%2A> è `false` e la proprietà <xref:System.Nullable%601.Value%2A> non è definita. Il valore predefinito è noto anche come valore *null* di un tipo di valore Nullable.|

Usare l'[operatore predefinito](../operators/default.md) per produrre il valore predefinito di un tipo, come illustrato nell'esempio seguente:

```csharp
int a = default(int);
```

A partire da C# 7.1 è possibile usare il [ valore letterale `default`](../operators/default.md#default-literal) per inizializzare una variabile con il valore predefinito del relativo tipo:

```csharp
int a = default;
```

Per un tipo valore, anche il costruttore senza parametri implicito produce il valore predefinito del tipo, come mostrato nell'esempio seguente:

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

In fase di esecuzione, se l'istanza di <xref:System.Type?displayProperty=nameWithType> rappresenta un tipo di valore, è possibile usare il metodo <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> per richiamare il costruttore senza parametri per ottenere il valore predefinito del tipo.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Valori predefiniti](~/_csharplang/spec/variables.md#default-values)
- [Costruttori predefiniti](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Costruttori](../../programming-guide/classes-and-structs/constructors.md)
