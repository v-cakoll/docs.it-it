---
title: Operatore % (Riferimenti per C#)
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: 9cd2f7ad3856feb34667686979c942ecb21887c2
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45645918"
---
# <a name="-operator-c-reference"></a>Operatore % (Riferimenti per C#)

L'operatore di resto `%` calcola il resto dopo aver diviso il primo operando per il secondo. I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `%`. Quando `%` viene sottoposto a overload, anche l'[operatore di assegnazione di resto](remainder-assignment-operator.md) `%=` viene sottoposto implicitamente a overload.

Tutti i tipi numerici supportano l'operatore di resto.

## <a name="integer-remainder"></a>Resto intero
  
Per gli operandi di intero, il risultato di `a % b` è il valore prodotto da `a - (a / b) * b`. Il segno del resto diverso da zero è uguale a quello del primo operando, come illustrato nell'esempio seguente:

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a>Resto a virgola mobile

Per gli operandi [float](../keywords/float.md) e [double](../keywords/double.md), il risultato di `x % y` per `x` e `y` finiti è il valore `z` tale per cui

- il segno di `z`, se diverso da zero, è uguale a quello di `x`;
- il valore assoluto di `z` è il valore prodotto da `|x| - n * |y|` in cui `n` è l'intero più grande possibile, che è minore o uguale a `|x| / |y|` e `|x|` e `|y|` sono i valori assoluti di `x` e `y`, rispettivamente.

Per informazioni sul comportamento dell'`%` operatore in caso di operandi non finiti, vedere la sezione [relativa all'operatore di resto](/dotnet/csharp/language-reference/language-specification/expressions#remainder-operator) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/index).

> [!NOTE]
> Questo metodo di calcolo del resto è analogo a quello utilizzato per gli operandi di numero intero, ma differisce da IEEE 754. Se è necessario che l'operazione di resto sia compatibile con il valore IEEE 754, usare il metodo <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.

Nell'esempio seguente viene illustrato il comportamento dell'operatore di resto per gli operandi `float` e `double`.

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

Prendere nota degli errori di arrotondamento che possono essere associati ai tipi a virgola mobile.

Per gli operandi [decimali](../keywords/decimal.md), l'operatore di resto è `%` equivale all'[operatore di resto](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) di tipo <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
