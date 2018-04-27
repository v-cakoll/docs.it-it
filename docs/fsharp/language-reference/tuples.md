---
title: Tuple (F#)
description: 'Informazioni su F # tupla, un raggruppamento di valori senza nome ma ordinati, tipi potenzialmente diversi.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 35069073-9a82-410f-8dea-912e2a152e6d
ms.openlocfilehash: e0a5e5eb08e13bd5cbe9f88a47d4cf4bba19ea22
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="tuples"></a><span data-ttu-id="a0253-104">Tuple</span><span class="sxs-lookup"><span data-stu-id="a0253-104">Tuples</span></span>

<span data-ttu-id="a0253-105">Oggetto *tupla* è un raggruppamento di valori senza nome ma ordinati, tipi potenzialmente diversi.</span><span class="sxs-lookup"><span data-stu-id="a0253-105">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="a0253-106">Tuple possono essere tipi di riferimento o struct.</span><span class="sxs-lookup"><span data-stu-id="a0253-106">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0253-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0253-107">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a><span data-ttu-id="a0253-108">Note</span><span class="sxs-lookup"><span data-stu-id="a0253-108">Remarks</span></span>
<span data-ttu-id="a0253-109">Ogni *elemento* nella sintassi precedente può essere qualsiasi espressione valida di F #.</span><span class="sxs-lookup"><span data-stu-id="a0253-109">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="a0253-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="a0253-110">Examples</span></span>
<span data-ttu-id="a0253-111">Sono esempi di tuple coppie, Triple e così via, di tipo stesso o diversi.</span><span class="sxs-lookup"><span data-stu-id="a0253-111">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="a0253-112">Alcuni esempi sono illustrati nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a0253-112">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a><span data-ttu-id="a0253-113">Recupero di singoli valori</span><span class="sxs-lookup"><span data-stu-id="a0253-113">Obtaining Individual Values</span></span>
<span data-ttu-id="a0253-114">È possibile utilizzare criteri di ricerca per accedere e assegnare i nomi degli elementi di tupla, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a0253-114">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="a0253-115">È anche possibile annullare una tupla tramite criteri di ricerca di fuori di un `match` espressione tramite `let` associazione:</span><span class="sxs-lookup"><span data-stu-id="a0253-115">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="a0253-116">O creare una serie di corrispondenza tuple come input per le funzioni:</span><span class="sxs-lookup"><span data-stu-id="a0253-116">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="a0253-117">Se è necessario un solo elemento della tupla, è possibile utilizzare il carattere jolly (carattere di sottolineatura) per evitare di creare un nuovo nome per un valore che non è necessario.</span><span class="sxs-lookup"><span data-stu-id="a0253-117">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="a0253-118">È inoltre semplice copia di elementi da una tupla di riferimento in una tupla di struct:</span><span class="sxs-lookup"><span data-stu-id="a0253-118">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="a0253-119">Le funzioni `fst` e `snd` (fare riferimento solo tuple) restituiscono il primo e secondo elemento di una tupla, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="a0253-119">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="a0253-120">Non vi è alcuna funzione predefinita che restituisce il terzo elemento di una tripla, ma è possibile scrivere facilmente uno come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a0253-120">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="a0253-121">In genere, si consiglia di utilizzare criteri di ricerca per accedere agli elementi di tupla individuali.</span><span class="sxs-lookup"><span data-stu-id="a0253-121">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="a0253-122">Utilizzo di tuple</span><span class="sxs-lookup"><span data-stu-id="a0253-122">Using Tuples</span></span>
<span data-ttu-id="a0253-123">Le tuple offrono un modo pratico per restituire più valori da una funzione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a0253-123">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="a0253-124">In questo esempio esegue la divisione di interi e restituisce il risultato arrotondato dell'operazione come primo membro di una coppia di tupla e il resto come secondo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="a0253-124">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="a0253-125">Tuple anche essere utilizzate come argomenti della funzione quando si desidera evitare il currying implicito gli argomenti della funzione è implicita la normale sintassi della funzione.</span><span class="sxs-lookup"><span data-stu-id="a0253-125">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="a0253-126">La sintassi comune per definire la funzione `let sum a b = a + b` consente di definire una funzione che è l'applicazione parziale del primo argomento della funzione, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a0253-126">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="a0253-127">L'utilizzo di una tupla come parametro Disattiva currying.</span><span class="sxs-lookup"><span data-stu-id="a0253-127">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="a0253-128">Per ulteriori informazioni, vedere "Applicazione parziale di argomenti" in [funzioni](functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="a0253-128">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="a0253-129">Nomi dei tipi di tupla</span><span class="sxs-lookup"><span data-stu-id="a0253-129">Names of Tuple Types</span></span>
<span data-ttu-id="a0253-130">Quando si scrive il nome di un tipo che è una tupla, utilizzare il `*` simbolo per separare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="a0253-130">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="a0253-131">Per una tupla costituita da un `int`, un `float`e un `string`, ad esempio `(10, 10.0, "ten")`, il tipo verrebbe scritto come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a0253-131">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="a0253-132">Interoperabilità con c# Tuple</span><span class="sxs-lookup"><span data-stu-id="a0253-132">Interoperation with C# Tuples</span></span>

<span data-ttu-id="a0253-133">C# 7.0 introdotti tuple per la lingua.</span><span class="sxs-lookup"><span data-stu-id="a0253-133">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="a0253-134">Le tuple in c# sono strutture e sono equivalenti alle tuple struct in F #.</span><span class="sxs-lookup"><span data-stu-id="a0253-134">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="a0253-135">Se è necessario interoperare con c#, è necessario utilizzare tuple struct.</span><span class="sxs-lookup"><span data-stu-id="a0253-135">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="a0253-136">Si tratta di un'operazione semplice.</span><span class="sxs-lookup"><span data-stu-id="a0253-136">This is easy to do.</span></span>  <span data-ttu-id="a0253-137">Si supponga, ad esempio, che è necessario passare una tupla a una classe c# e quindi utilizzare il risultato, che è anche una tupla:</span><span class="sxs-lookup"><span data-stu-id="a0253-137">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

<span data-ttu-id="a0253-138">Nel codice F #, è quindi possibile passare una tupla di struttura come parametro e utilizzare il risultato come una tupla di struct.</span><span class="sxs-lookup"><span data-stu-id="a0253-138">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="a0253-139">La conversione tra le tuple di riferimento e Struct Tuple</span><span class="sxs-lookup"><span data-stu-id="a0253-139">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="a0253-140">Le tuple di riferimento e Struct Tuples dispone di una rappresentazione sottostante completamente diversa, pertanto non sono convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="a0253-140">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="a0253-141">Ovvero, non verrà compilato il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a0253-141">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="a0253-142">È necessario criteri di corrispondenza per una tupla e costruire l'altro con le parti costitutive.</span><span class="sxs-lookup"><span data-stu-id="a0253-142">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="a0253-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a0253-143">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="a0253-144">Form compilato di tuple di riferimento</span><span class="sxs-lookup"><span data-stu-id="a0253-144">Compiled Form of Reference Tuples</span></span>
<span data-ttu-id="a0253-145">Questa sezione viene illustrato il formato di tuple quando essi è compilati.</span><span class="sxs-lookup"><span data-stu-id="a0253-145">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="a0253-146">Le informazioni riportate di seguito non sono necessaria per leggere, a meno che la destinazione di .NET Framework 3.5 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="a0253-146">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="a0253-147">Le tuple vengono compilate in oggetti di uno dei vari tipi generici, tutti i `System.Tuple`, che sono sottoposti a overload in grado o sul numero di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="a0253-147">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="a0253-148">Tipi di tupla vengono visualizzati in questo modulo quando visualizzati da un altro linguaggio, ad esempio c# o Visual Basic, o quando si utilizza uno strumento che non è a conoscenza dei costrutti di F #.</span><span class="sxs-lookup"><span data-stu-id="a0253-148">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="a0253-149">Il `Tuple` tipi sono stati introdotti in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a0253-149">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="a0253-150">Se la destinazione è una versione precedente di .NET Framework, il compilatore utilizza le versioni di [System. Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) dalla versione 2.0 della libreria di base F #.</span><span class="sxs-lookup"><span data-stu-id="a0253-150">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="a0253-151">I tipi in questa libreria vengono utilizzati solo per le applicazioni destinate a 2.0, 3.0 e 3.5 versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a0253-151">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="a0253-152">Inoltro dei tipi viene usato per garantire la compatibilità binaria tra i componenti di .NET Framework 2.0 e .NET Framework 4 F #.</span><span class="sxs-lookup"><span data-stu-id="a0253-152">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="a0253-153">Form compilato di tuple Struct</span><span class="sxs-lookup"><span data-stu-id="a0253-153">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="a0253-154">Struct Tuple (ad esempio, `struct (x, y)`), sono completamente diversi da tuple di riferimento.</span><span class="sxs-lookup"><span data-stu-id="a0253-154">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="a0253-155">Vengono compilate nel <xref:System.ValueTuple> tipo, dal grado, o il numero di parametri di tipo di overload.</span><span class="sxs-lookup"><span data-stu-id="a0253-155">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="a0253-156">Sono equivalenti a [c# 7.0 Tuple](../../csharp/tuples.md) e [Visual Basic 2017 Tuple](../../visual-basic/programming-guide/language-features/data-types/tuples.md)e interagire in modalità bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="a0253-156">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0253-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0253-157">See Also</span></span>
[<span data-ttu-id="a0253-158">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="a0253-158">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="a0253-159">Tipi F#</span><span class="sxs-lookup"><span data-stu-id="a0253-159">F# Types</span></span>](fsharp-types.md)
