---
title: Operatori di assegnazione C# -riferimento
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 19f74e6835ae555a3a38aa6ca8679948c7f290dd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712754"
---
# <a name="assignment-operators-c-reference"></a>Operatori di assegnazioneC# (riferimento)

L'operatore di assegnazione `=` assegna il valore dell'operando a destra a una variabile, una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un elemento [indicizzatore](../../programming-guide/indexers/index.md) indicato dall'operando a sinistra. Il risultato di un'espressione di assegnazione è il valore assegnato all'operando a sinistra. Il tipo dell'operando destro deve corrispondere al tipo dell'operando sinistro o essere convertibile in modo implicito in esso.

L'operatore di assegnazione `=` è associato a destra, ovvero un'espressione nel formato

```csharp
a = b = c
```

viene valutata come

```csharp
a = (b = c)
```

L'esempio seguente illustra l'utilizzo dell'operatore di assegnazione con una variabile locale, una proprietà e un elemento indicizzatore come operando sul lato sinistro:

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a>Operatore di assegnazione ref

A partire da C# 7.3, è possibile usare l'operatore di assegnazione ref `= ref` per riassegnare una variabile [locale ref](../keywords/ref.md#ref-locals) o [locale ref readonly](../keywords/ref.md#ref-readonly-locals). L'esempio seguente illustra l'uso dell'operatore di assegnazione ref:

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

Nel caso dell'operatore di assegnazione Ref, entrambi gli operandi devono essere dello stesso tipo.

## <a name="compound-assignment"></a>Assegnazione composta

Per un operatore binario `op`, un'espressione di assegnazione composta in formato

```csharp
x op= y
```

equivale a

```csharp
x = x op y
```

con la differenza che `x` viene valutato una sola volta.

L'assegnazione composta è supportata da operatori [aritmetici](arithmetic-operators.md#compound-assignment), [logici booleani](boolean-logical-operators.md#compound-assignment) e [logici bit per bit e shift](bitwise-and-shift-operators.md#compound-assignment).

## <a name="null-coalescing-assignment"></a>Assegnazione di Unione null

A partire C# da 8,0, è possibile usare l'operatore di assegnazione di unione null `??=` per assegnare il valore dell'operando destro all'operando sinistro solo se l'operando sinistro restituisce `null`. Per ulteriori informazioni, vedere [?? e?? = articolo Operators](null-coalescing-operator.md) .

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente non può eseguire l' [Overload](operator-overloading.md) dell'operatore di assegnazione. Tuttavia, un tipo definito dall'utente può definire una conversione implicita in un altro tipo. In questo modo il valore di un tipo definito dall'utente può essere assegnato a una variabile, una proprietà o un elemento indicizzatore di un altro tipo. Per altre informazioni, vedere [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md).

Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta. Tuttavia, se un tipo definito dall'utente sovraccarica un operatore binario `op`, anche l'operatore di `op=`, se esistente, viene sottosovraccarico in modo implicito.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori di assegnazione](~/_csharplang/spec/expressions.md#assignment-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Per ulteriori informazioni sull'operatore di assegnazione Ref `= ref`, vedere la [Nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [ref (parola chiave)](../keywords/ref.md)
