---
title: Unioni discriminate (F#)
description: Informazioni su come utilizzare F# unioni discriminate.
ms.date: 05/16/2016
ms.openlocfilehash: 06d6c154790f659c0c7ff73290357ab50a134362
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43788123"
---
# <a name="discriminated-unions"></a><span data-ttu-id="ad563-103">Unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="ad563-103">Discriminated Unions</span></span>

<span data-ttu-id="ad563-104">Le unioni discriminate offrono supporto per i valori che possono essere uno dei numerosi casi denominati, ognuno con diversi valori e tipi potenzialmente.</span><span class="sxs-lookup"><span data-stu-id="ad563-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="ad563-105">Le unioni discriminate sono utili per dati eterogenei dati con casi speciali, tra cui validi e casi di errore. dati che variano nel tipo da un'istanza a un altro. e come alternativa per le gerarchie di oggetti piccoli.</span><span class="sxs-lookup"><span data-stu-id="ad563-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="ad563-106">Inoltre, discriminate ricorsive unioni vengono usate per rappresentare strutture di dati ad albero.</span><span class="sxs-lookup"><span data-stu-id="ad563-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="ad563-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad563-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="ad563-108">Note</span><span class="sxs-lookup"><span data-stu-id="ad563-108">Remarks</span></span>

<span data-ttu-id="ad563-109">Le unioni discriminate sono simili ai tipi di unione in altri linguaggi, ma esistono differenze.</span><span class="sxs-lookup"><span data-stu-id="ad563-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="ad563-110">Come con un tipo di unione in C++ o un tipo variant in Visual Basic, i dati memorizzati nel valore non sono fisso; può essere una delle molte opzioni distinte.</span><span class="sxs-lookup"><span data-stu-id="ad563-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="ad563-111">A differenza delle unioni in questi altri linguaggi, tuttavia, per ognuna delle possibili opzioni viene fornito un *identificatore di case*.</span><span class="sxs-lookup"><span data-stu-id="ad563-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="ad563-112">Gli identificatori di case sono nomi per i vari tipi di valori possibili che possono essere oggetti di questo tipo; i valori sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="ad563-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="ad563-113">Se non sono presenti valori, il caso è equivalente a un case di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ad563-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="ad563-114">Se sono presenti valori, ogni valore può essere un singolo valore di un tipo specificato o una tupla che aggrega più campi dei tipi uguali o diversi.</span><span class="sxs-lookup"><span data-stu-id="ad563-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="ad563-115">È possibile assegnare un nome a un singolo campo, ma il nome è facoltativo, anche se gli altri campi in caso analogo sono denominati.</span><span class="sxs-lookup"><span data-stu-id="ad563-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="ad563-116">Per impostazione predefinita l'accessibilità per le unioni discriminate `public`.</span><span class="sxs-lookup"><span data-stu-id="ad563-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="ad563-117">Ad esempio, si consideri la seguente dichiarazione di un tipo di forma.</span><span class="sxs-lookup"><span data-stu-id="ad563-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="ad563-118">Il codice precedente viene dichiarata un'unione discriminata Shape, che può accettare valori di uno qualsiasi dei tre casi: rettangolo, cerchio e prisma.</span><span class="sxs-lookup"><span data-stu-id="ad563-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="ad563-119">Ogni case dispone di un set di campi diverso.</span><span class="sxs-lookup"><span data-stu-id="ad563-119">Each case has a different set of fields.</span></span> <span data-ttu-id="ad563-120">Il caso rettangolo dispone di due denominato i campi, entrambi di tipo `float`, che hanno i nomi larghezza e lunghezza.</span><span class="sxs-lookup"><span data-stu-id="ad563-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="ad563-121">Il caso cerchio dispone di un unico campo denominato, radius.</span><span class="sxs-lookup"><span data-stu-id="ad563-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="ad563-122">Il caso prisma dispone di tre campi, due dei quali (larghezza e altezza) vengono denominati i campi.</span><span class="sxs-lookup"><span data-stu-id="ad563-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="ad563-123">I campi senza nome sono detti campi anonimi.</span><span class="sxs-lookup"><span data-stu-id="ad563-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="ad563-124">Gli oggetti vengono costruiti fornendo valori per i campi denominati e anonimi seguendo gli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="ad563-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="ad563-125">Questo codice viene illustrato che è possibile usare i campi denominati nell'inizializzazione oppure affidarsi all'ordinamento dei campi nella dichiarazione è sufficiente fornire i valori per ogni campo, a sua volta.</span><span class="sxs-lookup"><span data-stu-id="ad563-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="ad563-126">La chiamata al costruttore per `rect` nel codice precedente utilizza campi denominati, ma la chiamata al costruttore per `circ` utilizza l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ad563-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="ad563-127">È possibile combinare i campi ordinati e i campi denominati, come nella costruzione di `prism`.</span><span class="sxs-lookup"><span data-stu-id="ad563-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="ad563-128">Il `option` tipo è un'unione discriminata semplice nella libreria di base F#.</span><span class="sxs-lookup"><span data-stu-id="ad563-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="ad563-129">Il `option` tipo è dichiarato come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ad563-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="ad563-130">Il codice precedente specifica che il tipo `Option` è un'unione discriminata con due casi `Some` e `None`.</span><span class="sxs-lookup"><span data-stu-id="ad563-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="ad563-131">Il `Some` case ha un valore associato che è costituito da un campo anonimo il cui tipo è rappresentato dal parametro di tipo `'a`.</span><span class="sxs-lookup"><span data-stu-id="ad563-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="ad563-132">Il `None` case non presenta valori associati.</span><span class="sxs-lookup"><span data-stu-id="ad563-132">The `None` case has no associated value.</span></span> <span data-ttu-id="ad563-133">In questo modo il `option` tipo specifica un tipo generico che presenta un valore di un tipo o nessun valore.</span><span class="sxs-lookup"><span data-stu-id="ad563-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="ad563-134">Il tipo `Option` ha anche un alias di tipo minuscolo, `option`, vale a dire più comunemente usato.</span><span class="sxs-lookup"><span data-stu-id="ad563-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="ad563-135">Gli identificatori di case possono essere utilizzati come costruttori per il tipo di unione discriminata.</span><span class="sxs-lookup"><span data-stu-id="ad563-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="ad563-136">Ad esempio, il codice seguente viene utilizzato per creare valori del `option` tipo.</span><span class="sxs-lookup"><span data-stu-id="ad563-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="ad563-137">Gli identificatori di case vengono inoltre utilizzati nelle espressioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="ad563-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="ad563-138">In un'espressione di corrispondenza, vengono forniti identificatori per i valori associati a singoli case.</span><span class="sxs-lookup"><span data-stu-id="ad563-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="ad563-139">Ad esempio, nel codice seguente, `x` è l'identificatore associato il valore è associato il `Some` case del `option` tipo.</span><span class="sxs-lookup"><span data-stu-id="ad563-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="ad563-140">Nelle espressioni dei criteri, è possibile utilizzare campi denominati per specificare corrispondenze di unione discriminate.</span><span class="sxs-lookup"><span data-stu-id="ad563-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="ad563-141">Per il tipo Shape dichiarato in precedenza, è possibile usare i campi denominati, come illustrato nel codice seguente per estrarre i valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="ad563-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

<span data-ttu-id="ad563-142">In genere, gli identificatori di case possono essere utilizzati senza qualifica il nome dell'unione.</span><span class="sxs-lookup"><span data-stu-id="ad563-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="ad563-143">Se si desidera che il nome venga sempre qualificato con il nome dell'unione, è possibile applicare il [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attributo alla definizione del tipo di unione.</span><span class="sxs-lookup"><span data-stu-id="ad563-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="ad563-144">Rimozione del wrapping e le unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="ad563-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="ad563-145">Nelle unioni discriminate F# vengono spesso utilizzati nella modellazione di dominio per il wrapping di un singolo tipo.</span><span class="sxs-lookup"><span data-stu-id="ad563-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="ad563-146">È facile estrarre il valore sottostante tramite criteri di ricerca nonché.</span><span class="sxs-lookup"><span data-stu-id="ad563-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="ad563-147">Non è necessario usare un'espressione di corrispondenza per un singolo case:</span><span class="sxs-lookup"><span data-stu-id="ad563-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

<span data-ttu-id="ad563-148">Questo concetto è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ad563-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="ad563-149">Unioni discriminate di struct</span><span class="sxs-lookup"><span data-stu-id="ad563-149">Struct Discriminated Unions</span></span>

<span data-ttu-id="ad563-150">A partire da F# 4.1, è anche possibile rappresentare le unioni discriminate come struct.</span><span class="sxs-lookup"><span data-stu-id="ad563-150">Starting with F# 4.1, you can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="ad563-151">Questa operazione viene eseguita con il `[<Struct>]` attributo.</span><span class="sxs-lookup"><span data-stu-id="ad563-151">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="ad563-152">Poiché queste sono tipi valore e non fanno riferimento ai tipi, esistono extra unioni discriminate considerazioni confrontati con riferimento:</span><span class="sxs-lookup"><span data-stu-id="ad563-152">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="ad563-153">Essi vengono copiate come tipi di valore e hanno una semantica di tipo valore.</span><span class="sxs-lookup"><span data-stu-id="ad563-153">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="ad563-154">È possibile usare una definizione di tipo ricorsive con uno struct multicase Union le unioni.</span><span class="sxs-lookup"><span data-stu-id="ad563-154">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="ad563-155">È necessario fornire nomi univoci di case per uno struct multicase Union le unioni.</span><span class="sxs-lookup"><span data-stu-id="ad563-155">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="ad563-156">Utilizzo di unioni discriminate invece di gerarchie di oggetti</span><span class="sxs-lookup"><span data-stu-id="ad563-156">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="ad563-157">È spesso possibile utilizzare un'unione discriminata come alternativa più semplice a una gerarchia di oggetti piccoli.</span><span class="sxs-lookup"><span data-stu-id="ad563-157">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="ad563-158">Ad esempio, l'unione discriminata seguente potrebbe essere utilizzato invece di un `Shape` classe base che dispone di tipi derivati per cerchi, quadrati e così via.</span><span class="sxs-lookup"><span data-stu-id="ad563-158">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="ad563-159">Invece di un metodo virtuale per calcolare un'area o perimetrale, come si utilizzerebbe in un'implementazione orientata agli oggetti, è possibile usare criteri di ricerca di rami per formule appropriate per calcolare queste quantità.</span><span class="sxs-lookup"><span data-stu-id="ad563-159">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="ad563-160">Nell'esempio seguente vengono utilizzate formule diverse per calcolare l'area, a seconda della forma.</span><span class="sxs-lookup"><span data-stu-id="ad563-160">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="ad563-161">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ad563-161">The output is as follows:</span></span>

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="ad563-162">Utilizzo di unioni discriminate per strutture di dati di struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="ad563-162">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="ad563-163">Le unioni discriminate possono essere ricorsive, vale a dire che l'unione stessa può essere incluso nel tipo di uno o più case.</span><span class="sxs-lookup"><span data-stu-id="ad563-163">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="ad563-164">Le unioni discriminate possono essere utilizzate per creare strutture ad albero, che vengono usati per modellare espressioni nei linguaggi di programmazione ricorsive.</span><span class="sxs-lookup"><span data-stu-id="ad563-164">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="ad563-165">Nel codice seguente, discriminata ricorsiva union consente di creare una struttura di dati ad albero binario.</span><span class="sxs-lookup"><span data-stu-id="ad563-165">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="ad563-166">L'unione è costituito da due casi `Node`, che è un nodo con un valore integer e sottoalberi destro e sinistro, e `Tip`, che termina l'albero.</span><span class="sxs-lookup"><span data-stu-id="ad563-166">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="ad563-167">Nel codice precedente, `resultSumTree` ha valore 10.</span><span class="sxs-lookup"><span data-stu-id="ad563-167">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="ad563-168">La figura seguente mostra la struttura ad albero `myTree`.</span><span class="sxs-lookup"><span data-stu-id="ad563-168">The following illustration shows the tree structure for `myTree`.</span></span>

![Struttura ad albero di myTree](../media/TreeStructureDiagram.png)

<span data-ttu-id="ad563-170">Le unioni discriminate funzionano bene se i nodi dell'albero sono eterogenei.</span><span class="sxs-lookup"><span data-stu-id="ad563-170">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="ad563-171">Nel codice seguente, il tipo `Expression` rappresenta l'albero sintattico astratto di un'espressione in un semplice linguaggio di programmazione che supporta l'addizione e moltiplicazione di numeri e variabili.</span><span class="sxs-lookup"><span data-stu-id="ad563-171">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="ad563-172">Alcuni case di unione non sono ricorsivi e rappresentano numeri (`Number`) o variabili (`Variable`).</span><span class="sxs-lookup"><span data-stu-id="ad563-172">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="ad563-173">Altri case sono ricorsivi e rappresentano operazioni (`Add` e `Multiply`), in cui anche gli operandi sono espressioni.</span><span class="sxs-lookup"><span data-stu-id="ad563-173">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="ad563-174">Il `Evaluate` funzione viene utilizzata un'espressione di corrispondenza per elaborare in modo ricorsivo l'albero della sintassi.</span><span class="sxs-lookup"><span data-stu-id="ad563-174">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="ad563-175">Quando viene eseguito questo codice, il valore di `result` è 5.</span><span class="sxs-lookup"><span data-stu-id="ad563-175">When this code is executed, the value of `result` is 5.</span></span>

## <a name="common-attributes"></a><span data-ttu-id="ad563-176">Attributi comuni</span><span class="sxs-lookup"><span data-stu-id="ad563-176">Common Attributes</span></span>

<span data-ttu-id="ad563-177">Gli attributi seguenti sono presente comunemente nelle unioni discriminate:</span><span class="sxs-lookup"><span data-stu-id="ad563-177">The following attributes are commonly seen in discriminated unions:</span></span>

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* `[Struct]`

## <a name="see-also"></a><span data-ttu-id="ad563-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad563-178">See also</span></span>

- [<span data-ttu-id="ad563-179">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="ad563-179">F# Language Reference</span></span>](index.md)
