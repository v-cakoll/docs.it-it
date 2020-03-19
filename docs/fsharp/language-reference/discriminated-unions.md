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
# <a name="discriminated-unions"></a><span data-ttu-id="d2253-103">Unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="d2253-103">Discriminated Unions</span></span>

<span data-ttu-id="d2253-104">Le unioni discriminate forniscono supporto per i valori che possono essere uno di un numero di casi denominati, possibilmente ognuno con valori e tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="d2253-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="d2253-105">Le unioni discriminate sono utili per dati eterogenei; dati che possono avere casi speciali, inclusi casi validi e di errore; dati che variano nel tipo da un'istanza all'altra; e come alternativa per piccole gerarchie di oggetti.</span><span class="sxs-lookup"><span data-stu-id="d2253-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="d2253-106">Inoltre, le unioni discriminate ricorsive vengono utilizzate per rappresentare le strutture di dati della struttura ad albero.</span><span class="sxs-lookup"><span data-stu-id="d2253-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2253-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2253-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="d2253-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d2253-108">Remarks</span></span>

<span data-ttu-id="d2253-109">Le unioni discriminate sono simili ai tipi di unione in altre lingue, ma esistono differenze.</span><span class="sxs-lookup"><span data-stu-id="d2253-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="d2253-110">Come con un tipo di unione in C , o un tipo variant in Visual Basic, i dati archiviati nel valore non sono fissi. può essere una delle diverse opzioni distinte.</span><span class="sxs-lookup"><span data-stu-id="d2253-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="d2253-111">A differenza delle unioni in questi altri linguaggi, tuttavia, a ciascuna delle opzioni possibili viene assegnato un *identificatore di case*.</span><span class="sxs-lookup"><span data-stu-id="d2253-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="d2253-112">Gli identificatori di case sono nomi per i vari tipi possibili di valori che gli oggetti di questo tipo potrebbero essere; i valori sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d2253-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="d2253-113">Se i valori non sono presenti, il case è equivalente a un case di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d2253-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="d2253-114">Se sono presenti valori, ogni valore può essere un singolo valore di un tipo specificato o una tupla che aggrega più campi dello stesso tipo o di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="d2253-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="d2253-115">È possibile assegnare un nome a un singolo campo, ma il nome è facoltativo, anche se sono denominati altri campi nella stessa combinazione di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d2253-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="d2253-116">L'accessibilità per le unioni discriminate è `public`predefinita .</span><span class="sxs-lookup"><span data-stu-id="d2253-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="d2253-117">Si consideri, ad esempio, la seguente dichiarazione di un Shape type.</span><span class="sxs-lookup"><span data-stu-id="d2253-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="d2253-118">Il codice precedente dichiara un'unione discriminata Shape, che può avere valori di uno qualsiasi dei tre casi: Rectangle, Circle e Prism.</span><span class="sxs-lookup"><span data-stu-id="d2253-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="d2253-119">Ogni caso ha un diverso set di campi.</span><span class="sxs-lookup"><span data-stu-id="d2253-119">Each case has a different set of fields.</span></span> <span data-ttu-id="d2253-120">Il case Rectangle dispone di due `float`campi denominati, entrambi di tipo , che hanno i nomi width e length.</span><span class="sxs-lookup"><span data-stu-id="d2253-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="d2253-121">Il caso Circle ha un solo campo denominato, raggio.</span><span class="sxs-lookup"><span data-stu-id="d2253-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="d2253-122">Il caso Prism ha tre campi, due dei quali (larghezza e altezza) sono campi denominati.</span><span class="sxs-lookup"><span data-stu-id="d2253-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="d2253-123">I campi senza nome sono detti campi anonimi.</span><span class="sxs-lookup"><span data-stu-id="d2253-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="d2253-124">È possibile costruire oggetti fornendo valori per i campi denominati e anonimi in base agli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d2253-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="d2253-125">Questo codice mostra che è possibile utilizzare i campi denominati nell'inizializzazione oppure è possibile basarsi sull'ordinamento dei campi nella dichiarazione e fornire solo i valori per ogni campo a turno.</span><span class="sxs-lookup"><span data-stu-id="d2253-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="d2253-126">La chiamata `rect` al costruttore per nel codice precedente utilizza `circ` i campi denominati, ma la chiamata al costruttore per utilizza l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="d2253-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="d2253-127">È possibile combinare i campi ordinati e i `prism`campi denominati, come nella costruzione di .</span><span class="sxs-lookup"><span data-stu-id="d2253-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="d2253-128">Il `option` tipo è un'unione discriminata semplice nella libreria di base di F.</span><span class="sxs-lookup"><span data-stu-id="d2253-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="d2253-129">Il `option` tipo viene dichiarato come segue.</span><span class="sxs-lookup"><span data-stu-id="d2253-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="d2253-130">Il codice precedente specifica `Option` che il tipo è un'unione discriminata con due casi `Some` e `None`.</span><span class="sxs-lookup"><span data-stu-id="d2253-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="d2253-131">Il `Some` case ha un valore associato costituito da un campo `'a`anonimo il cui tipo è rappresentato dal parametro di tipo .</span><span class="sxs-lookup"><span data-stu-id="d2253-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="d2253-132">Il `None` caso non ha alcun valore associato.</span><span class="sxs-lookup"><span data-stu-id="d2253-132">The `None` case has no associated value.</span></span> <span data-ttu-id="d2253-133">Pertanto `option` il tipo specifica un tipo generico che ha un valore di qualche tipo o nessun valore.</span><span class="sxs-lookup"><span data-stu-id="d2253-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="d2253-134">Il `Option` tipo ha anche un `option`alias di tipo minuscolo, , che viene utilizzato più comunemente.</span><span class="sxs-lookup"><span data-stu-id="d2253-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="d2253-135">Gli identificatori di case possono essere utilizzati come costruttori per il tipo di unione discriminato.</span><span class="sxs-lookup"><span data-stu-id="d2253-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="d2253-136">Ad esempio, il codice seguente viene `option` utilizzato per creare valori del tipo.</span><span class="sxs-lookup"><span data-stu-id="d2253-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="d2253-137">Gli identificatori case vengono utilizzati anche nelle espressioni di criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d2253-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="d2253-138">In un'espressione di criteri di ricerca, vengono forniti identificatori per i valori associati ai singoli case.</span><span class="sxs-lookup"><span data-stu-id="d2253-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="d2253-139">Nel codice seguente, ad `x` esempio, viene fornito l'identificatore dato il valore associato alla distinzione tra maiuscole e minuscole `Some` del `option` tipo.</span><span class="sxs-lookup"><span data-stu-id="d2253-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="d2253-140">Nelle espressioni di criteri di ricerca, è possibile utilizzare i campi denominati per specificare corrispondenze di unione discriminate.</span><span class="sxs-lookup"><span data-stu-id="d2253-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="d2253-141">Per il tipo Shape dichiarato in precedenza, è possibile utilizzare i campi denominati come illustrato nel codice seguente per estrarre i valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="d2253-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

<span data-ttu-id="d2253-142">In genere, gli identificatori di case possono essere utilizzati senza qualificarli con il nome dell'unione.</span><span class="sxs-lookup"><span data-stu-id="d2253-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="d2253-143">Se si desidera che il nome sia sempre qualificato con il nome dell'unione, è possibile applicare l'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) alla definizione del tipo di unione.</span><span class="sxs-lookup"><span data-stu-id="d2253-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="d2253-144">Annullamento del wrapping delle unioni discriminateUnwrapping Discriminated Unions</span><span class="sxs-lookup"><span data-stu-id="d2253-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="d2253-145">Nelle unioni discriminate in F , vengono spesso usate nella modellazione di dominio per eseguire il wrapping di un singolo tipo.</span><span class="sxs-lookup"><span data-stu-id="d2253-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="d2253-146">È facile estrarre anche il valore sottostante tramite criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d2253-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="d2253-147">Non è necessario usare un'espressione di corrispondenza per un singolo caso:You don't need to use a match expression for a single case:</span><span class="sxs-lookup"><span data-stu-id="d2253-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

<span data-ttu-id="d2253-148">Questo concetto è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d2253-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

<span data-ttu-id="d2253-149">I criteri di ricerca sono consentiti anche direttamente nei parametri di funzione, pertanto è possibile annullare il wrapping di un singolo caso:Pattern matching is also also allowed directly in function parameters, so you can unwrap a single case there:</span><span class="sxs-lookup"><span data-stu-id="d2253-149">Pattern matching is also allowed directly in function parameters, so you can unwrap a single case there:</span></span>

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="d2253-150">Struct Union discriminate</span><span class="sxs-lookup"><span data-stu-id="d2253-150">Struct Discriminated Unions</span></span>

<span data-ttu-id="d2253-151">È inoltre possibile rappresentare le unioni discriminate come struct.</span><span class="sxs-lookup"><span data-stu-id="d2253-151">You can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="d2253-152">Questa operazione viene `[<Struct>]` eseguita con l'attributo .</span><span class="sxs-lookup"><span data-stu-id="d2253-152">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="d2253-153">Poiché si tratta di tipi di valore e non di tipi di riferimento, esistono considerazioni aggiuntive rispetto alle unioni discriminate di riferimento:Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span><span class="sxs-lookup"><span data-stu-id="d2253-153">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="d2253-154">Vengono copiati come tipi di valore e hanno la semantica del tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="d2253-154">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="d2253-155">Non è possibile usare una definizione di tipo ricorsivo con un'unione discriminata di struct multicase.</span><span class="sxs-lookup"><span data-stu-id="d2253-155">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="d2253-156">È necessario fornire nomi di case univoci per un'unione discriminata di struct multicase.</span><span class="sxs-lookup"><span data-stu-id="d2253-156">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="d2253-157">Utilizzo di unioni discriminate anziché gerarchie di oggettiUsing Discriminated Unions Instead of Object Hierarchies</span><span class="sxs-lookup"><span data-stu-id="d2253-157">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="d2253-158">È spesso possibile usare un'unione discriminata come alternativa più semplice a una gerarchia di oggetti di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d2253-158">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="d2253-159">Ad esempio, è possibile utilizzare l'unione `Shape` discriminata seguente anziché una classe base con tipi derivati per circle, square e così via.</span><span class="sxs-lookup"><span data-stu-id="d2253-159">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="d2253-160">Invece di un metodo virtuale per calcolare un'area o un perimetro, come si farebbe in un'implementazione orientata agli oggetti, è possibile usare la corrispondenza dei modelli per creare un ramo alle formule appropriate per calcolare queste quantità.</span><span class="sxs-lookup"><span data-stu-id="d2253-160">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="d2253-161">Nell'esempio seguente vengono utilizzate formule diverse per calcolare l'area, a seconda della forma.</span><span class="sxs-lookup"><span data-stu-id="d2253-161">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="d2253-162">L'output è il seguente:</span><span class="sxs-lookup"><span data-stu-id="d2253-162">The output is as follows:</span></span>

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="d2253-163">Utilizzo di unioni discriminate per strutture di dati ad alberoUsing Discriminated Unions for Tree Data Structures</span><span class="sxs-lookup"><span data-stu-id="d2253-163">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="d2253-164">Le unioni discriminate possono essere ricorsive, il che significa che l'unione stessa può essere inclusa nel tipo di uno o più casi.</span><span class="sxs-lookup"><span data-stu-id="d2253-164">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="d2253-165">Le unioni discriminate ricorsive possono essere utilizzate per creare strutture ad albero, che vengono utilizzate per modellare espressioni nei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="d2253-165">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="d2253-166">Nel codice seguente viene usata un'unione discriminata ricorsiva per creare una struttura di dati ad albero binaria.</span><span class="sxs-lookup"><span data-stu-id="d2253-166">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="d2253-167">L'unione è costituita da due casi, `Node`, ovvero un nodo `Tip`con un valore intero e sottoalberi sinistro e destro e , che termina la struttura ad albero.</span><span class="sxs-lookup"><span data-stu-id="d2253-167">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="d2253-168">Nel codice precedente, `resultSumTree` ha il valore 10.</span><span class="sxs-lookup"><span data-stu-id="d2253-168">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="d2253-169">Nella figura seguente viene `myTree`illustrata la struttura ad albero per .</span><span class="sxs-lookup"><span data-stu-id="d2253-169">The following illustration shows the tree structure for `myTree`.</span></span>

![Diagramma che mostra la struttura ad albero per myTree.](../media/discriminated-unions/tree-structure-mytree.png)

<span data-ttu-id="d2253-171">Le unioni discriminate funzionano bene se i nodi nella struttura ad albero sono eterogenei.</span><span class="sxs-lookup"><span data-stu-id="d2253-171">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="d2253-172">Nel codice seguente il `Expression` tipo rappresenta la struttura ad albero della sintassi astratta di un'espressione in un linguaggio di programmazione semplice che supporta l'addizione e la moltiplicazione di numeri e variabili.</span><span class="sxs-lookup"><span data-stu-id="d2253-172">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="d2253-173">Alcuni dei casi di unione non sono ricorsivi e rappresentano numeri (`Number`) o variabili (`Variable`).</span><span class="sxs-lookup"><span data-stu-id="d2253-173">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="d2253-174">Altri casi sono ricorsivi e`Add` rappresentano `Multiply`operazioni ( e ), in cui gli operandi sono anche espressioni.</span><span class="sxs-lookup"><span data-stu-id="d2253-174">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="d2253-175">La `Evaluate` funzione utilizza un'espressione di corrispondenza per elaborare in modo ricorsivo l'albero della sintassi.</span><span class="sxs-lookup"><span data-stu-id="d2253-175">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="d2253-176">Quando viene eseguito questo codice, il valore di `result` è 5.</span><span class="sxs-lookup"><span data-stu-id="d2253-176">When this code is executed, the value of `result` is 5.</span></span>

## <a name="members"></a><span data-ttu-id="d2253-177">Members</span><span class="sxs-lookup"><span data-stu-id="d2253-177">Members</span></span>

<span data-ttu-id="d2253-178">È possibile definire i membri delle unioni discriminate.</span><span class="sxs-lookup"><span data-stu-id="d2253-178">It is possible to define members on discriminated unions.</span></span> <span data-ttu-id="d2253-179">Nell'esempio seguente viene illustrato come definire una proprietà e implementare un'interfaccia:The following example shows how to define a property and implement an interface:</span><span class="sxs-lookup"><span data-stu-id="d2253-179">The following example shows how to define a property and implement an interface:</span></span>

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

## <a name="common-attributes"></a><span data-ttu-id="d2253-180">Attributi comuni</span><span class="sxs-lookup"><span data-stu-id="d2253-180">Common attributes</span></span>

<span data-ttu-id="d2253-181">I seguenti attributi sono comunemente visibili nelle unioni discriminate:</span><span class="sxs-lookup"><span data-stu-id="d2253-181">The following attributes are commonly seen in discriminated unions:</span></span>

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a><span data-ttu-id="d2253-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2253-182">See also</span></span>

- [<span data-ttu-id="d2253-183">Guida di riferimento al linguaggio F</span><span class="sxs-lookup"><span data-stu-id="d2253-183">F# Language Reference</span></span>](index.md)
