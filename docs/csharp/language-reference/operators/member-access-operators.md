---
title: Operatori di accesso ai membri - Riferimenti per C#
description: Informazioni sugli operatori C# che è possibile usare per accedere ai membri di tipo.
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: 5ff5e68fbce320076e6d18e9e139b418a15bba77
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924634"
---
# <a name="member-access-operators-c-reference"></a>Operatori di accesso ai membri (Riferimenti per C#)

Quando si accede a un membro di tipo, è possibile utilizzare gli operatori seguenti:

- [`.` (accesso ai membri)](#member-access-operator-): per accedere a un membro di uno spazio dei nomi o di tipo
- [`[]` (accesso agli elementi della matrice o a indicizzatori)](#indexer-operator-): per accedere a un elemento della matrice o a un indicizzatore di tipo
- [`?.` e `?[]` (operatori condizionali Null)](#null-conditional-operators--and-): per eseguire un'operazione di accesso a un membro o a un elemento solo se un operando è diverso da Null
- [`()` (chiamata)](#invocation-operator-): per chiamare un metodo a cui si accede o per richiamare un delegato

## <a name="member-access-operator-"></a>Operatore di accesso ai membri .

Si usa il token `.` per accedere a un membro di uno spazio dei nomi o di un tipo, come illustrano gli esempi seguenti:

- Usare `.` per accedere a uno spazio dei nomi annidato in uno spazio dei nomi, come illustra l'esempio seguente di [direttiva `using`](../keywords/using-directive.md):

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- Usare `.` per formare un *nome qualificato* per accedere a un tipo in uno spazio dei nomi, come illustra il codice seguente:

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  Usare una [direttiva `using`](../keywords/using-directive.md) per rendere facoltativo l'uso di nomi qualificati.

- Usare `.` per accedere ai [membri dei tipi](../../programming-guide/classes-and-structs/index.md#members), statici e non statici, come illustra il codice seguente:

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

È anche possibile usare `.` per accedere a un [metodo di estensione](../../programming-guide/classes-and-structs/extension-methods.md).

## <a name="indexer-operator-"></a>Operatore indicizzatore []

Le parentesi quadre `[]` vengono in genere usate per l'accesso agli elementi matrice, indicizzatore o puntatore.

### <a name="array-access"></a>Accesso a matrici

Nell'esempio seguente viene illustrato come accedere agli elementi matrice:

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

Se un indice di matrice è fuori dai limiti della dimensione corrispondente di una matrice, viene generata un'eccezione <xref:System.IndexOutOfRangeException>.

Come illustrato nell'esempio precedente, si usano le parentesi quadre anche per dichiarare un tipo di matrice o creare un'istanza di matrice.

Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/arrays/index.md).

### <a name="indexer-access"></a>Accesso all'indicizzatore

Nell'esempio seguente viene usato il tipo .NET <xref:System.Collections.Generic.Dictionary%602> per dimostrare l'accesso all'indicizzatore:

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

Gli indicizzatori consentono di indicizzare le istanze di un tipo definito dall'utente con modalità simili a quelle dell'indicizzazione della matrice. A differenza degli indici di matrice, che devono essere valori interi, gli argomenti dell'indicizzatore possono essere dichiarati con qualsiasi tipo.

Per altre informazioni sugli indicizzatori, vedere [Indicizzatori](../../programming-guide/indexers/index.md).

### <a name="other-usages-of-"></a>Altri utilizzi di []

Per informazioni sull'accesso agli elementi del puntatore, vedere la sezione [Operatore [] (accesso agli elementi del puntatore)](pointer-related-operators.md#pointer-element-access-operator-) dell'articolo [Operatori relativi al puntatore](pointer-related-operators.md).

Le parentesi quadre possono anche essere usate per specificare [attributi](../../programming-guide/concepts/attributes/index.md):

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a>Operatori condizionali Null ?. e ?[]

Un operatore condizionale Null, disponibile in C# 6 e nelle versioni successive, applica un'operazione di accesso ai membri, `?.`, o di accesso a elementi, `?[]`, al relativo operando solo se l'operando restituisce un valore diverso da Null. Se l'operando restituisce `null`, il risultato dell'applicazione dell'operatore è `null`. L'operatore di accesso ai membri condizionale Null `?.` è anche noto come operatore Elvis.

Gli operatori condizionali Null causano corto circuiti. Vale a dire, se un'operazione in una catena di operazioni condizionali di accesso a un membro o a un elemento restituisce `null`, l'esecuzione delle altre operazioni della catena viene interrotta. Nell'esempio seguente `B` non viene valutato se `A` restituisce `null` e `C` non viene valutato se `A` oppure `B` restituisce `null`:

```csharp
A?.B?.Do(C);
A?.B?[C];
```

Nell'esempio seguente viene illustrato l'uso degli operatori `?.` e `?[]`:

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

L'esempio precedente mostra anche l'utilizzo dell'[operatore Null di coalescenza](null-coalescing-operator.md). È possibile utilizzare l'operatore Null di coalescenza per creare un'espressione alternativa da valutare nel caso in cui il risultato dell'operazione condizionale Null sia `null`.

### <a name="thread-safe-delegate-invocation"></a>Chiamata a delegati thread-safe

Usare l'operatore `?.` per controllare se un delegato è diverso da Null e richiamarlo in un modo thread-safe, ad esempio, quando si [genera un evento](../../../standard/events/how-to-raise-and-consume-events.md), come illustrato nel codice seguente:

```csharp
PropertyChanged?.Invoke(…)
```

Il codice equivale alla versione C# 5 o precedente del codice seguente:

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a>Operatore di chiamata ()

Usare le parentesi, `()`, per chiamare un [metodo](../../programming-guide/classes-and-structs/methods.md) oppure richiamare un [delegato](../../programming-guide/delegates/index.md).

L'esempio seguente illustra come chiamare un metodo, con o senza argomenti, e come richiamare un delegato:

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

Le parentesi si usano anche per richiamare un [costruttore](../../programming-guide/classes-and-structs/constructors.md) con l'operatore [`new`](new-operator.md).

### <a name="other-usages-of-"></a>Altri utilizzi di ()

È anche possibile usare le parentesi per specificare l'ordine in cui valutare le operazioni in un'espressione. Per altre informazioni, vedere [Operatori C#](index.md).

Anche le [espressioni cast](type-testing-and-cast.md#cast-operator-), che eseguono conversioni dei tipi esplicite, usano le parentesi.

## <a name="operator-overloadability"></a>Overload degli operatori

Gli operatori `.` e `()` non possono essere sottoposti a overload. Anche l'operatore `[]` viene considerato un operatore che non supporta l'overload. Per il supporto dell'indicizzazione con tipi definiti dall'utente, usare gli [indicizzatori](../../programming-guide/indexers/index.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Accesso ai membri](~/_csharplang/spec/expressions.md#member-access)
- [Accesso a elementi](~/_csharplang/spec/expressions.md#element-access)
- [Operatori condizionali Null](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [Espressioni di chiamata](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [ ?? (operatore null-coalescing)](null-coalescing-operator.md)
- [Operatore ::](namespace-alias-qualifier.md)
