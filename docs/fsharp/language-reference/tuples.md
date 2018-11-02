---
title: Tuple (F#)
description: 'Scopri la tupla F #, un raggruppamento di valori senza nome, ma ordinati, tipi potenzialmente diversi.'
ms.date: 05/16/2016
ms.openlocfilehash: e7628e4c4b538c2fe52fca25d2597b10fec28d1c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43749223"
---
# <a name="tuples"></a><span data-ttu-id="890bb-103">Tuple</span><span class="sxs-lookup"><span data-stu-id="890bb-103">Tuples</span></span>

<span data-ttu-id="890bb-104">Oggetto *tupla* è un raggruppamento di valori senza nome, ma ordinati, tipi potenzialmente diversi.</span><span class="sxs-lookup"><span data-stu-id="890bb-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="890bb-105">Le tuple possono essere tipi riferimento o struct.</span><span class="sxs-lookup"><span data-stu-id="890bb-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="890bb-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="890bb-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="890bb-107">Note</span><span class="sxs-lookup"><span data-stu-id="890bb-107">Remarks</span></span>

<span data-ttu-id="890bb-108">Ciascuna *elemento* nella sintassi precedente può essere qualsiasi espressione valida con F #.</span><span class="sxs-lookup"><span data-stu-id="890bb-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="890bb-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="890bb-109">Examples</span></span>

<span data-ttu-id="890bb-110">Coppie Triple e così via, dei tipi uguali o diversi esempi di tuple.</span><span class="sxs-lookup"><span data-stu-id="890bb-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="890bb-111">Nel codice seguente sono illustrati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="890bb-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="890bb-112">Recupero di singoli valori</span><span class="sxs-lookup"><span data-stu-id="890bb-112">Obtaining Individual Values</span></span>

<span data-ttu-id="890bb-113">È possibile utilizzare criteri di ricerca per accedere e assegnare i nomi per gli elementi di tupla, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="890bb-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="890bb-114">È anche possibile decostruire una tupla tramite criteri di ricerca di fuori di una `match` espressione tramite `let` associazione:</span><span class="sxs-lookup"><span data-stu-id="890bb-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="890bb-115">Oppure potete creare una serie corrispondono in tuple come input per le funzioni:</span><span class="sxs-lookup"><span data-stu-id="890bb-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="890bb-116">Se è necessario un solo elemento di tupla, il carattere jolly (il carattere di sottolineatura) è utilizzabile per evitare di creare un nuovo nome per un valore che non è necessario.</span><span class="sxs-lookup"><span data-stu-id="890bb-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="890bb-117">Copia gli elementi da una tupla di riferimento in una tupla di uno struct è anche semplice:</span><span class="sxs-lookup"><span data-stu-id="890bb-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="890bb-118">Le funzioni `fst` e `snd` (fanno riferimento le tuple solo) restituiscono il primo e secondo elemento di una tupla, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="890bb-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="890bb-119">Non vi è alcuna funzione predefinita che restituisce il terzo elemento di una triple, ma è possibile scrivere facilmente uno come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="890bb-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="890bb-120">In generale, è preferibile usare criteri di ricerca per accedere agli elementi di tupla individuali.</span><span class="sxs-lookup"><span data-stu-id="890bb-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="890bb-121">Usare le tuple</span><span class="sxs-lookup"><span data-stu-id="890bb-121">Using Tuples</span></span>

<span data-ttu-id="890bb-122">Le tuple forniscono un modo pratico per restituire più valori da una funzione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="890bb-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="890bb-123">In questo esempio esegue la divisione di interi e restituisce il risultato arrotondato dell'operazione come membro di una coppia di tuple prima che il resto come secondo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="890bb-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="890bb-124">Le tuple sono anche utilizzabile come argomenti della funzione quando si desidera evitare il currying implicita degli argomenti della funzione che è in cui è inclusa la sintassi della funzione normale.</span><span class="sxs-lookup"><span data-stu-id="890bb-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="890bb-125">La sintassi comune per la definizione di funzione `let sum a b = a + b` consente di definire una funzione che rappresenta l'applicazione parziale del primo argomento della funzione, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="890bb-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="890bb-126">Uso di una tupla come parametro disabilita currying.</span><span class="sxs-lookup"><span data-stu-id="890bb-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="890bb-127">Per altre informazioni, vedere "Applicazione parziale di argomenti" nella [funzioni](functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="890bb-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="890bb-128">Nomi dei tipi di tupla</span><span class="sxs-lookup"><span data-stu-id="890bb-128">Names of Tuple Types</span></span>

<span data-ttu-id="890bb-129">Quando si scrive il nome di un tipo che è una tupla, è utilizzare il `*` simbolo per separare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="890bb-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="890bb-130">Per una tupla costituita da un `int`, un `float`e una `string`, ad esempio `(10, 10.0, "ten")`, il tipo viene scritto come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="890bb-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="890bb-131">Interoperabilità con tuple in c#</span><span class="sxs-lookup"><span data-stu-id="890bb-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="890bb-132">C# 7.0 ha introdotto le tuple del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="890bb-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="890bb-133">Le tuple in c# sono strutture e sono equivalenti alle tuple di struct in F #.</span><span class="sxs-lookup"><span data-stu-id="890bb-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="890bb-134">Se è necessario per l'interoperabilità con c#, è necessario usare le tuple struct.</span><span class="sxs-lookup"><span data-stu-id="890bb-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="890bb-135">Si tratta di un'operazione semplice.</span><span class="sxs-lookup"><span data-stu-id="890bb-135">This is easy to do.</span></span>  <span data-ttu-id="890bb-136">Si supponga, ad esempio passare una tupla a una classe c# e quindi utilizzare il risultato, che è anche una tupla:</span><span class="sxs-lookup"><span data-stu-id="890bb-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="890bb-137">Nel codice F #, è quindi possibile passare una tupla di uno struct come parametro e utilizzare il risultato come una tupla di uno struct.</span><span class="sxs-lookup"><span data-stu-id="890bb-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="890bb-138">Conversione tra le tuple di riferimento e le tuple Struct</span><span class="sxs-lookup"><span data-stu-id="890bb-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="890bb-139">Poiché le tuple di riferimento e Struct Tuples hanno una rappresentazione sottostante completamente diversa, non sono convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="890bb-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="890bb-140">Vale a dire, non verrà compilato il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="890bb-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="890bb-141">È necessario criteri di corrispondenza per una tupla e costruire l'altro con le parti costituenti.</span><span class="sxs-lookup"><span data-stu-id="890bb-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="890bb-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="890bb-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="890bb-143">Formato compilato di tuple di riferimento</span><span class="sxs-lookup"><span data-stu-id="890bb-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="890bb-144">Questa sezione illustra la forma di tuple quando essi è compilati.</span><span class="sxs-lookup"><span data-stu-id="890bb-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="890bb-145">Le informazioni qui non sono necessari per la lettura a meno che non si usa .NET Framework 3.5 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="890bb-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="890bb-146">Le tuple vengono compilate in oggetti di uno dei vari tipi generici, tutte il nome `System.Tuple`, che sono sottoposti a overload in grado o sul numero di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="890bb-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="890bb-147">Tipi di tupla vengono visualizzati in questo modulo quando vengono visualizzati da un altro linguaggio, ad esempio c# o Visual Basic, oppure quando si usa uno strumento che non riconosce i costrutti F #.</span><span class="sxs-lookup"><span data-stu-id="890bb-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="890bb-148">Il `Tuple` tipi sono stati introdotti in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="890bb-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="890bb-149">Se la destinazione è una versione precedente di .NET Framework, il compilatore Usa le versioni di [System. Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) dalla versione 2.0 della libreria di base F #.</span><span class="sxs-lookup"><span data-stu-id="890bb-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="890bb-150">I tipi in questa raccolta vengono utilizzati solo per le applicazioni che usano la versione 2.0, 3.0 e 3.5 versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="890bb-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="890bb-151">L'inoltro dei tipi viene usato per garantire la compatibilità binaria tra i componenti di .NET Framework 2.0 e .NET Framework 4 F #.</span><span class="sxs-lookup"><span data-stu-id="890bb-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="890bb-152">Formato compilato di tuple di Struct</span><span class="sxs-lookup"><span data-stu-id="890bb-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="890bb-153">Le tuple struct (ad esempio, `struct (x, y)`), sono fondamentalmente diversi da tuple di riferimento.</span><span class="sxs-lookup"><span data-stu-id="890bb-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="890bb-154">Vengono compilate nel <xref:System.ValueTuple> tipo, sottoposti a overload da arietà o il numero di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="890bb-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="890bb-155">Queste saranno equivalenti a [tuple in c# 7.0](../../csharp/tuples.md) e [tuple di Visual Basic 2017](../../visual-basic/programming-guide/language-features/data-types/tuples.md)e l'interoperabilità bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="890bb-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="890bb-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="890bb-156">See also</span></span>

- [<span data-ttu-id="890bb-157">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="890bb-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="890bb-158">Tipi F#</span><span class="sxs-lookup"><span data-stu-id="890bb-158">F# Types</span></span>](fsharp-types.md)
