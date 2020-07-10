---
title: Tipi di tupla-riferimenti per C#
description: 'Informazioni sulle tuple C#: strutture di dati lightweight che è possibile usare per raggruppare elementi di dati vagamente correlati'
ms.date: 07/09/2020
helpviewer_keywords:
- value tuples [C#]
ms.openlocfilehash: 3d79ab19117847e2364b154db33a1521416bb3f4
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174991"
---
# <a name="tuple-types-c-reference"></a><span data-ttu-id="baadd-103">Tipi di tupla (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="baadd-103">Tuple types (C# reference)</span></span>

<span data-ttu-id="baadd-104">Disponibile in C# 7,0 e versioni successive, la funzionalità *Tuple* offre una sintassi concisa per raggruppare più elementi dati in una struttura di dati semplice.</span><span class="sxs-lookup"><span data-stu-id="baadd-104">Available in C# 7.0 and later, the *tuples* feature provides concise syntax to group multiple data elements in a lightweight data structure.</span></span> <span data-ttu-id="baadd-105">Nell'esempio seguente viene illustrato come è possibile dichiarare una variabile di tupla, inizializzarla e accedere ai relativi membri dati:</span><span class="sxs-lookup"><span data-stu-id="baadd-105">The following example shows how you can declare a tuple variable, initialize it, and access its data members:</span></span>

[!code-csharp-interactive[tuple intro](snippets/ValueTuples.cs#Introduction)]

<span data-ttu-id="baadd-106">Come illustrato nell'esempio precedente, per definire un tipo di tupla, è necessario specificare i tipi di tutti i relativi membri dati e, facoltativamente, i [nomi dei campi](#tuple-field-names).</span><span class="sxs-lookup"><span data-stu-id="baadd-106">As the preceding example shows, to define a tuple type, you specify types of all its data members and, optionally, the [field names](#tuple-field-names).</span></span> <span data-ttu-id="baadd-107">Non è possibile definire metodi in un tipo di tupla, ma è possibile usare i metodi forniti da .NET, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="baadd-107">You cannot define methods in a tuple type, but you can use the methods provided by .NET, as the following example shows:</span></span>

[!code-csharp-interactive[tuple methods](snippets/ValueTuples.cs#MethodOnTuples)]

<span data-ttu-id="baadd-108">A partire da C# 7,3, i tipi di tupla supportano [gli operatori di uguaglianza](../operators/equality-operators.md) `==` e `!=` .</span><span class="sxs-lookup"><span data-stu-id="baadd-108">Beginning with C# 7.3, tuple types support [equality operators](../operators/equality-operators.md) `==` and `!=`.</span></span> <span data-ttu-id="baadd-109">Per ulteriori informazioni, vedere la sezione relativa all' [uguaglianza delle tuple](#tuple-equality) .</span><span class="sxs-lookup"><span data-stu-id="baadd-109">For more information, see the [Tuple equality](#tuple-equality) section.</span></span>

<span data-ttu-id="baadd-110">I tipi di tupla sono [tipi valore](value-types.md); gli elementi della tupla sono campi pubblici.</span><span class="sxs-lookup"><span data-stu-id="baadd-110">Tuple types are [value types](value-types.md); tuple elements are public fields.</span></span> <span data-ttu-id="baadd-111">Che rende i tipi di valore *modificabili* delle tuple.</span><span class="sxs-lookup"><span data-stu-id="baadd-111">That makes tuples *mutable* value types.</span></span>

> [!NOTE]
> <span data-ttu-id="baadd-112">La funzionalità Tuple richiede il <xref:System.ValueTuple?displayProperty=nameWithType> tipo e i tipi generici correlati, ad esempio, <xref:System.ValueTuple%602?displayProperty=nameWithType> che sono disponibili in .NET Core e .NET Framework 4,7 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="baadd-112">The tuples feature requires the <xref:System.ValueTuple?displayProperty=nameWithType> type and related generic types (for example, <xref:System.ValueTuple%602?displayProperty=nameWithType>), which are available in .NET Core and .NET Framework 4.7 and later.</span></span> <span data-ttu-id="baadd-113">Per usare le tuple in un progetto che ha come destinazione .NET Framework 4.6.2 o versione precedente, aggiungere il pacchetto NuGet [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) al progetto.</span><span class="sxs-lookup"><span data-stu-id="baadd-113">To use tuples in a project that targets .NET Framework 4.6.2 or earlier, add the NuGet package [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) to the project.</span></span>

<span data-ttu-id="baadd-114">È possibile definire tuple con un numero elevato arbitrario di elementi:</span><span class="sxs-lookup"><span data-stu-id="baadd-114">You can define tuples with an arbitrary large number of elements:</span></span>

[!code-csharp-interactive[large tuple](snippets/ValueTuples.cs#LargeTuple)]

## <a name="use-cases-of-tuples"></a><span data-ttu-id="baadd-115">Casi d'uso delle tuple</span><span class="sxs-lookup"><span data-stu-id="baadd-115">Use cases of tuples</span></span>

<span data-ttu-id="baadd-116">Uno dei casi d'uso più comuni delle tuple è come tipo restituito del metodo.</span><span class="sxs-lookup"><span data-stu-id="baadd-116">One of the most common use cases of tuples is as a method return type.</span></span> <span data-ttu-id="baadd-117">Ovvero, anziché definire i [ `out` parametri del metodo](../keywords/out-parameter-modifier.md), è possibile raggruppare i risultati del metodo in un tipo restituito della tupla, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="baadd-117">That is, instead of defining [`out` method parameters](../keywords/out-parameter-modifier.md), you can group method results in a tuple return type, as the following example shows:</span></span>

[!code-csharp-interactive[multiple method outputs](snippets/ValueTuples.cs#MultipleReturns)]

<span data-ttu-id="baadd-118">Come illustrato nell'esempio precedente, è possibile usare direttamente l'istanza di tupla restituita o [decostruirla](#tuple-assignment-and-deconstruction) in variabili separate.</span><span class="sxs-lookup"><span data-stu-id="baadd-118">As the preceding example shows, you can work with the returned tuple instance directly or [deconstruct](#tuple-assignment-and-deconstruction) it in separate variables.</span></span>

<span data-ttu-id="baadd-119">È inoltre possibile utilizzare tipi di tupla anziché [tipi anonimi](../../programming-guide/classes-and-structs/anonymous-types.md); ad esempio, nelle query LINQ.</span><span class="sxs-lookup"><span data-stu-id="baadd-119">You can also use tuple types instead of [anonymous types](../../programming-guide/classes-and-structs/anonymous-types.md); for example, in LINQ queries.</span></span> <span data-ttu-id="baadd-120">Per ulteriori informazioni, vedere [scelta tra tipi anonimi e Tuple](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).</span><span class="sxs-lookup"><span data-stu-id="baadd-120">For more information, see [Choosing between anonymous and tuple types](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).</span></span>

<span data-ttu-id="baadd-121">In genere, le tuple vengono utilizzate per raggruppare elementi di dati debolmente correlati.</span><span class="sxs-lookup"><span data-stu-id="baadd-121">Typically, you use tuples to group loosely related data elements.</span></span> <span data-ttu-id="baadd-122">Questo è in genere utile all'interno di metodi di utilità privati e interni.</span><span class="sxs-lookup"><span data-stu-id="baadd-122">That is usually useful within private and internal utility methods.</span></span> <span data-ttu-id="baadd-123">Nel caso di un'API pubblica, è consigliabile definire una [classe](../keywords/class.md) o un tipo di [struttura](struct.md) .</span><span class="sxs-lookup"><span data-stu-id="baadd-123">In the case of public API, consider defining a [class](../keywords/class.md) or a [structure](struct.md) type.</span></span>

## <a name="tuple-field-names"></a><span data-ttu-id="baadd-124">Nomi dei campi di tupla</span><span class="sxs-lookup"><span data-stu-id="baadd-124">Tuple field names</span></span>

<span data-ttu-id="baadd-125">È possibile specificare in modo esplicito i nomi dei campi di tupla in un'espressione di inizializzazione della tupla o nella definizione di un tipo di tupla, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="baadd-125">You can explicitly specify the names of tuple fields either in a tuple initialization expression or in the definition of a tuple type, as the following example shows:</span></span>

[!code-csharp-interactive[explicit field names](snippets/ValueTuples.cs#ExplicitFieldNames)]

<span data-ttu-id="baadd-126">A partire da C# 7,1, se non si specifica un nome di campo, può essere dedotto dal nome della variabile corrispondente in un'espressione di inizializzazione della tupla, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="baadd-126">Beginning with C# 7.1, if you don't specify a field name, it may be inferred from the name of the corresponding variable in a tuple initialization expression, as the following example shows:</span></span>

[!code-csharp-interactive[inferred field names](snippets/ValueTuples.cs#InferFieldNames)]

<span data-ttu-id="baadd-127">Noto come inizializzatori di proiezione della tupla.</span><span class="sxs-lookup"><span data-stu-id="baadd-127">That's known as tuple projection initializers.</span></span> <span data-ttu-id="baadd-128">Il nome di una variabile non è proiettato su un nome di campo di tupla nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="baadd-128">The name of a variable isn't projected onto a tuple field name in the following cases:</span></span>

- <span data-ttu-id="baadd-129">Il nome candidato è un nome di membro di un tipo di tupla, ad esempio,, `Item3` `ToString` o `Rest` .</span><span class="sxs-lookup"><span data-stu-id="baadd-129">The candidate name is a member name of a tuple type, for example, `Item3`, `ToString`, or `Rest`.</span></span>
- <span data-ttu-id="baadd-130">Il nome candidato è un duplicato di un altro nome di campo di tupla, esplicito o implicito.</span><span class="sxs-lookup"><span data-stu-id="baadd-130">The candidate name is a duplicate of another tuple field name, either explicit or implicit.</span></span>

<span data-ttu-id="baadd-131">In questi casi è possibile specificare in modo esplicito il nome di un campo o accedere a un campo con il nome predefinito.</span><span class="sxs-lookup"><span data-stu-id="baadd-131">In those cases you either explicitly specify the name of a field or access a field by its default name.</span></span>

<span data-ttu-id="baadd-132">I nomi predefiniti dei campi di tupla sono `Item1` , `Item2` `Item3` e così via.</span><span class="sxs-lookup"><span data-stu-id="baadd-132">The default names of tuple fields are `Item1`, `Item2`, `Item3` and so on.</span></span> <span data-ttu-id="baadd-133">È sempre possibile usare il nome predefinito di un campo, anche quando un nome di campo viene specificato in modo esplicito o dedotto, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="baadd-133">You can always use the default name of a field, even when a field name is specified explicitly or inferred, as the following example shows:</span></span>

[!code-csharp-interactive[default field names](snippets/ValueTuples.cs#DefaultFieldNames)]

<span data-ttu-id="baadd-134">L' [assegnazione di Tuple](#tuple-assignment-and-deconstruction) e i [confronti di uguaglianza delle tuple](#tuple-equality) non accettano nomi di campo.</span><span class="sxs-lookup"><span data-stu-id="baadd-134">[Tuple assignment](#tuple-assignment-and-deconstruction) and [tuple equality comparisons](#tuple-equality) don't take field names into account.</span></span>

<span data-ttu-id="baadd-135">In fase di compilazione, il compilatore sostituisce i nomi di campo non predefiniti con i nomi predefiniti corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="baadd-135">At compile time, the compiler replaces non-default field names with the corresponding default names.</span></span> <span data-ttu-id="baadd-136">Di conseguenza, i nomi di campo specificati in modo esplicito o dedotti non sono disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="baadd-136">As a result, explicitly specified or inferred field names aren't available at run time.</span></span>

## <a name="tuple-assignment-and-deconstruction"></a><span data-ttu-id="baadd-137">Assegnazione e decostruzione di Tuple</span><span class="sxs-lookup"><span data-stu-id="baadd-137">Tuple assignment and deconstruction</span></span>

<span data-ttu-id="baadd-138">C# supporta l'assegnazione tra tipi di tupla che soddisfano entrambe le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="baadd-138">C# supports assignment between tuple types that satisfy both of the following conditions:</span></span>

- <span data-ttu-id="baadd-139">entrambi i tipi di tupla hanno lo stesso numero di elementi</span><span class="sxs-lookup"><span data-stu-id="baadd-139">both tuple types have the same number of elements</span></span>
- <span data-ttu-id="baadd-140">per ogni posizione di tupla, il tipo dell'elemento di tupla a destra è uguale o convertibile in modo implicito nel tipo dell'elemento tupla a sinistra corrispondente.</span><span class="sxs-lookup"><span data-stu-id="baadd-140">for each tuple position, the type of the right-hand tuple element is the same as or implicitly convertible to the type of the corresponding left-hand tuple element</span></span>

<span data-ttu-id="baadd-141">I valori degli elementi di tupla vengono assegnati in base all'ordine degli elementi della tupla.</span><span class="sxs-lookup"><span data-stu-id="baadd-141">Tuple element values are assigned following the order of tuple elements.</span></span> <span data-ttu-id="baadd-142">I nomi dei campi di tupla vengono ignorati e non assegnati, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="baadd-142">The names of tuple fields are ignored and not assigned, as the following example shows:</span></span>

[!code-csharp-interactive[tuple assignment](snippets/ValueTuples.cs#Assignment)]

<span data-ttu-id="baadd-143">È anche possibile usare l'operatore `=` di assegnazione per *decostruire* un'istanza di tupla in variabili separate.</span><span class="sxs-lookup"><span data-stu-id="baadd-143">You can also use the assignment operator `=` to *deconstruct* a tuple instance in separate variables.</span></span> <span data-ttu-id="baadd-144">Questa operazione può essere eseguita in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="baadd-144">You can do that in one of the following ways:</span></span>

- <span data-ttu-id="baadd-145">Dichiarare in modo esplicito il tipo di ogni variabile racchiusa tra parentesi:</span><span class="sxs-lookup"><span data-stu-id="baadd-145">Explicitly declare the type of each variable inside parentheses:</span></span>

  [!code-csharp-interactive[specify types of variables](snippets/ValueTuples.cs#DeconstructExplicit)]

- <span data-ttu-id="baadd-146">Usare la `var` parola chiave all'esterno delle parentesi per dichiarare le variabili tipizzate in modo implicito e consentire al compilatore di dedurre i tipi:</span><span class="sxs-lookup"><span data-stu-id="baadd-146">Use the `var` keyword outside the parentheses to declare implicitly typed variables and let the compiler infer their types:</span></span>

  [!code-csharp-interactive[implicitly typed variables](snippets/ValueTuples.cs#DeconstructVar)]

- <span data-ttu-id="baadd-147">USA variabili esistenti:</span><span class="sxs-lookup"><span data-stu-id="baadd-147">Use existing variables:</span></span>

  [!code-csharp-interactive[existing variables](snippets/ValueTuples.cs#DeconstructExisting)]

<span data-ttu-id="baadd-148">Per ulteriori informazioni sulla decostruzione di tuple e altri tipi, vedere decostruzione di [Tuple e altri tipi](../../deconstruct.md).</span><span class="sxs-lookup"><span data-stu-id="baadd-148">For more information about deconstruction of tuples and other types, see [Deconstructing tuples and other types](../../deconstruct.md).</span></span>

## <a name="tuple-equality"></a><span data-ttu-id="baadd-149">Uguaglianza Tuple</span><span class="sxs-lookup"><span data-stu-id="baadd-149">Tuple equality</span></span>

<span data-ttu-id="baadd-150">A partire da C# 7.3, i tipi tupla supportano gli operatori `==` e `!=`.</span><span class="sxs-lookup"><span data-stu-id="baadd-150">Beginning with C# 7.3, tuple types support the `==` and `!=` operators.</span></span> <span data-ttu-id="baadd-151">Questi operatori confrontano i membri dell'operando sinistro con i membri corrispondenti dell'operando destro che segue l'ordine degli elementi della tupla.</span><span class="sxs-lookup"><span data-stu-id="baadd-151">These operators compare members of the left-hand operand with the corresponding members of the right-hand operand following the order of tuple elements.</span></span>

[!code-csharp-interactive[tuple equality](snippets/ValueTuples.cs#TupleEquality)]

<span data-ttu-id="baadd-152">Come illustrato nell'esempio precedente, le `==` `!=` operazioni e non prendono in considerazione i nomi dei campi di tupla.</span><span class="sxs-lookup"><span data-stu-id="baadd-152">As the preceding example shows, the `==` and `!=` operations don't take into account tuple field names.</span></span>

<span data-ttu-id="baadd-153">Due tuple sono confrontabili quando sono soddisfatte entrambe le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="baadd-153">Two tuples are comparable when both of the following conditions are satisfied:</span></span>

- <span data-ttu-id="baadd-154">Entrambe le tuple hanno lo stesso numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="baadd-154">Both tuples have the same number of elements.</span></span> <span data-ttu-id="baadd-155">Ad esempio, `t1 != t2` non compila se `t1` e `t2` hanno numeri di elementi diversi.</span><span class="sxs-lookup"><span data-stu-id="baadd-155">For example, `t1 != t2` doesn't compile if `t1` and `t2` have different numbers of elements.</span></span>
- <span data-ttu-id="baadd-156">Per ogni posizione di tupla, gli elementi corrispondenti dagli operandi di tupla a sinistra e a destra sono confrontabili con `==` gli `!=` operatori e.</span><span class="sxs-lookup"><span data-stu-id="baadd-156">For each tuple position, the corresponding elements from the left-hand and right-hand tuple operands are comparable with the `==` and `!=` operators.</span></span> <span data-ttu-id="baadd-157">Ad esempio, `(1, (2, 3)) == ((1, 2), 3)` non viene compilato perché `1` non è confrontabile con `(1, 2)` .</span><span class="sxs-lookup"><span data-stu-id="baadd-157">For example, `(1, (2, 3)) == ((1, 2), 3)` doesn't compile because `1` is not comparable with `(1, 2)`.</span></span>

<span data-ttu-id="baadd-158">Gli `==` `!=` operatori e confrontano le tuple in modalità di corto circuito.</span><span class="sxs-lookup"><span data-stu-id="baadd-158">The `==` and `!=` operators compare tuples in short-circuiting way.</span></span> <span data-ttu-id="baadd-159">In altre termini, un'operazione viene arrestata non appena incontra una coppia di elementi non uguali o raggiunge le estremità delle tuple.</span><span class="sxs-lookup"><span data-stu-id="baadd-159">That is, an operation stops as soon as it meets a pair of non equal elements or reaches the ends of tuples.</span></span> <span data-ttu-id="baadd-160">Tuttavia, prima di qualsiasi confronto, vengono valutati *tutti* gli elementi della tupla, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="baadd-160">However, before any comparison, *all* tuple elements are evaluated, as the following example shows:</span></span>

[!code-csharp-interactive[tuple element evaluation](snippets/ValueTuples.cs#TupleEvaluationForEquality)]

## <a name="tuples-as-out-parameters"></a><span data-ttu-id="baadd-161">Tuple come parametri out</span><span class="sxs-lookup"><span data-stu-id="baadd-161">Tuples as out parameters</span></span>

<span data-ttu-id="baadd-162">In genere, si effettua il refactoring di un metodo che dispone di [ `out` parametri](../keywords/out-parameter-modifier.md) in un metodo che restituisce una tupla.</span><span class="sxs-lookup"><span data-stu-id="baadd-162">Typically, you refactor a method that has [`out` parameters](../keywords/out-parameter-modifier.md) into a method that returns a tuple.</span></span> <span data-ttu-id="baadd-163">Tuttavia, esistono casi in cui un `out` parametro può essere di un tipo di tupla.</span><span class="sxs-lookup"><span data-stu-id="baadd-163">However, there are cases in which an `out` parameter can be of a tuple type.</span></span> <span data-ttu-id="baadd-164">Nell'esempio seguente viene illustrato come utilizzare le tuple come `out` parametri:</span><span class="sxs-lookup"><span data-stu-id="baadd-164">The following example shows how to work with tuples as `out` parameters:</span></span>

[!code-csharp-interactive[tuple as out parameter](snippets/ValueTuples.cs#TupleAsOutParameter)]

## <a name="tuples-vs-systemtuple"></a><span data-ttu-id="baadd-165">Confronto tra tuple e`System.Tuple`</span><span class="sxs-lookup"><span data-stu-id="baadd-165">Tuples vs `System.Tuple`</span></span>

<span data-ttu-id="baadd-166">Le tuple C#, supportate dai <xref:System.ValueTuple?displayProperty=nameWithType> tipi, sono diverse dalle tuple rappresentate dai <xref:System.Tuple?displayProperty=nameWithType> tipi.</span><span class="sxs-lookup"><span data-stu-id="baadd-166">C# tuples, which are backed by <xref:System.ValueTuple?displayProperty=nameWithType> types, are different from tuples that are represented by <xref:System.Tuple?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="baadd-167">Di seguito sono riportate le differenze principali:</span><span class="sxs-lookup"><span data-stu-id="baadd-167">The main differences are as follows:</span></span>

- <span data-ttu-id="baadd-168">`ValueTuple`i tipi sono [tipi di valore](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="baadd-168">`ValueTuple` types are [value types](value-types.md).</span></span> <span data-ttu-id="baadd-169">`Tuple`i tipi sono [tipi di riferimento](../keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="baadd-169">`Tuple` types are [reference types](../keywords/reference-types.md).</span></span>
- <span data-ttu-id="baadd-170">`ValueTuple`i tipi sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="baadd-170">`ValueTuple` types are mutable.</span></span> <span data-ttu-id="baadd-171">`Tuple`i tipi non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="baadd-171">`Tuple` types are immutable.</span></span>
- <span data-ttu-id="baadd-172">I membri dati di `ValueTuple` tipo sono campi.</span><span class="sxs-lookup"><span data-stu-id="baadd-172">Data members of `ValueTuple` types are fields.</span></span> <span data-ttu-id="baadd-173">I membri dati di `Tuple` tipo sono proprietà.</span><span class="sxs-lookup"><span data-stu-id="baadd-173">Data members of `Tuple` types are properties.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="baadd-174">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="baadd-174">C# language specification</span></span>

<span data-ttu-id="baadd-175">Per ulteriori informazioni, vedere le note sulla proposta di funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="baadd-175">For more information, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="baadd-176">Deduce i nomi delle Tuple (noti anche come inizializzatori di proiezione della tupla)</span><span class="sxs-lookup"><span data-stu-id="baadd-176">Infer tuple names (aka. tuple projection initializers)</span></span>](~/_csharplang/proposals/csharp-7.1/infer-tuple-names.md)
- [<span data-ttu-id="baadd-177">Supporto per `==` e `!=` su tipi di tupla</span><span class="sxs-lookup"><span data-stu-id="baadd-177">Support for `==` and `!=` on tuple types</span></span>](~/_csharplang/proposals/csharp-7.3/tuple-equality.md)

## <a name="see-also"></a><span data-ttu-id="baadd-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baadd-178">See also</span></span>

- [<span data-ttu-id="baadd-179">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="baadd-179">C# reference</span></span>](../index.md)
- [<span data-ttu-id="baadd-180">Tipi di valori</span><span class="sxs-lookup"><span data-stu-id="baadd-180">Value types</span></span>](value-types.md)
- [<span data-ttu-id="baadd-181">Scelta tra tipi anonimi e di tupla</span><span class="sxs-lookup"><span data-stu-id="baadd-181">Choosing between anonymous and tuple types</span></span>](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)
- <xref:System.ValueTuple?displayProperty=nameWithType>
