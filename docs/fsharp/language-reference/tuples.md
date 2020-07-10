---
title: Tuple
description: 'Informazioni sulla tupla F #, un raggruppamento di valori senza nome ma ordinati, possibilmente di tipi diversi.'
ms.date: 05/16/2016
ms.openlocfilehash: 5d26fd5d7ec5b4939a895a6d2a6a0d7fc6c6c733
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173289"
---
# <a name="tuples"></a><span data-ttu-id="734c4-103">Tuple</span><span class="sxs-lookup"><span data-stu-id="734c4-103">Tuples</span></span>

<span data-ttu-id="734c4-104">Una *tupla* è un raggruppamento di valori senza nome ma ordinati, possibilmente di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="734c4-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="734c4-105">Le tuple possono essere tipi o struct di riferimento.</span><span class="sxs-lookup"><span data-stu-id="734c4-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="734c4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="734c4-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="734c4-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="734c4-107">Remarks</span></span>

<span data-ttu-id="734c4-108">Ogni *elemento* della sintassi precedente può essere qualsiasi espressione F # valida.</span><span class="sxs-lookup"><span data-stu-id="734c4-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="734c4-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="734c4-109">Examples</span></span>

<span data-ttu-id="734c4-110">Esempi di Tuple includono coppie, triple e così via, dello stesso tipo o di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="734c4-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="734c4-111">Nel codice riportato di seguito sono illustrati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="734c4-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="734c4-112">Recupero di singoli valori</span><span class="sxs-lookup"><span data-stu-id="734c4-112">Obtaining Individual Values</span></span>

<span data-ttu-id="734c4-113">È possibile utilizzare criteri di ricerca per accedere e assegnare nomi per gli elementi di tupla, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="734c4-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="734c4-114">È anche possibile decostruire una tupla tramite criteri di ricerca all'esterno di un' `match` espressione tramite `let` Binding:</span><span class="sxs-lookup"><span data-stu-id="734c4-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="734c4-115">In alternativa, è possibile modellare le corrispondenze sulle tuple come input per le funzioni:</span><span class="sxs-lookup"><span data-stu-id="734c4-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="734c4-116">Se è necessario un solo elemento della tupla, è possibile usare il carattere jolly (il carattere di sottolineatura) per evitare di creare un nuovo nome per un valore che non è necessario.</span><span class="sxs-lookup"><span data-stu-id="734c4-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="734c4-117">Anche la copia di elementi da una tupla di riferimento in una tupla di struct è semplice:</span><span class="sxs-lookup"><span data-stu-id="734c4-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="734c4-118">Le funzioni `fst` e `snd` (solo tuple di riferimento) restituiscono rispettivamente il primo e il secondo elemento di una tupla.</span><span class="sxs-lookup"><span data-stu-id="734c4-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="734c4-119">Non esiste alcuna funzione incorporata che restituisce il terzo elemento di un triplo, ma è possibile scriverne facilmente uno come segue.</span><span class="sxs-lookup"><span data-stu-id="734c4-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="734c4-120">In genere, è preferibile usare i criteri di ricerca per accedere ai singoli elementi della tupla.</span><span class="sxs-lookup"><span data-stu-id="734c4-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="734c4-121">Utilizzo di Tuple</span><span class="sxs-lookup"><span data-stu-id="734c4-121">Using Tuples</span></span>

<span data-ttu-id="734c4-122">Le tuple rappresentano un modo pratico per restituire più valori da una funzione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="734c4-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="734c4-123">In questo esempio viene eseguita la divisione di interi e viene restituito il risultato arrotondato dell'operazione come primo membro di una coppia di tuple e il resto come un secondo membro della coppia.</span><span class="sxs-lookup"><span data-stu-id="734c4-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="734c4-124">Le tuple possono essere utilizzate anche come argomenti della funzione quando si desidera evitare il currying implicito degli argomenti della funzione che è implicito nella sintassi della funzione usuale.</span><span class="sxs-lookup"><span data-stu-id="734c4-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="734c4-125">La sintassi consueta per la definizione della funzione `let sum a b = a + b` consente di definire una funzione che rappresenta l'applicazione parziale del primo argomento della funzione, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="734c4-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="734c4-126">Se si usa una tupla come parametro, il currying viene disabilitato.</span><span class="sxs-lookup"><span data-stu-id="734c4-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="734c4-127">Per ulteriori informazioni, vedere la sezione relativa all'applicazione parziale degli argomenti in [Functions](./functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="734c4-127">For more information, see "Partial Application of Arguments" in [Functions](./functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="734c4-128">Nomi dei tipi di tupla</span><span class="sxs-lookup"><span data-stu-id="734c4-128">Names of Tuple Types</span></span>

<span data-ttu-id="734c4-129">Quando si scrive il nome di un tipo che è una tupla, si usa il `*` simbolo per separare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="734c4-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="734c4-130">Per una tupla costituita da un oggetto `int` , un oggetto `float` e un oggetto `string` , ad esempio `(10, 10.0, "ten")` , il tipo viene scritto come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="734c4-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="734c4-131">Interoperabilità con Tuple C#</span><span class="sxs-lookup"><span data-stu-id="734c4-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="734c4-132">C# 7,0 ha introdotto le tuple nel linguaggio.</span><span class="sxs-lookup"><span data-stu-id="734c4-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="734c4-133">Le tuple in C# sono struct e sono equivalenti alle tuple struct in F #.</span><span class="sxs-lookup"><span data-stu-id="734c4-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="734c4-134">Se è necessario interagire con C#, è necessario usare le tuple struct.</span><span class="sxs-lookup"><span data-stu-id="734c4-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="734c4-135">Questa operazione è facile.</span><span class="sxs-lookup"><span data-stu-id="734c4-135">This is easy to do.</span></span>  <span data-ttu-id="734c4-136">Si supponga, ad esempio, di dover passare una tupla a una classe C# e quindi utilizzare il risultato, che è anche una tupla:</span><span class="sxs-lookup"><span data-stu-id="734c4-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="734c4-137">Nel codice F # è quindi possibile passare una tupla struct come parametro e utilizzare il risultato come tupla struct.</span><span class="sxs-lookup"><span data-stu-id="734c4-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="734c4-138">Conversione tra tuple di riferimento e Tuple di struct</span><span class="sxs-lookup"><span data-stu-id="734c4-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="734c4-139">Poiché le tuple di riferimento e le tuple struct hanno una rappresentazione sottostante completamente diversa, non sono convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="734c4-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="734c4-140">Ovvero, il codice come il seguente non verrà compilato:</span><span class="sxs-lookup"><span data-stu-id="734c4-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="734c4-141">È necessario definire la corrispondenza in una tupla e costruire l'altra con le parti costituenti.</span><span class="sxs-lookup"><span data-stu-id="734c4-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="734c4-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="734c4-142">For example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="734c4-143">Forma compilata di tuple di riferimento</span><span class="sxs-lookup"><span data-stu-id="734c4-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="734c4-144">In questa sezione viene illustrata la forma delle tuple quando vengono compilate.</span><span class="sxs-lookup"><span data-stu-id="734c4-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="734c4-145">Le informazioni non sono necessarie per la lettura, a meno che la destinazione non sia .NET Framework 3,5 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="734c4-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="734c4-146">Le tuple vengono compilate in oggetti di uno dei diversi tipi generici, tutti denominati `System.Tuple` , che sono sottoutilizzati per il grado o il numero di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="734c4-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="734c4-147">I tipi di tupla vengono visualizzati in questo formato quando vengono visualizzati da un altro linguaggio, ad esempio C# o Visual Basic, oppure quando si utilizza uno strumento che non è in grado di riconoscere i costrutti F #.</span><span class="sxs-lookup"><span data-stu-id="734c4-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="734c4-148">I `Tuple` tipi sono stati introdotti in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="734c4-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="734c4-149">Se la destinazione è una versione precedente del .NET Framework, il compilatore usa le versioni di [System. Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) dalla versione 2,0 della libreria di base F #.</span><span class="sxs-lookup"><span data-stu-id="734c4-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="734c4-150">I tipi in questa libreria vengono usati solo per le applicazioni destinate alle versioni 2,0, 3,0 e 3,5 del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="734c4-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="734c4-151">L'invio dei tipi viene usato per garantire la compatibilità binaria tra i componenti .NET Framework 2,0 e .NET Framework 4 F #.</span><span class="sxs-lookup"><span data-stu-id="734c4-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="734c4-152">Forma compilata di Tuple struct</span><span class="sxs-lookup"><span data-stu-id="734c4-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="734c4-153">Le tuple struct (ad esempio, `struct (x, y)` ) sono fondamentalmente diverse dalle tuple di riferimento.</span><span class="sxs-lookup"><span data-stu-id="734c4-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="734c4-154">Sono compilati nel <xref:System.ValueTuple> tipo, in overload per grado o nel numero di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="734c4-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="734c4-155">Sono equivalenti a [Tuple C# 7,0](../../csharp/language-reference/builtin-types/value-tuples.md) e [Visual Basic Tuple 2017](../../visual-basic/programming-guide/language-features/data-types/tuples.md)e interoperano in modo bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="734c4-155">They are equivalent to [C# 7.0 Tuples](../../csharp/language-reference/builtin-types/value-tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="734c4-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="734c4-156">See also</span></span>

- [<span data-ttu-id="734c4-157">Riferimenti per il linguaggio F #</span><span class="sxs-lookup"><span data-stu-id="734c4-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="734c4-158">Tipi F#</span><span class="sxs-lookup"><span data-stu-id="734c4-158">F# Types</span></span>](fsharp-types.md)
