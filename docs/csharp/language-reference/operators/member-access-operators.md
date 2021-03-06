---
title: Operatori di accesso ai membri ed espressioni-riferimenti per C#
description: Informazioni sugli operatori C# che è possibile usare per accedere ai membri di tipo.
ms.date: 04/17/2020
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
- ^_CSharpKeyword
- .._CSharpKeyword
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
- ^ operator [C#]
- index from end operator [C#]
- hat operator [C#]
- .. operator [C#]
- range operator [C#]
ms.openlocfilehash: 59e01b17d78032714803629d503a92ba86a20fdc
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394648"
---
# <a name="member-access-operators-and-expressions-c-reference"></a>Operatori di accesso ai membri ed espressioni (riferimenti per C#)

Quando si accede a un membro di un tipo, è possibile utilizzare gli operatori e le espressioni seguenti:

- [ `.` (accesso ai membri)](#member-access-expression-): per accedere a un membro di uno spazio dei nomi o di un tipo
- [ `[]` (accesso all'elemento della matrice o all'indicizzatore)](#indexer-operator-): per accedere a un elemento di matrice o a un indicizzatore di tipo
- [ `?.` and `?[]` (operatori condizionali null)](#null-conditional-operators--and-): per eseguire un'operazione di accesso a un membro o a un elemento solo se un operando è non null
- [ `()` (chiamata)](#invocation-expression-): per chiamare un metodo a cui si accede o richiamare un delegato
- [ `^` (indice dalla fine)](#index-from-end-operator-): per indicare che la posizione dell'elemento è dalla fine di una sequenza
- [ `..` (intervallo)](#range-operator-): per specificare un intervallo di indici che è possibile usare per ottenere un intervallo di elementi di sequenza

## <a name="member-access-expression-"></a>Espressione di accesso ai membri.

Si usa il token `.` per accedere a un membro di uno spazio dei nomi o di un tipo, come illustrano gli esempi seguenti:

- Utilizzare `.` per accedere a uno spazio dei nomi annidato all'interno di uno spazio dei nomi, come illustrato nell'esempio seguente di una [ `using` direttiva](../keywords/using-directive.md) :

  [!code-csharp[nested namespaces](snippets/MemberAccessOperators.cs#NestedNamespace)]

- Usare `.` per formare un *nome qualificato* per accedere a un tipo in uno spazio dei nomi, come illustra il codice seguente:

  [!code-csharp[qualified name](snippets/MemberAccessOperators.cs#QualifiedName)]

  Usare una [ `using` direttiva](../keywords/using-directive.md) per rendere facoltativo l'uso di nomi qualificati.

- Usare `.` per accedere ai [membri dei tipi](../../programming-guide/classes-and-structs/index.md#members), statici e non statici, come illustra il codice seguente:

  [!code-csharp-interactive[type members](snippets/MemberAccessOperators.cs#TypeMemberAccess)]

È anche possibile usare `.` per accedere a un [metodo di estensione](../../programming-guide/classes-and-structs/extension-methods.md).

## <a name="indexer-operator-"></a>Operatore indicizzatore []

Le parentesi quadre `[]` vengono in genere usate per l'accesso agli elementi matrice, indicizzatore o puntatore.

### <a name="array-access"></a>Accesso a matrici

Nell'esempio seguente viene illustrato come accedere agli elementi matrice:

[!code-csharp-interactive[array access](snippets/MemberAccessOperators.cs#Arrays)]

Se un indice di matrice è fuori dai limiti della dimensione corrispondente di una matrice, viene generata un'eccezione <xref:System.IndexOutOfRangeException>.

Come illustrato nell'esempio precedente, si usano le parentesi quadre anche per dichiarare un tipo di matrice o creare un'istanza di matrice.

Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/arrays/index.md).

### <a name="indexer-access"></a>Accesso all'indicizzatore

Nell'esempio seguente viene usato il <xref:System.Collections.Generic.Dictionary%602> tipo .NET per dimostrare l'accesso dell'indicizzatore:

[!code-csharp-interactive[indexer access](snippets/MemberAccessOperators.cs#Indexers)]

Gli indicizzatori consentono di indicizzare le istanze di un tipo definito dall'utente con modalità simili a quelle dell'indicizzazione della matrice. A differenza degli indici di matrice, che devono essere numeri interi, i parametri dell'indicizzatore possono essere dichiarati come di qualsiasi tipo.

Per altre informazioni sugli indicizzatori, vedere [Indicizzatori](../../programming-guide/indexers/index.md).

### <a name="other-usages-of-"></a>Altri utilizzi di []

Per informazioni sull'accesso agli elementi del puntatore, vedere la sezione [Operatore [] (accesso agli elementi del puntatore)](pointer-related-operators.md#pointer-element-access-operator-) dell'articolo [Operatori relativi al puntatore](pointer-related-operators.md).

Le parentesi quadre possono anche essere usate per specificare [attributi](../../programming-guide/concepts/attributes/index.md):

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a>Operatori condizionali Null ?. e ?[]

Disponibile in C# 6 e versioni successive, un operatore condizionale null applica un'operazione di [accesso ai membri](#member-access-expression-), `?.` o [l'accesso all'elemento](#indexer-operator-), `?[]` , all'operando solo se tale operando restituisce un valore non null. in caso contrario, restituisce `null` . Cioè

- Se `a` restituisce `null` , il risultato di `a?.x` o `a?[x]` è `null` .
- Se `a` restituisce un valore diverso da null, il risultato di `a?.x` o `a?[x]` è uguale al risultato di `a.x` o `a[x]` , rispettivamente.

  > [!NOTE]
  > Se `a.x` o `a[x]` genera un'eccezione `a?.x` o genera `a?[x]` la stessa eccezione per un valore diverso da null `a` . Se, ad esempio, `a` è un'istanza di matrice non null ed `x` è all'esterno dei limiti di `a` , `a?[x]` genera un' <xref:System.IndexOutOfRangeException> .

Gli operatori condizionali Null causano corto circuiti. Vale a dire, se un'operazione in una catena di operazioni condizionali di accesso a un membro o a un elemento restituisce `null`, l'esecuzione delle altre operazioni della catena viene interrotta. Nell'esempio seguente `B` non viene valutato se `A` restituisce `null` e `C` non viene valutato se `A` oppure `B` restituisce `null`:

```csharp
A?.B?.Do(C);
A?.B?[C];
```

Nell'esempio seguente viene illustrato l'uso degli operatori `?.` e `?[]`:

[!code-csharp-interactive[null-conditional operators](snippets/MemberAccessOperators.cs#NullConditional)]

Nell'esempio precedente viene inoltre usato l' [operatore `??` ](null-coalescing-operator.md) di Unione null per specificare un'espressione alternativa da valutare se il risultato di un'operazione condizionale null è `null` .

Se `a.x` o `a[x]` è di un tipo di valore non Nullable `T` `a?.x` oppure `a?[x]` è del [tipo di valore Nullable](../builtin-types/nullable-value-types.md) corrispondente `T?` . Se è necessaria un'espressione di tipo `T` , applicare l'operatore di Unione null `??` a un'espressione condizionale null, come illustrato nell'esempio seguente:

[!code-csharp-interactive[null-conditional with null-coalescing](snippets/MemberAccessOperators.cs#NullConditionalWithNullCoalescing)]

Nell'esempio precedente, se non si usa l' `??` operatore, `numbers?.Length < 2` restituisce `false` quando `numbers` è `null` .

L'operatore di accesso ai membri condizionale Null `?.` è anche noto come operatore Elvis.

> [!NOTE]
> In C# 8, l' [operatore che perdona i valori null](null-forgiving.md) termina l'elenco delle operazioni condizionali null precedenti. Ad esempio, l'espressione `x?.y!.z` viene analizzata come `(x?.y)!.z` . A causa di questa interpretazione, `z` viene valutato anche se `x` è `null` , che può produrre un <xref:System.NullReferenceException> .

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

Si tratta di un metodo thread-safe per assicurarsi che venga richiamato solo un valore non null `handler` . Poiché le istanze di delegati non sono modificabili, nessun thread può modificare l'oggetto a cui fa riferimento la `handler` variabile locale. In particolare, se il codice eseguito da un altro thread annulla la sottoscrizione dell' `PropertyChanged` evento e `PropertyChanged` diventa `null` prima che `handler` venga richiamato, l'oggetto a cui fa riferimento `handler` rimane inalterato. L' `?.` operatore valuta l'operando sinistro non più di una volta, garantendo che non possa essere modificato in `null` dopo essere stato verificato come non null.

## <a name="invocation-expression-"></a>Espressione di chiamata ()

Usare le parentesi, `()`, per chiamare un [metodo](../../programming-guide/classes-and-structs/methods.md) oppure richiamare un [delegato](../../programming-guide/delegates/index.md).

L'esempio seguente illustra come chiamare un metodo, con o senza argomenti, e come richiamare un delegato:

[!code-csharp-interactive[invocation with ()](snippets/MemberAccessOperators.cs#Invocation)]

Le parentesi si usano anche per richiamare un [costruttore](../../programming-guide/classes-and-structs/constructors.md) con l'operatore [`new`](new-operator.md).

### <a name="other-usages-of-"></a>Altri utilizzi di ()

È anche possibile usare le parentesi per specificare l'ordine in cui valutare le operazioni in un'espressione. Per altre informazioni, vedere [Operatori C#](index.md).

Anche le [espressioni cast](type-testing-and-cast.md#cast-expression), che eseguono conversioni dei tipi esplicite, usano le parentesi.

## <a name="index-from-end-operator-"></a>Index from End Operator ^

Disponibile in C# 8,0 e versioni successive, l' `^` operatore indica la posizione dell'elemento alla fine di una sequenza. Per una sequenza di lunghezza `length` , `^n` punta all'elemento con offset `length - n` dall'inizio di una sequenza. Ad esempio, `^1` punta all'ultimo elemento di una sequenza e `^length` punta al primo elemento di una sequenza.

[!code-csharp[index from end](snippets/MemberAccessOperators.cs#IndexFromEnd)]

Come illustrato nell'esempio precedente, Expression `^e` è del <xref:System.Index?displayProperty=nameWithType> tipo. Nell'espressione `^e` , il risultato di `e` deve essere convertibile in modo implicito in `int` .

`^`Per creare un intervallo di indici, è anche possibile usare l'operatore con l' [operatore Range](#range-operator-) . Per altre informazioni, vedere [indici e intervalli](../../tutorials/ranges-indexes.md).

## <a name="range-operator-"></a>Operatore di intervallo..

Disponibile in C# 8,0 e versioni successive, l' `..` operatore specifica l'inizio e la fine di un intervallo di indici come operandi. L'operando sinistro è un inizio *inclusivo* di un intervallo. L'operando destro è una fine *esclusiva* di un intervallo. Uno degli operandi può essere un indice dall'inizio o dalla fine di una sequenza, come illustrato nell'esempio seguente:

[!code-csharp[range examples](snippets/MemberAccessOperators.cs#Ranges)]

Come illustrato nell'esempio precedente, Expression `a..b` è del <xref:System.Range?displayProperty=nameWithType> tipo. Nell'espressione `a..b` i risultati di `a` e `b` devono essere convertibili in modo implicito in `int` o <xref:System.Index> .

È possibile omettere gli operandi dell' `..` operatore per ottenere un intervallo aperto:

- `a..`equivale a`a..^0`
- `..b`equivale a`0..b`
- `..`equivale a`0..^0`

[!code-csharp[ranges with omitted operands](snippets/MemberAccessOperators.cs#RangesOptional)]

Per altre informazioni, vedere [indici e intervalli](../../tutorials/ranges-indexes.md).

## <a name="operator-overloadability"></a>Overload degli operatori

`.` `()` `^` `..` Non è possibile eseguire l'overload degli operatori,, e. Anche l'operatore `[]` viene considerato un operatore che non supporta l'overload. Per il supporto dell'indicizzazione con tipi definiti dall'utente, usare gli [indicizzatori](../../programming-guide/indexers/index.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Accesso ai membri](~/_csharplang/spec/expressions.md#member-access)
- [Accesso a elementi](~/_csharplang/spec/expressions.md#element-access)
- [Operatori condizionali Null](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [Espressioni di chiamata](~/_csharplang/spec/expressions.md#invocation-expressions)

Per ulteriori informazioni sugli indici e sugli intervalli, vedere la [Nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-8.0/ranges.md).

## <a name="see-also"></a>Vedi anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [?? (null-coalescing operator)](null-coalescing-operator.md) ?? (operatore null-coalescing)
- [:: (operatore)](namespace-alias-qualifier.md)
