---
title: Unioni discriminate (F#)
description: "Informazioni sull'utilizzo di F # unioni discriminate."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 64c91410e284ee16036c4f51bd2247475a202a45
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="discriminated-unions"></a>Unioni discriminate

Unioni discriminate forniscono supporto per i valori che possono essere uno dei numerosi casi denominati, ognuno con diversi valori e tipi potenzialmente. Unioni discriminate sono utili per i dati eterogenei. dati che possono disporre di casi speciali, tra cui validi e casi di errore. dati variabili di tipo da un'istanza a un altro. e come alternativa per le gerarchie di oggetti piccoli. Inoltre, discriminata ricorsiva unioni vengono utilizzate per rappresentare strutture di dati.

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
type type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a>Note
Unioni discriminate sono simili ai tipi di unione in altri linguaggi, ma esistono alcune differenze. Come con un tipo di unione in C++ o un tipo variant in Visual Basic, i dati archiviati nel valore non sono fisso; può essere una delle numerose opzioni distinte. A differenza delle unioni in questi altri linguaggi, tuttavia, per ognuna delle possibili opzioni viene fornito un *identificatore case*. Gli identificatori di case sono nomi per i vari tipi di valori possibili che possono essere oggetti di questo tipo; i valori sono facoltativi. Se i valori non sono presenti, il caso è equivalente a un case di enumerazione. Se sono presenti i valori, ogni valore può essere un singolo valore di un tipo specificato o una tupla che consente di aggregare più campi di tipo stesso o diversi. A partire da F # 3.1, è possibile assegnare un nome a un singolo campo, ma il nome è facoltativo, anche se altri campi nel caso stesso nome.

Ad esempio, si consideri la seguente dichiarazione di un tipo di forma.

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

Il codice precedente viene dichiarata un'unione discriminata forma, che può avere valori di uno qualsiasi dei tre casi: rettangolo, cerchio e prisma. Ogni case è un set diverso di campi. Il rettangolo di case ha due denominato campi, entrambi di tipo `float`, con la larghezza di nomi e la lunghezza. Nel caso del cerchio è solo un campo denominato, radius. Il case prisma presenta tre campi, due dei quali (larghezza e altezza) sono denominati campi. Campi senza nome sono indicati come campi di tipo anonimi.

Per creare oggetti, che fornisce valori per i campi denominati e anonimi, in base negli esempi seguenti.

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

Questo codice viene illustrato che è possibile utilizzare i campi denominati durante l'inizializzazione o basarsi sull'ordine dei campi nella dichiarazione è sufficiente fornire i valori per ogni campo, a sua volta. La chiamata al costruttore per `rect` nel codice precedente utilizza i campi, ma la chiamata al costruttore per `circ` utilizza l'ordinamento. È possibile combinare i campi ordinati e denominata campi, come la costruzione di `prism`.

Il `option` tipo è un'unione discriminata semplice nella libreria di base F #. Il `option` tipo è dichiarato come indicato di seguito.

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

Il codice precedente specifica che il tipo `Option` è un'unione discriminata che dispone di due casi, `Some` e `None`. Il `Some` case ha un valore associato che è costituito da un campo anonimo il cui tipo è rappresentato dal parametro di tipo `'a`. Il `None` case non ha alcun valore associato. In questo modo il `option` tipo specifica un tipo generico che presenta un valore di un tipo o nessun valore. Il tipo `Option` dispone anche di un alias del tipo di lettere minuscole, `option`, vale a dire utilizzati più frequentemente.

Gli identificatori di case è utilizzabile i costruttori per il tipo di unione discriminato. Ad esempio, il codice seguente viene utilizzato per creare valori del `option` tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

Gli identificatori di case vengono inoltre utilizzati nelle espressioni dei criteri. In un modello di espressione di criteri, gli identificatori vengono forniti per i valori associati a singoli case. Ad esempio, nel codice seguente, `x` è l'identificatore specificato il valore di cui è associato il `Some` case del `option` tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

Nelle espressioni dei criteri, è possibile utilizzare i campi denominati per specificare le corrispondenze di unione discriminate. Per il tipo di forma che è stato dichiarato in precedenza, è possibile utilizzare i campi denominati, come mostrato nel codice seguente per estrarre i valori dei campi.

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

In genere, gli identificatori di case possono essere utilizzati senza qualifica con il nome dell'unione. Se si desidera il nome sempre essere qualificati con il nome dell'unione, è possibile applicare il [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attributo alla definizione del tipo di unione.

### <a name="unwrapping-discriminated-unions"></a>Rimozione del wrapping unioni discriminate

Nelle unioni discriminate di F # vengono spesso utilizzati nella modellazione di dominio per il wrapping di un solo tipo. È facile per estrarre il valore sottostante tramite anche i criteri di ricerca. Non è necessario utilizzare un'espressione di corrispondenza per un singolo case:
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

Questo concetto è illustrato nell'esempio seguente:

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a>Unioni discriminate struct

A partire da F # 4.1, si può anche rappresentare unioni discriminate come struct.  Questa operazione viene eseguita con il `[<Struct>]` attributo.

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

Poiché questi sono tipi di valore e tipi di riferimento non esistono aggiuntivo unioni discriminate considerazioni confrontati con riferimento:

1. Essi vengono copiati come tipi di valore e hanno una semantica di tipo valore.
2. È possibile utilizzare una definizione di tipo ricorsivo con una struttura multicase unione le unioni.
3. È necessario fornire nomi univoci di case per uno struct multicase unione le unioni.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>Utilizzo di unioni discriminate anziché gerarchie di oggetti
È spesso possibile utilizzare un'unione discriminata come un'alternativa più semplice per una gerarchia di oggetti piccoli. Ad esempio, è Impossibile utilizzare unione discriminata seguente invece di un `Shape` classe base che dispone di tipi derivati per cerchi, quadrati, e così via.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

Invece di un metodo virtuale per calcolare un'area o perimetrale, come si utilizzerebbe in un'implementazione orientata agli oggetti, è possibile utilizzare criteri di ricerca di diramazione formule appropriate per calcolare le quantità. Nell'esempio seguente, formule diverse vengono utilizzate per calcolare l'area, a seconda della forma.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

L'output è indicato di seguito:

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>Utilizzo di unioni discriminate per strutture di dati
Unioni discriminate possono essere ricorsivo, vale a dire che l'unione stessa può essere incluso nel tipo di uno o più case. Ricorsivo unioni discriminate possono essere utilizzate per creare strutture ad albero, che vengono usati per modellare espressioni nei linguaggi di programmazione. Nel codice seguente, discriminata ricorsiva unione viene utilizzata per creare una struttura di dati della struttura ad albero binaria. L'unione è costituito da due casi, `Node`, che è un nodo con un valore integer e sottoalberi destro e sinistro, e `Tip`, che termina l'albero.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

Nel codice precedente, `resultSumTree` ha valore 10. La figura seguente mostra la struttura ad albero `myTree`.

![Struttura ad albero per myTree](../media/TreeStructureDiagram.png)

Le unioni discriminate anche se i nodi nell'albero sono eterogenei. Nel codice seguente, il tipo `Expression` rappresenta l'albero sintattico astratto di un'espressione in un semplice linguaggio di programmazione che supporta l'addizione e moltiplicazione di numeri e variabili. Alcuni dei case di unione non sono ricorsivi e rappresentano numeri (`Number`) o variabili (`Variable`). Gli altri casi sono ricorsivi e rappresentano operazioni (`Add` e `Multiply`), in cui gli operandi sono anche le espressioni. Il `Evaluate` funzione viene utilizzata un'espressione di corrispondenza per elaborare in modo ricorsivo l'albero della sintassi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

Quando viene eseguito questo codice, il valore di `result` è 5.

## <a name="common-attributes"></a>Attributi comuni

Gli attributi seguenti sono presente comunemente nelle unioni discriminate:

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* `[Struct]` (F # 4.1 e versioni successive)

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)
