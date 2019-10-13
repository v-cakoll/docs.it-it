---
title: '! ( C# riferimento a null) (operatore)'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: cf941e5e3fa3fc6313ef8b2ff5c176aec68c1e6b
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291725"
---
# <a name="-null-forgiving-operator-c-reference"></a>! operatore (riferimento null) (C# riferimento)

Disponibile in C# 8,0 e versioni successive, il suffisso unario `!` operatore è l'operatore che perdona i valori null. In un [contesto di annotazione Nullable](../../nullable-references.md#nullable-annotation-context)abilitato, è possibile usare l'operatore con indulgenza null per dichiarare che l'espressione `x` di un tipo di riferimento non è null: `x!`. Il prefisso unario @no__t operatore-0 è un [operatore logico di negazione](boolean-logical-operators.md#logical-negation-operator-).

L'operatore che perdona i valori null non ha alcun effetto in fase di esecuzione. Influisce solo sull'analisi del flusso statico del compilatore modificando lo stato null dell'espressione. In fase di esecuzione l'espressione `x!` restituisce il risultato dell'espressione sottostante `x`.

Per ulteriori informazioni sulla funzionalità dei tipi di riferimento Nullable, vedere [tipi di riferimento Nullable](../../nullable-references.md).

## <a name="examples"></a>Esempi

Uno dei casi d'uso dell'operatore che perdona i valori null è il test della logica di convalida degli argomenti. Si consideri ad esempio la classe seguente:

[!code-csharp[Person class](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#PersonClass)]

Usando il [Framework di test di MSTest](../../../core/testing/unit-testing-with-mstest.md), è possibile creare il test seguente per la logica di convalida nel costruttore:

[!code-csharp[Person test](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#TestPerson)]

Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per il codice precedente: `Warning CS8625: Cannot convert null literal to non-nullable reference type`. Con l'uso dell'operatore di indulgenza null, si consente al compilatore di sapere che il passaggio di `null` è previsto e non deve essere avvisato.

È anche possibile usare l'operatore di indulgenza null quando si è certi che un'espressione non può essere `null`, ma il compilatore non riesce a conoscerlo. Nell'esempio seguente, se il metodo `IsValid` restituisce `true`, il relativo argomento non è `null` ed è possibile dereferenziarlo in modo sicuro:

[!code-csharp[Use null-forgiving operator](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseNullForgiving)]

Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per il codice `p.Name`: `Warning CS8602: Dereference of a possibly null reference.`.

Se è possibile modificare il metodo `IsValid`, è possibile usare l'attributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) per indicare al compilatore che un argomento del metodo `IsValid` non può essere `null` quando il metodo restituisce `true`:

[!code-csharp[Use an attribute](~/samples/csharp/language-reference/operators/NullForgivingOperator.cs#UseAttribute)]

Nell'esempio precedente non è necessario usare l'operatore che perdona i valori null perché il compilatore dispone di informazioni sufficienti per scoprire che `p` non può essere `null` nell'istruzione `if`. Per ulteriori informazioni sugli attributi che consentono di specificare informazioni aggiuntive sullo stato null di una variabile, vedere [aggiornare le API con attributi per definire le aspettative null](../../nullable-attributes.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Esercitazione: Progettazione con tipi di riferimento Nullable @ no__t-0
