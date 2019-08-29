---
title: Unioni discriminate
description: Informazioni su come usare F# le unioni discriminate.
ms.date: 05/16/2016
ms.openlocfilehash: fa4f011a8d5fd6725a44e030b423e79244a18734
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106774"
---
# <a name="discriminated-unions"></a>Unioni discriminate

Le unioni discriminate forniscono supporto per i valori che possono essere uno dei diversi casi denominati, probabilmente ognuno con valori e tipi diversi. Le unioni discriminate sono utili per i dati eterogenei. dati che possono avere casi speciali, inclusi i casi di errore e validi. dati che variano in base al tipo da un'istanza a un'altra. e come alternativa per le gerarchie di oggetti di piccole dimensioni. Inoltre, le unioni discriminate ricorsive vengono utilizzate per rappresentare strutture di dati ad albero.

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a>Note

Le unioni discriminate sono simili ai tipi di Unione in altri linguaggi, ma vi sono differenze. Come per un tipo di Unione C++ in o un tipo variant in Visual Basic, i dati archiviati nel valore non sono corretti; può essere una delle diverse opzioni DISTINCT. A differenza delle unioni in questi altri linguaggi, tuttavia, a ciascuna delle possibili opzioni viene assegnato un *identificatore del case*. Gli identificatori del case sono nomi per i diversi tipi di valori possibili che possono essere gli oggetti di questo tipo. i valori sono facoltativi. Se i valori non sono presenti, il case è equivalente a un case di enumerazione. Se sono presenti valori, ogni valore può essere un singolo valore di un tipo specificato o una tupla che aggrega più campi dello stesso tipo o di tipi diversi. È possibile assegnare un nome a un singolo campo, ma il nome è facoltativo, anche se altri campi nello stesso caso sono denominati.

Per impostazione predefinita `public`, l'accessibilità per le unioni discriminate è.

Si consideri, ad esempio, la seguente dichiarazione di un tipo di forma.

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

Il codice precedente dichiara una forma unione discriminata, che può avere valori di uno dei tre casi seguenti: Rettangolo, cerchio e prisma. Ogni case ha un set di campi diverso. Il caso rettangolo presenta due campi denominati, entrambi `float`di tipo, che hanno i nomi Width e length. Il case Circle ha un solo campo denominato RADIUS. Il caso Prisma ha tre campi, due dei quali (larghezza e altezza) sono campi denominati. I campi senza nome vengono definiti campi anonimi.

Per costruire oggetti, è necessario fornire valori per i campi denominati e anonimi in base agli esempi seguenti.

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

Questo codice mostra che è possibile usare i campi denominati nell'inizializzazione oppure è possibile basarsi sull'ordinamento dei campi nella dichiarazione e fornire solo i valori per ogni campo a turno. La chiamata del costruttore `rect` per nel codice precedente usa i campi denominati, ma la chiamata `circ` del costruttore per USA l'ordinamento. È possibile combinare i campi ordinati e i campi denominati, come nella `prism`costruzione di.

Il `option` tipo è una semplice unione discriminata nella libreria F# principale. Il `option` tipo viene dichiarato come indicato di seguito.

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

Il codice precedente specifica che il tipo `Option` è un'unione discriminata con due case, `Some` e `None`. Al `Some` case è associato un valore costituito da un campo Anonimo il cui tipo è rappresentato dal parametro `'a`di tipo. Al `None` case non è associato alcun valore. In questo `option` modo, il tipo specifica un tipo generico che ha un valore di un tipo o nessun valore. Il tipo `Option` dispone anche di un alias di tipo `option`minuscolo,, che viene usato più di frequente.

Gli identificatori di case possono essere utilizzati come costruttori per il tipo di unione discriminata. Il codice seguente, ad esempio, viene usato per creare valori del `option` tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

Gli identificatori del case vengono usati anche nelle espressioni di criteri di ricerca. In un'espressione di criteri di ricerca, gli identificatori vengono forniti per i valori associati ai singoli case. Nel codice seguente, ad esempio, `x` è l'identificatore dato il valore associato `Some` al case del `option` tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

Nelle espressioni di criteri di ricerca è possibile usare campi denominati per specificare le corrispondenze di unione discriminata. Per il tipo di forma dichiarato in precedenza, è possibile utilizzare i campi denominati come illustrato nel codice seguente per estrarre i valori dei campi.

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

In genere, gli identificatori di case possono essere utilizzati senza qualificarli con il nome dell'Unione. Se si desidera che il nome sia sempre qualificato con il nome dell'Unione, è possibile applicare l'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) alla definizione del tipo di Unione.

### <a name="unwrapping-discriminated-unions"></a>Annullamento del wrapping di unioni discriminate

Nelle F# unioni discriminate vengono spesso utilizzate nella modellazione del dominio per il wrapping di un singolo tipo. È facile estrarre il valore sottostante anche tramite criteri di ricerca. Non è necessario usare un'espressione di corrispondenza per un singolo case:

```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

Questo concetto è illustrato nell'esempio seguente:

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

I criteri di ricerca sono consentiti anche direttamente nei parametri della funzione, pertanto è possibile annullare il wrapping di un singolo case:

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a>Unioni discriminate struct

È inoltre possibile rappresentare le unioni discriminate come struct.  Questa operazione viene eseguita con `[<Struct>]` l'attributo.

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

Poiché si tratta di tipi di valore e non di tipi di riferimento, sono presenti considerazioni aggiuntive rispetto alle unioni discriminate di riferimento:

1. Vengono copiati come tipi di valore e hanno una semantica del tipo di valore.
2. Non è possibile usare una definizione di tipo ricorsivo con un'unione discriminata di struct a più case.
3. È necessario fornire nomi di case univoci per un'unione discriminata di struct a più case.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>Utilizzo di unioni discriminate anziché di gerarchie di oggetti

È spesso possibile usare un'unione discriminata come alternativa più semplice a una gerarchia di oggetti di piccole dimensioni. Ad esempio, è possibile usare l'unione discriminata seguente al posto di `Shape` una classe di base con tipi derivati per Circle, Square e così via.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

Anziché un metodo virtuale per calcolare un'area o un perimetro, come si farebbe per un'implementazione orientata a oggetti, è possibile utilizzare criteri di ricerca per creare branch per le formule appropriate per calcolare tali quantità. Nell'esempio seguente vengono utilizzate formule diverse per calcolare l'area, a seconda della forma.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

L'output è indicato di seguito:

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>Utilizzo di unioni discriminate per strutture di dati ad albero

Le unioni discriminate possono essere ricorsive, vale a dire che l'Unione stessa può essere inclusa nel tipo di uno o più case. Le unioni discriminate ricorsive possono essere utilizzate per creare strutture ad albero, utilizzate per modellare espressioni nei linguaggi di programmazione. Nel codice seguente viene usata un'unione discriminata ricorsiva per creare una struttura di dati albero binaria. L'Unione è costituita da due `Node`case,, ovvero un nodo con un valore integer e sottoalberi sinistro e destro, e `Tip`, che termina l'albero.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

Nel codice precedente, `resultSumTree` il valore è 10. Nella figura seguente viene illustrata la struttura `myTree`ad albero di.

![Diagramma che mostra la struttura ad albero per l'albero.](../media/discriminated-unions/tree-structure-mytree.png)

Le unioni discriminate funzionano bene se i nodi della struttura ad albero sono eterogenei. Nel codice seguente, il tipo `Expression` rappresenta l'albero della sintassi astratta di un'espressione in un linguaggio di programmazione semplice che supporta l'aggiunta e la moltiplicazione di numeri e variabili. Alcuni case di Unione non sono ricorsivi e rappresentano numeri (`Number`) o variabili (`Variable`). Gli altri casi sono ricorsivi e rappresentano le operazioni`Add` ( `Multiply`e), in cui anche gli operandi sono espressioni. La `Evaluate` funzione usa un'espressione di corrispondenza per elaborare in modo ricorsivo l'albero della sintassi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

Quando viene eseguito questo codice, il valore di `result` è 5.

## <a name="members"></a>Members

È possibile definire i membri nelle unioni discriminate. Nell'esempio seguente viene illustrato come definire una proprietà e implementare un'interfaccia:

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

Gli attributi seguenti sono comunemente visualizzati nelle unioni discriminate:

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
