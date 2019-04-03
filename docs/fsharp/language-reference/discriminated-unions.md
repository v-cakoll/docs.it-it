---
title: Unioni discriminate
description: Informazioni su come usare F# unioni discriminate.
ms.date: 05/16/2016
ms.openlocfilehash: 9d3f423d068df1c43791919b0d71ca82304ae85e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821426"
---
# <a name="discriminated-unions"></a>Unioni discriminate

Le unioni discriminate offrono supporto per i valori che possono essere uno dei numerosi casi denominati, ognuno con diversi valori e tipi potenzialmente. Le unioni discriminate sono utili per dati eterogenei dati con casi speciali, tra cui validi e casi di errore. dati che variano nel tipo da un'istanza a un altro. e come alternativa per le gerarchie di oggetti piccoli. Inoltre, discriminate ricorsive unioni vengono usate per rappresentare strutture di dati ad albero.

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a>Note

Le unioni discriminate sono simili ai tipi di unione in altri linguaggi, ma esistono differenze. Come con un tipo di unione in C++ o un tipo variant in Visual Basic, i dati memorizzati nel valore non sono fisso; può essere una delle molte opzioni distinte. A differenza delle unioni in questi altri linguaggi, tuttavia, per ognuna delle possibili opzioni viene fornito un *identificatore di case*. Gli identificatori di case sono nomi per i vari tipi di valori possibili che possono essere oggetti di questo tipo; i valori sono facoltativi. Se non sono presenti valori, il caso è equivalente a un case di enumerazione. Se sono presenti valori, ogni valore può essere un singolo valore di un tipo specificato o una tupla che aggrega più campi dei tipi uguali o diversi. È possibile assegnare un nome a un singolo campo, ma il nome è facoltativo, anche se gli altri campi in caso analogo sono denominati.

Per impostazione predefinita l'accessibilità per le unioni discriminate `public`.

Ad esempio, si consideri la seguente dichiarazione di un tipo di forma.

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

Il codice precedente viene dichiarata un'unione discriminata Shape, che può accettare valori di uno qualsiasi dei tre casi: Rettangolo, cerchio e prisma. Ogni case dispone di un set di campi diverso. Il caso rettangolo dispone di due denominato i campi, entrambi di tipo `float`, che hanno i nomi larghezza e lunghezza. Il caso cerchio dispone di un unico campo denominato, radius. Il caso prisma dispone di tre campi, due dei quali (larghezza e altezza) vengono denominati i campi. I campi senza nome sono detti campi anonimi.

Gli oggetti vengono costruiti fornendo valori per i campi denominati e anonimi seguendo gli esempi seguenti.

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

Questo codice viene illustrato che è possibile usare i campi denominati nell'inizializzazione oppure affidarsi all'ordinamento dei campi nella dichiarazione è sufficiente fornire i valori per ogni campo, a sua volta. La chiamata al costruttore per `rect` nel codice precedente utilizza campi denominati, ma la chiamata al costruttore per `circ` utilizza l'ordinamento. È possibile combinare i campi ordinati e i campi denominati, come nella costruzione di `prism`.

Il `option` il tipo è un'unione discriminata semplice nella F# libreria di base. Il `option` tipo è dichiarato come indicato di seguito.

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

Il codice precedente specifica che il tipo `Option` è un'unione discriminata con due casi `Some` e `None`. Il `Some` case ha un valore associato che è costituito da un campo anonimo il cui tipo è rappresentato dal parametro di tipo `'a`. Il `None` case non presenta valori associati. In questo modo il `option` tipo specifica un tipo generico che presenta un valore di un tipo o nessun valore. Il tipo `Option` ha anche un alias di tipo minuscolo, `option`, vale a dire più comunemente usato.

Gli identificatori di case possono essere utilizzati come costruttori per il tipo di unione discriminata. Ad esempio, il codice seguente viene utilizzato per creare valori del `option` tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

Gli identificatori di case vengono inoltre utilizzati nelle espressioni dei criteri. In un'espressione di corrispondenza, vengono forniti identificatori per i valori associati a singoli case. Ad esempio, nel codice seguente, `x` è l'identificatore associato il valore è associato il `Some` case del `option` tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

Nelle espressioni dei criteri, è possibile utilizzare campi denominati per specificare corrispondenze di unione discriminate. Per il tipo Shape dichiarato in precedenza, è possibile usare i campi denominati, come illustrato nel codice seguente per estrarre i valori dei campi.

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

In genere, gli identificatori di case possono essere utilizzati senza qualifica il nome dell'unione. Se si desidera che il nome venga sempre qualificato con il nome dell'unione, è possibile applicare il [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attributo alla definizione del tipo di unione.

### <a name="unwrapping-discriminated-unions"></a>Rimozione del wrapping e le unioni discriminate

In F# unioni discriminate vengono spesso utilizzate nella modellazione di dominio per il wrapping di un singolo tipo. È facile estrarre il valore sottostante tramite criteri di ricerca nonché. Non è necessario usare un'espressione di corrispondenza per un singolo case:

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

Criteri di ricerca sono inoltre consentita direttamente nei parametri della funzione, quindi è possibile annullare il wrapping di un singolo case:

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a>Unioni discriminate di struct

A partire da F# 4.1, è anche possibile rappresentare le unioni discriminate di struct.  Questa operazione viene eseguita con il `[<Struct>]` attributo.

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

Poiché queste sono tipi valore e non fanno riferimento ai tipi, esistono extra unioni discriminate considerazioni confrontati con riferimento:

1. Essi vengono copiate come tipi di valore e hanno una semantica di tipo valore.
2. È possibile usare una definizione di tipo ricorsive con uno struct multicase Union le unioni.
3. È necessario fornire nomi univoci di case per uno struct multicase Union le unioni.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>Utilizzo di unioni discriminate invece di gerarchie di oggetti

È spesso possibile utilizzare un'unione discriminata come alternativa più semplice a una gerarchia di oggetti piccoli. Ad esempio, l'unione discriminata seguente potrebbe essere utilizzato invece di un `Shape` classe base che dispone di tipi derivati per cerchi, quadrati e così via.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

Invece di un metodo virtuale per calcolare un'area o perimetrale, come si utilizzerebbe in un'implementazione orientata agli oggetti, è possibile usare criteri di ricerca di rami per formule appropriate per calcolare queste quantità. Nell'esempio seguente vengono utilizzate formule diverse per calcolare l'area, a seconda della forma.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

L'output è indicato di seguito:

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>Utilizzo di unioni discriminate per strutture di dati di struttura ad albero

Le unioni discriminate possono essere ricorsive, vale a dire che l'unione stessa può essere incluso nel tipo di uno o più case. Le unioni discriminate possono essere utilizzate per creare strutture ad albero, che vengono usati per modellare espressioni nei linguaggi di programmazione ricorsive. Nel codice seguente, discriminata ricorsiva union consente di creare una struttura di dati ad albero binario. L'unione è costituito da due casi `Node`, che è un nodo con un valore integer e sottoalberi destro e sinistro, e `Tip`, che termina l'albero.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

Nel codice precedente, `resultSumTree` ha valore 10. La figura seguente mostra la struttura ad albero `myTree`.

![Diagramma che mostra la struttura ad albero di mytree.](../media/discriminated-unions/tree-structure-mytree.png)

Le unioni discriminate funzionano bene se i nodi dell'albero sono eterogenei. Nel codice seguente, il tipo `Expression` rappresenta l'albero sintattico astratto di un'espressione in un semplice linguaggio di programmazione che supporta l'addizione e moltiplicazione di numeri e variabili. Alcuni case di unione non sono ricorsivi e rappresentano numeri (`Number`) o variabili (`Variable`). Altri case sono ricorsivi e rappresentano operazioni (`Add` e `Multiply`), in cui anche gli operandi sono espressioni. Il `Evaluate` funzione viene utilizzata un'espressione di corrispondenza per elaborare in modo ricorsivo l'albero della sintassi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

Quando viene eseguito questo codice, il valore di `result` è 5.

## <a name="common-attributes"></a>Attributi comuni

Gli attributi seguenti sono presente comunemente nelle unioni discriminate:

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* `[Struct]`

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)