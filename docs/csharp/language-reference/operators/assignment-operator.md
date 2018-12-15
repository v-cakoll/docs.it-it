---
title: Operatore = - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 2c999e76a9238e6401e89af0faa81967b13a3995
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244388"
---
# <a name="-operator-c-reference"></a>Operatore = (Riferimenti per C#)

L'operatore di assegnazione `=` assegna il valore dell'operando a destra a una variabile, una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un elemento [indicizzatore](../../../csharp/programming-guide/indexers/index.md) indicato dall'operando a sinistra. Il risultato di un'espressione di assegnazione è il valore assegnato all'operando a sinistra. Il tipo dell'operando destro deve corrispondere al tipo dell'operando sinistro o essere convertibile in modo implicito in esso.

L'operatore di assegnazione si associa all'operando a destra, che significa che un'espressione nel formato

```csharp
a = b = c
```

viene valutata come

```csharp
a = (b = c)
```

L'esempio seguente illustra l'utilizzo dell'operatore di assegnazione per assegnare valori a una variabile locale, una proprietà e un elemento indicizzatore:

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a>Operatore di assegnazione ref

A partire da C# 7.3, è possibile usare l'operatore di assegnazione ref `= ref` per riassegnare una variabile [locale ref](../keywords/ref.md#ref-locals) o [locale ref readonly](../keywords/ref.md#ref-readonly-locals). L'esempio seguente illustra l'uso dell'operatore di assegnazione ref:

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

Nel caso dell'operatore di assegnazione ref, il tipo dell'operando sinistro deve corrispondere al tipo dell'operando destro.

Per altre informazioni, vedere la [nota relativa alla proposta di funzionalità](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente non può eseguire l'overload dell'operatore di assegnazione. Tuttavia, un tipo definito dall'utente può definire una conversione implicita in un altro tipo. In questo modo il valore di un tipo definito dall'utente può essere assegnato a una variabile, una proprietà o un elemento indicizzatore di un altro tipo. Per altre informazioni, vedere l'articolo relativo alla parola chiave [implicit](../keywords/implicit.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Assegnazione semplice](~/_csharplang/spec/expressions.md#simple-assignment) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [ref (parola chiave)](../keywords/ref.md)
