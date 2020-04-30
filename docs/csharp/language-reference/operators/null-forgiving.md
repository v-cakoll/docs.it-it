---
title: '! operatore (null-perdonatore)-riferimenti per C#'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 772f37f1fc7446eae66f0cd0f12adb5e2e41997d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595949"
---
# <a name="-null-forgiving-operator-c-reference"></a>! operatore (null-perdonatore) (riferimenti per C#)

Disponibile in C# 8,0 e versioni successive, l'operatore `!` unario di suffisso è l'operatore che perdona i valori null. In un [contesto di annotazione Nullable](../../nullable-references.md#nullable-annotation-context)abilitato, si usa l'operatore che perdona i valori `x` null per dichiarare che l' `null`espressione `x!`di un tipo di riferimento non è:. L'operatore di `!` prefisso unario è l' [operatore logico di negazione](boolean-logical-operators.md#logical-negation-operator-).

L'operatore che perdona i valori null non ha alcun effetto in fase di esecuzione. Influisce solo sull'analisi del flusso statico del compilatore modificando lo stato null dell'espressione. In fase di esecuzione, `x!` l'espressione restituisce il risultato dell'espressione `x`sottostante.

> [!NOTE]
> In C# 8 l'operatore che perdona i valori null interagisce con gli [operatori condizionali null](member-access-operators.md#null-conditional-operators--and-) in modo imprevisto. L'espressione `x?.y!.z` viene analizzata come `(x?.y)!.z`. A causa di questa `z` interpretazione viene valutata `x` anche `null`se è, che può produrre <xref:System.NullReferenceException>un.

Per ulteriori informazioni sulla funzionalità dei tipi di riferimento Nullable, vedere [tipi di riferimento Nullable](../builtin-types/nullable-reference-types.md).

## <a name="examples"></a>Esempi

Uno dei casi d'uso dell'operatore che perdona i valori null è il test della logica di convalida degli argomenti. Si consideri ad esempio la classe seguente:

[!code-csharp[Person class](snippets/NullForgivingOperator.cs#PersonClass)]

Usando il [Framework di test di MSTest](../../../core/testing/unit-testing-with-mstest.md), è possibile creare il test seguente per la logica di convalida nel costruttore:

[!code-csharp[Person test](snippets/NullForgivingOperator.cs#TestPerson)]

Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per il codice precedente `Warning CS8625: Cannot convert null literal to non-nullable reference type`:. Utilizzando l'operatore di indulgenza null, si informa il compilatore che il `null` passaggio è previsto e non deve essere avvisato.

È anche possibile usare l'operatore di indulgenza null quando si è certi che un'espressione non `null` può essere, ma il compilatore non riesce a riconoscerlo. Nell'esempio seguente, se il `IsValid` metodo restituisce `true`, il relativo argomento non `null` è ed è possibile dereferenziarlo in modo sicuro:

[!code-csharp[Use null-forgiving operator](snippets/NullForgivingOperator.cs#UseNullForgiving)]

Senza l'operatore di indulgenza null, il compilatore genera l'avviso seguente per `p.Name` il codice `Warning CS8602: Dereference of a possibly null reference`:.

Se è possibile modificare il `IsValid` metodo, è possibile usare l'attributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) per informare il compilatore che un argomento del `IsValid` metodo non può essere `null` quando il metodo restituisce `true`:

[!code-csharp[Use an attribute](snippets/NullForgivingOperator.cs#UseAttribute)]

Nell'esempio precedente non è necessario usare l'operatore che perdona i valori null perché il compilatore dispone di informazioni sufficienti per individuare che `p` non possono essere `null` incluse nell' `if` istruzione. Per ulteriori informazioni sugli attributi che consentono di fornire informazioni aggiuntive sullo stato null di una variabile, vedere [aggiornare le API con attributi per definire le aspettative null](../attributes/nullable-analysis.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere [la sezione operatore con indulgenza null](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) della [bozza della specifica dei tipi di riferimento Nullable](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Esercitazione: progettare con tipi di riferimento Nullable](../../tutorials/nullable-reference-types.md)
