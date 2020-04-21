---
title: Operatori ed espressioni di accesso ai membri - Informazioni di riferimento su C
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
ms.openlocfilehash: 4e213c92ae08edd8d537017e474c33200cb4c22c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738729"
---
# <a name="member-access-operators-and-expressions-c-reference"></a>Operatori ed espressioni di accesso ai membri (riferimenti per C

Quando si accede a un membro di tipo, è possibile utilizzare gli operatori e le espressioni seguenti:You can use the following operators and expressions when you access a type member:

- (accesso ai membri): per accedere a un membro di uno spazio dei nomi o di un tipo [ `.` ](#member-access-expression-)
- [(elemento matrice o accesso all'indicizzatore): per accedere a un elemento di matrice o a un indicizzatore di tipo `[]` ](#indexer-operator-)
- e (operatori null-conditional) : per eseguire un'operazione di accesso a un membro o a un elemento solo se un operando non è null [ `?.` `?[]` ](#null-conditional-operators--and-)
- (chiamata) : per chiamare un metodo a cui si accede o richiamare un delegato [ `()` ](#invocation-expression-)
- (indice dalla fine) : per indicare che la posizione dell'elemento è dalla fine di una sequenza [ `^` ](#index-from-end-operator-)
- (intervallo) : per specificare un intervallo di indici che è possibile utilizzare per ottenere un intervallo di elementi di sequenza [ `..` ](#range-operator-)

## <a name="member-access-expression-"></a>Espressione di accesso ai membri .

Si usa il token `.` per accedere a un membro di uno spazio dei nomi o di un tipo, come illustrano gli esempi seguenti:

- Utilizzare `.` per accedere a uno spazio dei nomi annidato all'interno di uno spazio dei nomi, come illustrato nell'esempio seguente di una [ `using` direttiva:Use](../keywords/using-directive.md) to access a nested namespace within a namespace, as the following example of a directive shows:

  [!code-csharp[nested namespaces](snippets/MemberAccessOperators.cs#NestedNamespace)]

- Usare `.` per formare un *nome qualificato* per accedere a un tipo in uno spazio dei nomi, come illustra il codice seguente:

  [!code-csharp[qualified name](snippets/MemberAccessOperators.cs#QualifiedName)]

  Utilizzare una [ `using` direttiva](../keywords/using-directive.md) per rendere facoltativo l'utilizzo di nomi qualificati.

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

Nell'esempio seguente viene <xref:System.Collections.Generic.Dictionary%602> utilizzato il tipo .NET per illustrare l'accesso all'indicizzatore:The following example uses the .NET type to demonstrate indexer access:

[!code-csharp-interactive[indexer access](snippets/MemberAccessOperators.cs#Indexers)]

Gli indicizzatori consentono di indicizzare le istanze di un tipo definito dall'utente con modalità simili a quelle dell'indicizzazione della matrice. A differenza degli indici di matrice, che devono essere integer, i parametri dell'indicizzatore possono essere dichiarati di qualsiasi tipo.

Per altre informazioni sugli indicizzatori, vedere [Indicizzatori](../../programming-guide/indexers/index.md).

### <a name="other-usages-of-"></a>Altri utilizzi di []

Per informazioni sull'accesso agli elementi del puntatore, vedere la sezione [Operatore [] (accesso agli elementi del puntatore)](pointer-related-operators.md#pointer-element-access-operator-) dell'articolo [Operatori relativi al puntatore](pointer-related-operators.md).

Le parentesi quadre possono anche essere usate per specificare [attributi](../../programming-guide/concepts/attributes/index.md):

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a>Operatori condizionali Null ?. e ?[]

Disponibile in C, 6 e versioni successive, un `?.`operatore null-condizionale applica un [accesso ai membri](#member-access-expression-), , o accesso [all'elemento](#indexer-operator-), `?[]`operazione all'operando solo se tale operando restituisce non null; in caso `null`contrario, restituisce . Cioè

- Se `a` restituisce `null`, il `a?.x` `a?[x]` risultato di o è `null`.
- Se `a` restituisce non null, il `a?.x` `a?[x]` risultato di o `a.x` è `a[x]`uguale al risultato di o , rispettivamente.

  > [!NOTE]
  > Se `a.x` `a[x]` o genera un'eccezione `a?.x` o `a?[x]` la stessa `a`eccezione per non null . Se, ad `a` esempio, se è `x` un'istanza di `a`matrice `a?[x]` non <xref:System.IndexOutOfRangeException>null e si trova all'esterno dei limiti di , verrà generato un'eccezione .

Gli operatori condizionali Null causano corto circuiti. Vale a dire, se un'operazione in una catena di operazioni condizionali di accesso a un membro o a un elemento restituisce `null`, l'esecuzione delle altre operazioni della catena viene interrotta. Nell'esempio seguente `B` non viene valutato se `A` restituisce `null` e `C` non viene valutato se `A` oppure `B` restituisce `null`:

```csharp
A?.B?.Do(C);
A?.B?[C];
```

Nell'esempio seguente viene illustrato l'uso degli operatori `?.` e `?[]`:

[!code-csharp-interactive[null-conditional operators](snippets/MemberAccessOperators.cs#NullConditional)]

Nell'esempio precedente viene inoltre utilizzato `null`l'operatore [ `??` null-coalescing](null-coalescing-operator.md) per specificare un'espressione alternativa da valutare nel caso in cui il risultato di un'operazione null-conditional sia .

Se `a.x` `a[x]` o è di un tipo `T` `a?.x` di `a?[x]` valore non nullable o è del tipo `T?`di [valore nullable](../builtin-types/nullable-value-types.md) corrispondente. Se è necessaria un'espressione di tipo `T`, applicare `??` l'operatore null-coalescing a un'espressione null-condizionale, come illustrato nell'esempio seguente:

[!code-csharp-interactive[null-conditional with null-coalescing](snippets/MemberAccessOperators.cs#NullConditionalWithNullCoalescing)]

Nell'esempio precedente, se non si `??` utilizza `numbers?.Length < 2` l'operatore `numbers` `null`, restituisce `false` quando è .

L'operatore di accesso ai membri condizionale Null `?.` è anche noto come operatore Elvis.

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

Si tratta di un modo thread-safe per `handler` garantire che venga richiamato solo un non null. Poiché le istanze dei delegati non sono modificabili, `handler` nessun thread può modificare il valore a cui fa riferimento la variabile locale. In particolare, se il codice eseguito da `PropertyChanged` un `PropertyChanged` altro `null` `handler` thread annulla la sottoscrizione all'evento e diventa before viene richiamato, il valore a `handler` cui viene fatto riferimento rimane invariato. L'operatore `?.` valuta l'operando di sinistra non più di una `null` volta, garantendo che non possa essere modificato dopo essere stato verificato come non null.

## <a name="invocation-expression-"></a>Espressione di chiamata ()

Usare le parentesi, `()`, per chiamare un [metodo](../../programming-guide/classes-and-structs/methods.md) oppure richiamare un [delegato](../../programming-guide/delegates/index.md).

L'esempio seguente illustra come chiamare un metodo, con o senza argomenti, e come richiamare un delegato:

[!code-csharp-interactive[invocation with ()](snippets/MemberAccessOperators.cs#Invocation)]

Le parentesi si usano anche per richiamare un [costruttore](../../programming-guide/classes-and-structs/constructors.md) con l'operatore [`new`](new-operator.md).

### <a name="other-usages-of-"></a>Altri utilizzi di ()

È anche possibile usare le parentesi per specificare l'ordine in cui valutare le operazioni in un'espressione. Per altre informazioni, vedere [Operatori C#](index.md).

Anche le [espressioni cast](type-testing-and-cast.md#cast-expression), che eseguono conversioni dei tipi esplicite, usano le parentesi.

## <a name="index-from-end-operator-"></a>Indice dall'operatore finale

Disponibile in C , 8.0 `^` e versioni successive, l'operatore indica la posizione dell'elemento dalla fine di una sequenza. Per una sequenza di lunghezza `length`, `^n` punta all'elemento con offset `length - n` dall'inizio di una sequenza. Ad esempio, `^1` punta all'ultimo elemento `^length` di una sequenza e al primo elemento di una sequenza.

[!code-csharp[index from end](snippets/MemberAccessOperators.cs#IndexFromEnd)]

Come illustrato nell'esempio `^e` precedente, <xref:System.Index?displayProperty=nameWithType> expression è del tipo. In `^e`expression , `e` il risultato di deve `int`essere convertibile in modo implicito in .

È inoltre possibile `^` utilizzare l'operatore con l'operatore [di intervallo](#range-operator-) per creare un intervallo di indici. Per ulteriori informazioni, consultate [Indici e intervalli.](../../tutorials/ranges-indexes.md)

## <a name="range-operator-"></a>Operatore di intervallo ..

Disponibile in C , 8.0 `..` e versioni successive, l'operatore specifica l'inizio e la fine di un intervallo di indici come operandi. L'operando di sinistra è un inizio *inclusivo* di un intervallo. L'operando di destra è *un'estremità esclusiva* di un intervallo. Uno degli operandi può essere un indice dall'inizio o dalla fine di una sequenza, come illustrato nell'esempio seguente:Either of operands can be an index from the start or from the end of a sequence, as the following example shows:

[!code-csharp[range examples](snippets/MemberAccessOperators.cs#Ranges)]

Come illustrato nell'esempio `a..b` precedente, <xref:System.Range?displayProperty=nameWithType> expression è del tipo. In `a..b`expression , `a` i `b` risultati di e devono `int` <xref:System.Index>essere convertibili in modo implicito in o .

È possibile omettere uno qualsiasi degli operandi dell'operatore `..` per ottenere un intervallo aperto:

- `a..`equivale a`a..^0`
- `..b`equivale a`0..b`
- `..`equivale a`0..^0`

[!code-csharp[ranges with omitted operands](snippets/MemberAccessOperators.cs#RangesOptional)]

Per ulteriori informazioni, consultate [Indici e intervalli.](../../tutorials/ranges-indexes.md)

## <a name="operator-overloadability"></a>Overload degli operatori

Gli `.` `()`operatori `^`, `..` , e non possono essere sottoposti a overload. Anche l'operatore `[]` viene considerato un operatore che non supporta l'overload. Per il supporto dell'indicizzazione con tipi definiti dall'utente, usare gli [indicizzatori](../../programming-guide/indexers/index.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Accesso ai membri](~/_csharplang/spec/expressions.md#member-access)
- [Accesso a elementi](~/_csharplang/spec/expressions.md#element-access)
- [Operatori condizionali Null](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [Espressioni di chiamata](~/_csharplang/spec/expressions.md#invocation-expressions)

Per ulteriori informazioni su indici e intervalli, vedere la nota della [proposta di feature.](~/_csharplang/proposals/csharp-8.0/ranges.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [?? (null-coalescing operator)](null-coalescing-operator.md) ?? (operatore null-coalescing)
- [:: (operatore)](namespace-alias-qualifier.md)
