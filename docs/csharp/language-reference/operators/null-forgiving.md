---
title: '! (null-forgiving) (operatore - Riferimento in C'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 658043f8d5e149064f6da328657b2ccef9b5da94
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121439"
---
# <a name="-null-forgiving-operator-c-reference"></a>! (null-forgiving) (riferimento c'è)

Disponibile in C , 8.0 e versioni `!` successive, l'operatore suffisso unario è l'operatore per dono null. In un contesto di [annotazione nullable](../../nullable-references.md#nullable-annotation-context)abilitato , utilizzare `x` l'operatore di `null` `x!`perdono null per dichiarare che l'espressione di un tipo di riferimento non è : . L'operatore `!` prefisso unario è l'operatore di [negazione logica.](boolean-logical-operators.md#logical-negation-operator-)

L'operatore che perdona i valori Null non ha alcun effetto in fase di esecuzione. Influisce solo sull'analisi statica del flusso del compilatore modificando lo stato null dell'espressione. In fase di `x!` esecuzione, expression restituisce `x`il risultato dell'espressione sottostante.

Per ulteriori informazioni sulla funzionalità dei tipi di riferimento nullable, vedere [Tipi di riferimento nullable](../builtin-types/nullable-reference-types.md).

## <a name="examples"></a>Esempi

Uno dei casi d'uso dell'operatore che perdona i valori Null è nel test della logica di convalida dell'argomento. Si consideri ad esempio la classe seguente:

[!code-csharp[Person class](snippets/NullForgivingOperator.cs#PersonClass)]

Utilizzando il framework di [test MSTest](../../../core/testing/unit-testing-with-mstest.md), è possibile creare il test seguente per la logica di convalida nel costruttore:

[!code-csharp[Person test](snippets/NullForgivingOperator.cs#TestPerson)]

Senza l'operatore di perdono null, il compilatore `Warning CS8625: Cannot convert null literal to non-nullable reference type`genera il seguente avviso per il codice precedente: . Utilizzando l'operatore di perdono null, `null` si informa il compilatore che il passaggio è previsto e non deve essere avvisato.

È anche possibile usare l'operatore di perdono null `null` quando si sa sicuramente che un'espressione non può essere, ma il compilatore non riesce a riconoscerlo. Nell'esempio seguente, `IsValid` se `true`il metodo restituisce , il relativo argomento non `null` è ed è possibile dereferenziarlo in modo sicuro:

[!code-csharp[Use null-forgiving operator](snippets/NullForgivingOperator.cs#UseNullForgiving)]

Senza l'operatore di perdono null, il `p.Name` compilatore genera il seguente avviso per il codice: `Warning CS8602: Dereference of a possibly null reference`.

Se è possibile `IsValid` modificare il metodo, è possibile utilizzare l'attributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) per informare il compilatore che un argomento del `IsValid` metodo non può essere `null` quando il metodo restituisce `true`:

[!code-csharp[Use an attribute](snippets/NullForgivingOperator.cs#UseAttribute)]

Nell'esempio precedente, non è necessario utilizzare l'operatore di perdono null perché `p` il `null` compilatore `if` dispone di informazioni sufficienti per scoprire che non possono essere all'interno dell'istruzione. Per ulteriori informazioni sugli attributi che consentono di fornire informazioni aggiuntive sullo stato null di una variabile, vedere [Aggiornare le API con attributi per definire le aspettative null.](../../nullable-attributes.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere [Sezione relativa all'operatore](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) di perdono null della bozza della specifica dei tipi di riferimento [nullable](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Esercitazione: Progettazione con tipi di riferimento nullableTutorial: Design with nullable reference types](../../tutorials/nullable-reference-types.md)
