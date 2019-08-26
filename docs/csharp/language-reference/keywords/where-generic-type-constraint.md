---
title: where (vincolo di tipo generico) - Riferimenti per C#
ms.custom: seodec18
ms.date: 04/12/2018
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: 1608cd7b888a67af3ccb98b16323e74a9c5ad4a9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608405"
---
# <a name="where-generic-type-constraint-c-reference"></a>where (vincolo di tipo generico) (Riferimenti per C#)

La clausola `where` in una definizione generica specifica i vincoli per i tipi che vengono usati come argomenti per i parametri di tipo in un tipo generico, metodo, delegato o funzione locale. I vincoli possono specificare interfacce, classi di base o richiedere che un tipo generico sia un riferimento, un valore o un tipo non gestito. Dichiarano le funzionalità che l'argomento tipo deve possedere.

Ad esempio, una classe generica, `MyGenericClass`, può essere dichiarata in modo che tramite il parametro di tipo `T` venga implementata l'interfaccia <xref:System.IComparable%601>:

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#1)]

> [!NOTE]
> Per altre informazioni sulla clausola where in un'espressione di query, vedere [Clausola where](where-clause.md).

La clausola `where` può inoltre includere un vincolo di classe di base. Il vincolo di classe di base dichiara che un tipo da usare come argomento tipo per quel tipo generico usi la classe specificata come classe di base (o sia quella classe di base) come argomento tipo per quel tipo generico. Se viene usato il vincolo della classe di base, deve apparire prima di tutti gli altri vincoli per quel parametro di tipo. Alcuni tipi non sono consentiti come vincoli di classe di base: <xref:System.Object>, <xref:System.Array> e <xref:System.ValueType>. Prima di C# 7.3 anche <xref:System.Enum>, <xref:System.Delegate> e <xref:System.MulticastDelegate> non erano consentiti come vincoli di classe di base. L'esempio seguente illustra i tipi possono ora essere specificati come una classe di base:

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#2)]

La clausola `where` può specificare che il tipo è un oggetto `class` o `struct`. Il vincolo `struct` elimina la necessità di specificare un vincolo di classe di base di `System.ValueType`. Il tipo `System.ValueType` non può essere usato come vincolo di classe di base. Nell'esempio seguente vengono illustrati i vincoli `class` e `struct`:

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#3)]

La clausola `where` può anche includere un vincolo `unmanaged`. Il vincolo `unmanaged` limita il parametro di tipo ai tipi noti come [tipi non gestiti](../builtin-types/unmanaged-types.md). Il vincolo `unmanaged` rende più semplice la scrittura di codice di interoperabilità di basso livello in C#. Questo vincolo abilita le routine riutilizzabili in tutti i tipi non gestiti. Il vincolo `unmanaged` non può essere combinato con il vincolo `class` o `struct`. Il vincolo `unmanaged` impone che il tipo deve essere un elemento `struct`:

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#4)]

La clausola `where` può anche includere un vincolo di costruttore, `new()`. Tale vincolo consente di creare un'istanza di un parametro di tipo usando l'operatore `new`. Il [vincolo new()](new-constraint.md) consente al compilatore di sapere che ogni argomento di tipo specificato deve usare un costruttore accessibile senza parametri o predefinito. Ad esempio:

[!code-csharp[using the new constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#5)]

Il vincolo `new()` viene visualizzato per ultimo nella clausola `where`. Il vincolo `new()` non può essere combinato con i vincoli `struct` o `unmanaged`. Tutti i tipi che soddisfano i vincoli devono avere un costruttore senza parametri accessibile, per rendere il vincolo `new()` ridondante.

Con più parametri di tipo, usare una clausola `where` per ogni parametro di tipo, ad esempio:

[!code-csharp[using multiple where constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#6)]

È anche possibile associare vincoli ai parametri di tipo di metodi generici, come illustrato nell'esempio seguente:

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#7)]

Si noti che la sintassi usata per descrivere i vincoli dei parametri di tipo per i delegati è uguale a quella dei metodi:

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#8)]

Per informazioni sui delegati generici, vedere [Delegati generici](../../programming-guide/generics/generic-delegates.md).

Per informazioni dettagliate sulla sintassi e sull'uso dei vincoli, vedere [Vincoli sui parametri di tipo](../../programming-guide/generics/constraints-on-type-parameters.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Introduzione ai generics](../../programming-guide/generics/index.md)
- [Vincolo new](./new-constraint.md)
- [Vincoli sui parametri di tipo](../../programming-guide/generics/constraints-on-type-parameters.md)
