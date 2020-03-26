---
title: Valori predefiniti dei tipi C
description: Informazioni sui valori predefiniti dei tipi c'è, ad esempio bool, char, int, float, double e altro ancora.
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 5e34d291ec15c738f3bc9409df321ede454b6710
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507256"
---
# <a name="default-values-of-c-types-c-reference"></a>Valori predefiniti dei tipi C .

La tabella seguente mostra i valori predefiniti dei tipi C#:

|Type|Valore predefinito|
|---------|------------------|
|Qualsiasi tipo riferimento|`null`|
|Qualsiasi [tipo numerico integrale incorporato](integral-numeric-types.md)|0 (zero)|
|Qualsiasi [tipo numerico a virgola mobile incorporato](floating-point-numeric-types.md)|0 (zero)|
|[bool](bool.md)|`false`|
|[char](char.md)|`'\0'` (U+0000)|
|[Enum](enum.md)|Valore prodotto dall'espressione `(E)0`, dove `E` è l'identificatore di enumerazione.|
|[struct](struct.md)|Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.|
|Qualsiasi [tipo valore nullable](nullable-value-types.md)|Un'istanza per la quale la proprietà <xref:System.Nullable%601.HasValue%2A> è `false` e la proprietà <xref:System.Nullable%601.Value%2A> non è definita. Tale valore predefinito è noto anche come valore *null* di un tipo di valore nullable.|

Utilizzare [ `default` l'operatore](../operators/default.md#default-operator) per produrre il valore predefinito di un tipo, come illustrato nell'esempio seguente:

```csharp
int a = default(int);
```

A partire dalla versione 7.1 di C, è possibile usare il [ `default` valore letterale](../operators/default.md#default-literal) per inizializzare una variabile con il valore predefinito del relativo tipo:

```csharp
int a = default;
```

Per un tipo valore, anche il costruttore senza parametri implicito produce il valore predefinito del tipo, come mostrato nell'esempio seguente:

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

In fase di <xref:System.Type?displayProperty=nameWithType> esecuzione, se l'istanza rappresenta <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> un tipo di valore, è possibile utilizzare il metodo per richiamare il costruttore senza parametri per ottenere il valore predefinito del tipo.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Valori predefiniti](~/_csharplang/spec/variables.md#default-values)
- [Costruttori predefiniti](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Costruttori](../../programming-guide/classes-and-structs/constructors.md)
