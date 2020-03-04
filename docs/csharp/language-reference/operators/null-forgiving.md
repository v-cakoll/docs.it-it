---
title: '! ( C# riferimento a null) (operatore)'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 026c50d1696b29f8498d316ae106bc851ed16f6a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239015"
---
# <a name="-null-forgiving-operator-c-reference"></a>! operatore (riferimento null) (C# riferimento)

Disponibile in C# 8,0 e versioni successive, il suffisso unario `!` operatore è l'operatore che perdona i valori null. In un [contesto di annotazione Nullable](../../nullable-references.md#nullable-annotation-context)abilitato, si usa l'operatore che perdona i valori null per dichiarare che l'espressione `x` di un tipo di riferimento non è `null`: `x!`. Il prefisso unario `!` operatore è l' [operatore di negazione logica](boolean-logical-operators.md#logical-negation-operator-).

L'operatore che perdona i valori null non ha alcun effetto in fase di esecuzione. Influisce solo sull'analisi del flusso statico del compilatore modificando lo stato null dell'espressione. In fase di esecuzione, Expression `x!` restituisce il risultato dell'espressione sottostante `x`.

Per ulteriori informazioni sulla funzionalità dei tipi di riferimento Nullable, vedere [tipi di riferimento Nullable](../../nullable-references.md).

## <a name="examples"></a>Esempi

Uno dei casi d'uso dell'operatore che perdona i valori null è il test della logica di convalida degli argomenti. Si consideri ad esempio la classe seguente:

[!code-csharp[Person class](~/samples/snippets/csharp/language-reference/operators/NullForgivingOperator.cs#PersonClass)]

Usando il [Framework di test di MSTest](../../../core/testing/unit-testing-with-mstest.md), è possibile creare il test seguente per la logica di convalida nel costruttore:

[!code-csharp[Person test](~/samples/snippets/csharp/language-reference/operators/NullForgivingOperator.cs#TestPerson)]

Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per il codice precedente: `Warning CS8625: Cannot convert null literal to non-nullable reference type`. Utilizzando l'operatore di indulgenza null, si informa il compilatore che il passaggio di `null` è previsto e non deve essere avvisato.

È anche possibile usare l'operatore di indulgenza null quando si è certi che un'espressione non può essere `null` ma il compilatore non riesce a conoscerlo. Nell'esempio seguente, se il metodo `IsValid` restituisce `true`, il relativo argomento non viene `null` ed è possibile dereferenziarlo in modo sicuro:

[!code-csharp[Use null-forgiving operator](~/samples/snippets/csharp/language-reference/operators/NullForgivingOperator.cs#UseNullForgiving)]

Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per il codice di `p.Name`: `Warning CS8602: Dereference of a possibly null reference`.

Se è possibile modificare il metodo `IsValid`, è possibile usare l'attributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) per informare il compilatore che non è possibile `null` un argomento del metodo `IsValid` quando il metodo restituisce `true`:

[!code-csharp[Use an attribute](~/samples/snippets/csharp/language-reference/operators/NullForgivingOperator.cs#UseAttribute)]

Nell'esempio precedente non è necessario usare l'operatore che perdona i valori null perché il compilatore dispone di informazioni sufficienti per scoprire che non è possibile `null` `p` all'interno dell'istruzione `if`. Per ulteriori informazioni sugli attributi che consentono di fornire informazioni aggiuntive sullo stato null di una variabile, vedere [aggiornare le API con attributi per definire le aspettative null](../../nullable-attributes.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere [la sezione operatore con indulgenza null](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) della [bozza della specifica dei tipi di riferimento Nullable](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Esercitazione: progettare con tipi di riferimento Nullable](../../tutorials/nullable-reference-types.md)
