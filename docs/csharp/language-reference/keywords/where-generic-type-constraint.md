---
title: where (vincolo di tipo generico) - Riferimenti per C#
ms.date: 04/15/2020
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: 406c710cd884363c32b98336717732a09b3d1fc1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401875"
---
# <a name="where-generic-type-constraint-c-reference"></a>where (vincolo di tipo generico) (Riferimenti per C#)

La clausola `where` in una definizione generica specifica i vincoli per i tipi che vengono usati come argomenti per i parametri di tipo in un tipo generico, metodo, delegato o funzione locale. I vincoli possono specificare interfacce, classi base o richiedere che un tipo generico sia un riferimento, un valore o un tipo non gestito. Dichiarano le funzionalità che l'argomento di tipo deve avere.

Ad esempio, una classe generica, `MyGenericClass`, può essere dichiarata in modo che tramite il parametro di tipo `T` venga implementata l'interfaccia <xref:System.IComparable%601>:

[!code-csharp[using an interface constraint](snippets/GenericWhereConstraints.cs#1)]

> [!NOTE]
> Per altre informazioni sulla clausola where in un'espressione di query, vedere [Clausola where](where-clause.md).

La clausola `where` può inoltre includere un vincolo di classe di base. Il vincolo della classe base dichiara che un tipo da usare come argomento di tipo per il tipo generico ha la classe specificata come classe di base o è tale classe base. Se viene usato il vincolo della classe di base, deve apparire prima di tutti gli altri vincoli per quel parametro di tipo. Alcuni tipi non sono consentiti come vincoli di classe di base: <xref:System.Object>, <xref:System.Array> e <xref:System.ValueType>. Prima di C# 7,3,, <xref:System.Enum> <xref:System.Delegate> e non <xref:System.MulticastDelegate> sono consentiti come vincoli di classe di base. L'esempio seguente illustra i tipi possono ora essere specificati come una classe di base:

[!code-csharp[using an interface constraint](snippets/GenericWhereConstraints.cs#2)]

In un contesto nullable in C# 8,0 e versioni successive, viene applicato il supporto di valori null del tipo di classe base. Se la classe base è non Nullable (ad esempio `Base` ), l'argomento di tipo deve essere non nullable. Se la classe di base ammette i valori null (ad esempio `Base?` ), l'argomento di tipo può essere un tipo di riferimento nullable o non nullable. Il compilatore genera un avviso se l'argomento di tipo è un tipo di riferimento Nullable quando la classe base è non nullable.

La clausola `where` può specificare che il tipo è un oggetto `class` o `struct`. Il vincolo `struct` elimina la necessità di specificare un vincolo di classe di base di `System.ValueType`. Il tipo `System.ValueType` non può essere usato come vincolo di classe di base. Nell'esempio seguente vengono illustrati i vincoli `class` e `struct`:

[!code-csharp[using the class and struct constraints](snippets/GenericWhereConstraints.cs#3)]

In un contesto nullable in C# 8,0 e versioni successive, il `class` vincolo richiede che un tipo sia un tipo di riferimento non nullable. Per consentire i tipi di riferimento Nullable, usare il `class?` vincolo, che consente i tipi di riferimento nullable e non nullable.

La `where` clausola può includere il `notnull` vincolo. Il `notnull` vincolo limita il parametro di tipo ai tipi che non ammettono valori null. Il tipo può essere un [tipo di valore](../builtin-types/value-types.md) o un tipo di riferimento non nullable. Il `notnull` vincolo è disponibile a partire da C# 8,0 per il codice compilato in un [ `nullable enable` contesto](../../nullable-references.md#nullable-contexts). Diversamente da altri vincoli, se un argomento di tipo viola il `notnull` vincolo, il compilatore genera un avviso anziché un errore. Gli avvisi vengono generati solo in un `nullable enable` contesto.

> [!IMPORTANT]
> Le dichiarazioni generiche che includono il `notnull` vincolo possono essere utilizzate in un contesto ignaro Nullable, ma il compilatore non impone il vincolo.

[!code-csharp[using the nonnull constraint](snippets/GenericWhereConstraints.cs#NotNull)]

La clausola `where` può anche includere un vincolo `unmanaged`. Il vincolo `unmanaged` limita il parametro di tipo ai tipi noti come [tipi non gestiti](../builtin-types/unmanaged-types.md). Il vincolo `unmanaged` rende più semplice la scrittura di codice di interoperabilità di basso livello in C#. Questo vincolo abilita le routine riutilizzabili in tutti i tipi non gestiti. Il vincolo `unmanaged` non può essere combinato con il vincolo `class` o `struct`. Il vincolo `unmanaged` impone che il tipo deve essere un elemento `struct`:

[!code-csharp[using the unmanaged constraint](snippets/GenericWhereConstraints.cs#4)]

La clausola `where` può anche includere un vincolo di costruttore, `new()`. Tale vincolo consente di creare un'istanza di un parametro di tipo usando l'operatore `new`. Il [vincolo New ()](new-constraint.md) consente al compilatore di verificare che qualsiasi argomento di tipo fornito disponga di un costruttore senza parametri accessibile. Ad esempio:

[!code-csharp[using the new constraint](snippets/GenericWhereConstraints.cs#5)]

Il vincolo `new()` viene visualizzato per ultimo nella clausola `where`. Il vincolo `new()` non può essere combinato con i vincoli `struct` o `unmanaged`. Tutti i tipi che soddisfano i vincoli devono avere un costruttore senza parametri accessibile, per rendere il vincolo `new()` ridondante.

Con più parametri di tipo, usare una clausola `where` per ogni parametro di tipo, ad esempio:

[!code-csharp[using multiple where constraints](snippets/GenericWhereConstraints.cs#6)]

È anche possibile associare vincoli ai parametri di tipo di metodi generici, come illustrato nell'esempio seguente:

[!code-csharp[where constraints with generic methods](snippets/GenericWhereConstraints.cs#7)]

Si noti che la sintassi usata per descrivere i vincoli dei parametri di tipo per i delegati è uguale a quella dei metodi:

[!code-csharp[where constraints with generic methods](snippets/GenericWhereConstraints.cs#8)]

Per informazioni sui delegati generici, vedere [Delegati generici](../../programming-guide/generics/generic-delegates.md).

Per informazioni dettagliate sulla sintassi e sull'uso dei vincoli, vedere [Vincoli sui parametri di tipo](../../programming-guide/generics/constraints-on-type-parameters.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Introduzione ai generics](../../programming-guide/generics/index.md)
- [nuovo vincolo](./new-constraint.md)
- [Vincoli sui parametri di tipo](../../programming-guide/generics/constraints-on-type-parameters.md)
