---
title: Operatori di cast e di test del tipo - Riferimenti per C#
description: Informazioni sugli operatori C# che è possibile usare per controllare il tipo del risultato di un'espressione e, se necessario, convertirlo in un altro tipo.
ms.date: 06/21/2019
author: pkulikov
f1_keywords:
- is_CSharpKeyword
- as_CSharpKeyword
- ()_CSharpKeyword
- typeof_CSharpKeyword
helpviewer_keywords:
- type-testing operators [C#]
- conversion operators [C#]
- type conversion [C#]
- is operator [C#]
- as operator [C#]
- cast operator [C#]
- cast expression [C#]
- () operator [C#]
- typeof operator [C#]
ms.openlocfilehash: 037ddc8eeda418b2e4858ab98be6cd362ca0e1e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399469"
---
# <a name="type-testing-and-cast-operators-c-reference"></a>Operatori di cast e di test del tipo (Riferimenti per C#)

È possibile usare gli operatori seguenti per eseguire il controllo o la conversione di tipi:

- [operatore is](#is-operator): per controllare se il tipo di runtime di un'espressione è compatibile con un determinato tipo
- [operatore as](#as-operator): per convertire in modo esplicito un'espressione in un tipo specificato se il tipo di runtime è compatibile con esso
- [operatore cast ()](#cast-operator-): per eseguire una conversione esplicita
- [operatore typeof](#typeof-operator): per ottenere l'istanza <xref:System.Type?displayProperty=nameWithType> per un tipo

## <a name="is-operator"></a>Operatore is

L' operatore `is` controlla se il tipo di runtime del risultato di un'espressione è compatibile con un determinato tipo. A partire dalla versione 7.0 di C, l'operatore verifica anche il `is` risultato di un'espressione rispetto a un modello.

L'espressione con l'operatore di test del tipo `is` ha il formato seguente:

```csharp
E is T
```

in cui `E` è un'espressione che restituisce un valore e `T` è il nome di un tipo o un parametro di tipo. `E` non può essere un metodo anonimo o un'espressione lambda.

L'espressione `E is T` restituisce `true` se il risultato di `E` è diverso da null e può essere convertito nel tipo `T` da una conversione di riferimento, una conversione boxing o una conversione unboxing; in caso contrario, restituisce `false`. L'operatore `is` non considera le conversioni definite dall'utente.

L'esempio seguente dimostra che l'operatore `is` restituisce `true` se il tipo di runtime del risultato di un'espressione deriva da un determinato tipo, ovvero se esiste una conversione di riferimento tra i tipi:

[!code-csharp[is with reference conversion](snippets/TypeTestingAndConversionOperators.cs#IsWithReferenceConversion)]

L'esempio seguente `is` mostra che l'operatore prende in considerazione le conversioni boxing e unboxing, ma non considera [le conversioni numeriche:](../builtin-types/numeric-conversions.md)

[!code-csharp-interactive[is with int](snippets/TypeTestingAndConversionOperators.cs#IsWithInt)]

Per informazioni sulle conversioni C#, vedere il capito [Conversioni](~/_csharplang/spec/conversions.md) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

### <a name="type-testing-with-pattern-matching"></a>Test del tipo con criteri di ricerca

A partire dalla versione 7.0 di C, l'operatore verifica anche il `is` risultato di un'espressione rispetto a un modello. In particolare, supporta il criterio del tipo nel formato seguente:

```csharp
E is T v
```

in cui `E` è un'espressione che restituisce un valore, `T` è il nome di un tipo o un parametro di tipo e `v` è una nuova variabile locale di tipo `T`. Se il risultato di `E` è diverso da null e può essere convertito in `T` con una conversione di riferimento, boxing o unboxing, l'espressione `E is T v` restituisce `true` e il valore convertito del risultato di `E` viene assegnato alla variabile `v`.

L'esempio seguente illustra l'uso dell'operatore `is` con un criterio del tipo:

[!code-csharp-interactive[is with type pattern](snippets/TypeTestingAndConversionOperators.cs#IsTypePattern)]

Per altre informazioni sul criterio del tipo e sugli altri criteri supportati, vedere [Criteri di ricerca con is](../keywords/is.md#pattern-matching-with-is).

## <a name="as-operator"></a>operatore as

L'operatore `as` converte in modo esplicito il risultato di un'espressione in un tipo di valore nullable o di riferimento specificato. Se la conversione non è possibile, l'operatore `as` restituisce `null`. A differenza dell'[operatore cast ()](#cast-operator-), l'operatore `as` non genera mai un'eccezione.

Un'espressione nel formato

```csharp
E as T
```

in cui `E` è un'espressione che restituisce un valore e `T` è il nome di un tipo o un parametro di tipo, produce lo stesso risultato di

```csharp
E is T ? (T)(E) : (T)null
```

con la differenza che `E` viene valutato una sola volta.

L'operatore `as` considera solo conversioni di riferimenti, nullable, boxing e unboxing. Non è possibile usare l'operatore `as` per eseguire una conversione definita dall'utente. A questo scopo, usare l'[operatore cast()](#cast-operator-).

Nell'esempio seguente viene illustrato l'uso dell'operatore `as`:

[!code-csharp-interactive[as operator](snippets/TypeTestingAndConversionOperators.cs#AsOperator)]

> [!NOTE]
> Come mostrato nell'esempio precedente, è necessario confrontare il risultato dell'espressione `as` con `null` per verificare se la conversione riesce. A partire dalla versione 7.0 di C, è possibile usare [l'operatore is](#type-testing-with-pattern-matching) sia per verificare se la conversione ha esito positivo e, in caso di esito positivo, assegnare il risultato a una nuova variabile.

## <a name="cast-operator-"></a>Operatore cast ()

Un'espressione cast nel formato `(T)E` esegue una conversione esplicita del risultato dell'espressione `E` nel tipo `T`. Se non esiste alcuna conversione esplicita dal tipo `E` al tipo `T`, si verifica un errore in fase di compilazione. In fase di esecuzione, è possibile che una conversione esplicita non riesca e che un'espressione cast generi un'eccezione.

L'esempio seguente illustra conversioni esplicite numeriche e di riferimento:

[!code-csharp-interactive[cast expression](snippets/TypeTestingAndConversionOperators.cs#Cast)]

Per informazioni sulle conversioni esplicite supportate, vedere la sezione [Conversioni esplicite](~/_csharplang/spec/conversions.md#explicit-conversions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md). Per informazioni su come definire una conversione personalizzata del tipo esplicito o implicito, vedere [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md).

### <a name="other-usages-of-"></a>Altri utilizzi di ()

È possibile usare le parentesi anche per [chiamare un metodo oppure richiamare un delegato](member-access-operators.md#invocation-operator-).

Le parentesi possono essere usate anche per specificare l'ordine in cui valutare le operazioni in un'espressione. Per altre informazioni, vedere [Operatori C#](index.md).

## <a name="typeof-operator"></a>Operatore typeof

L'operatore `typeof` ottiene l'istanza <xref:System.Type?displayProperty=nameWithType> per un tipo. L'argomento dell'operatore `typeof` deve essere il nome o il parametro di un tipo, come illustrato nell'esempio seguente:

[!code-csharp-interactive[typeof operator](snippets/TypeTestingAndConversionOperators.cs#TypeOf)]

È possibile usare l'operatore `typeof` anche con tipi generici non associati. Il nome di un tipo generico non associato deve contenere il numero appropriato di virgole, ovvero una in meno rispetto al numero di parametri del tipo. L'esempio seguente illustra l'uso dell'operatore `typeof` con un tipo generico non associato:

[!code-csharp-interactive[typeof unbound generic](snippets/TypeTestingAndConversionOperators.cs#TypeOfUnboundGeneric)]

Un'espressione non può essere un argomento dell'operatore `typeof`. Per ottenere <xref:System.Type?displayProperty=nameWithType> l'istanza per il tipo di <xref:System.Object.GetType%2A?displayProperty=nameWithType> runtime di un risultato dell'espressione, utilizzare il metodo .

### <a name="type-testing-with-the-typeof-operator"></a>Test del tipo con l'operatore `typeof`

Usare l'operatore `typeof` per controllare se il tipo di runtime del risultato dell'espressione corrisponde esattamente a un determinato tipo. L'esempio seguente illustra la differenza tra il controllo del tipo eseguito con l'operatore `typeof` e il controllo del tipo con l'[operatore is](#is-operator):

[!code-csharp[typeof vs is](snippets/TypeTestingAndConversionOperators.cs#TypeCheckWithTypeOf)]

## <a name="operator-overloadability"></a>Overload degli operatori

Gli `is` `as`operatori `typeof` , e non possono essere sottoposti a overload.

Un tipo definito dall'utente non può eseguire l'overload dell'operatore `()`, ma può definire conversioni di tipi personalizzate che possano essere eseguite da un'espressione cast. Per altre informazioni, vedere [Operatori di conversione definiti dall'utente](user-defined-conversion-operators.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Operatore is](~/_csharplang/spec/expressions.md#the-is-operator)
- [Operatore as](~/_csharplang/spec/expressions.md#the-as-operator)
- [Espressioni cast](~/_csharplang/spec/expressions.md#cast-expressions)
- [Operatore typeof](~/_csharplang/spec/expressions.md#the-typeof-operator)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Come eseguire il cast in modo sicuro utilizzando criteri di ricerca e gli operatori is e as](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [Generics in .NET](../../../standard/generics/index.md)
