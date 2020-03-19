---
title: Unioni discriminate
description: Informazioni su come usare le unioni discriminate di F.
ms.date: 05/16/2016
ms.openlocfilehash: 539e2843c0bbc8c5ac9c0597ffc5443f8cd127f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400218"
---
# <a name="discriminated-unions"></a>Unioni discriminate

Le unioni discriminate forniscono supporto per i valori che possono essere uno di un numero di casi denominati, possibilmente ognuno con valori e tipi diversi. Le unioni discriminate sono utili per dati eterogenei; dati che possono avere casi speciali, inclusi casi validi e di errore; dati che variano nel tipo da un'istanza all'altra; e come alternativa per piccole gerarchie di oggetti. Inoltre, le unioni discriminate ricorsive vengono utilizzate per rappresentare le strutture di dati della struttura ad albero.

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a>Osservazioni

Le unioni discriminate sono simili ai tipi di unione in altre lingue, ma esistono differenze. Come con un tipo di unione in C , o un tipo variant in Visual Basic, i dati archiviati nel valore non sono fissi. può essere una delle diverse opzioni distinte. A differenza delle unioni in questi altri linguaggi, tuttavia, a ciascuna delle opzioni possibili viene assegnato un *identificatore di case*. Gli identificatori di case sono nomi per i vari tipi possibili di valori che gli oggetti di questo tipo potrebbero essere; i valori sono facoltativi. Se i valori non sono presenti, il case è equivalente a un case di enumerazione. Se sono presenti valori, ogni valore può essere un singolo valore di un tipo specificato o una tupla che aggrega più campi dello stesso tipo o di tipi diversi. È possibile assegnare un nome a un singolo campo, ma il nome è facoltativo, anche se sono denominati altri campi nella stessa combinazione di maiuscole e minuscole.

L'accessibilità per le unioni discriminate è `public`predefinita .

Si consideri, ad esempio, la seguente dichiarazione di un Shape type.

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

Il codice precedente dichiara un'unione discriminata Shape, che può avere valori di uno qualsiasi dei tre casi: Rectangle, Circle e Prism. Ogni caso ha un diverso set di campi. Il case Rectangle dispone di due `float`campi denominati, entrambi di tipo , che hanno i nomi width e length. Il caso Circle ha un solo campo denominato, raggio. Il caso Prism ha tre campi, due dei quali (larghezza e altezza) sono campi denominati. I campi senza nome sono detti campi anonimi.

È possibile costruire oggetti fornendo valori per i campi denominati e anonimi in base agli esempi seguenti.

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

Questo codice mostra che è possibile utilizzare i campi denominati nell'inizializzazione oppure è possibile basarsi sull'ordinamento dei campi nella dichiarazione e fornire solo i valori per ogni campo a turno. La chiamata `rect` al costruttore per nel codice precedente utilizza `circ` i campi denominati, ma la chiamata al costruttore per utilizza l'ordinamento. È possibile combinare i campi ordinati e i `prism`campi denominati, come nella costruzione di .

Il `option` tipo è un'unione discriminata semplice nella libreria di base di F. Il `option` tipo viene dichiarato come segue.

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

Il codice precedente specifica `Option` che il tipo è un'unione discriminata con due casi `Some` e `None`. Il `Some` case ha un valore associato costituito da un campo `'a`anonimo il cui tipo è rappresentato dal parametro di tipo . Il `None` caso non ha alcun valore associato. Pertanto `option` il tipo specifica un tipo generico che ha un valore di qualche tipo o nessun valore. Il `Option` tipo ha anche un `option`alias di tipo minuscolo, , che viene utilizzato più comunemente.

Gli identificatori di case possono essere utilizzati come costruttori per il tipo di unione discriminato. Ad esempio, il codice seguente viene `option` utilizzato per creare valori del tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

Gli identificatori case vengono utilizzati anche nelle espressioni di criteri di ricerca. In un'espressione di criteri di ricerca, vengono forniti identificatori per i valori associati ai singoli case. Nel codice seguente, ad `x` esempio, viene fornito l'identificatore dato il valore associato alla distinzione tra maiuscole e minuscole `Some` del `option` tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

Nelle espressioni di criteri di ricerca, è possibile utilizzare i campi denominati per specificare corrispondenze di unione discriminate. Per il tipo Shape dichiarato in precedenza, è possibile utilizzare i campi denominati come illustrato nel codice seguente per estrarre i valori dei campi.

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

In genere, gli identificatori di case possono essere utilizzati senza qualificarli con il nome dell'unione. Se si desidera che il nome sia sempre qualificato con il nome dell'unione, è possibile applicare l'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) alla definizione del tipo di unione.

### <a name="unwrapping-discriminated-unions"></a>Annullamento del wrapping delle unioni discriminateUnwrapping Discriminated Unions

Nelle unioni discriminate in F , vengono spesso usate nella modellazione di dominio per eseguire il wrapping di un singolo tipo. È facile estrarre anche il valore sottostante tramite criteri di ricerca. Non è necessario usare un'espressione di corrispondenza per un singolo caso:You don't need to use a match expression for a single case:

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

Questo concetto è illustrato nell'esempio seguente:

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

I criteri di ricerca sono consentiti anche direttamente nei parametri di funzione, pertanto è possibile annullare il wrapping di un singolo caso:Pattern matching is also also allowed directly in function parameters, so you can unwrap a single case there:

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a>Struct Union discriminate

È inoltre possibile rappresentare le unioni discriminate come struct.  Questa operazione viene `[<Struct>]` eseguita con l'attributo .

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

Poiché si tratta di tipi di valore e non di tipi di riferimento, esistono considerazioni aggiuntive rispetto alle unioni discriminate di riferimento:Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:

1. Vengono copiati come tipi di valore e hanno la semantica del tipo di valore.
2. Non è possibile usare una definizione di tipo ricorsivo con un'unione discriminata di struct multicase.
3. È necessario fornire nomi di case univoci per un'unione discriminata di struct multicase.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>Utilizzo di unioni discriminate anziché gerarchie di oggettiUsing Discriminated Unions Instead of Object Hierarchies

È spesso possibile usare un'unione discriminata come alternativa più semplice a una gerarchia di oggetti di piccole dimensioni. Ad esempio, è possibile utilizzare l'unione `Shape` discriminata seguente anziché una classe base con tipi derivati per circle, square e così via.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

Invece di un metodo virtuale per calcolare un'area o un perimetro, come si farebbe in un'implementazione orientata agli oggetti, è possibile usare la corrispondenza dei modelli per creare un ramo alle formule appropriate per calcolare queste quantità. Nell'esempio seguente vengono utilizzate formule diverse per calcolare l'area, a seconda della forma.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

L'output è il seguente:

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>Utilizzo di unioni discriminate per strutture di dati ad alberoUsing Discriminated Unions for Tree Data Structures

Le unioni discriminate possono essere ricorsive, il che significa che l'unione stessa può essere inclusa nel tipo di uno o più casi. Le unioni discriminate ricorsive possono essere utilizzate per creare strutture ad albero, che vengono utilizzate per modellare espressioni nei linguaggi di programmazione. Nel codice seguente viene usata un'unione discriminata ricorsiva per creare una struttura di dati ad albero binaria. L'unione è costituita da due casi, `Node`, ovvero un nodo `Tip`con un valore intero e sottoalberi sinistro e destro e , che termina la struttura ad albero.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

Nel codice precedente, `resultSumTree` ha il valore 10. Nella figura seguente viene `myTree`illustrata la struttura ad albero per .

![Diagramma che mostra la struttura ad albero per myTree.](../media/discriminated-unions/tree-structure-mytree.png)

Le unioni discriminate funzionano bene se i nodi nella struttura ad albero sono eterogenei. Nel codice seguente il `Expression` tipo rappresenta la struttura ad albero della sintassi astratta di un'espressione in un linguaggio di programmazione semplice che supporta l'addizione e la moltiplicazione di numeri e variabili. Alcuni dei casi di unione non sono ricorsivi e rappresentano numeri (`Number`) o variabili (`Variable`). Altri casi sono ricorsivi e`Add` rappresentano `Multiply`operazioni ( e ), in cui gli operandi sono anche espressioni. La `Evaluate` funzione utilizza un'espressione di corrispondenza per elaborare in modo ricorsivo l'albero della sintassi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

Quando viene eseguito questo codice, il valore di `result` è 5.

## <a name="members"></a>Members

È possibile definire i membri delle unioni discriminate. Nell'esempio seguente viene illustrato come definire una proprietà e implementare un'interfaccia:The following example shows how to define a property and implement an interface:

```fsharp
open System

type IPrintable =
    abstract Print: unit -> unit

type Shape =
    | Circle of float
    | EquilateralTriangle of float
    | Square of float
    | Rectangle of float * float

    member this.Area =
        match this with
        | Circle r -> 2.0 * Math.PI * r
        | EquilateralTriangle s -> s * s * sqrt 3.0 / 4.0
        | Square s -> s * s
        | Rectangle(l, w) -> l * w

    interface IPrintable with
        member this.Print () =
            match this with
            | Circle r -> printfn "Circle with radius %f" r
            | EquilateralTriangle s -> printfn "Equilateral Triangle of side %f" s
            | Square s -> printfn "Square with side %f" s
            | Rectangle(l, w) -> printfn "Rectangle with length %f and width %f" l w
```

## <a name="common-attributes"></a>Attributi comuni

I seguenti attributi sono comunemente visibili nelle unioni discriminate:

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento al linguaggio F](index.md)
