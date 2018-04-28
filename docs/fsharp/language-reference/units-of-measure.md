---
title: Unità di misura (F#)
description: 'A virgola mobile come informazioni e i valori interi con segno in F # è possono associare le unità di misura, che sono in genere usate per indicare lunghezza, volume e massa.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 336a1e04426fb39f5ceb98e06a06cd7eadc36e85
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="units-of-measure"></a><span data-ttu-id="088e7-103">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="088e7-103">Units of Measure</span></span>

<span data-ttu-id="088e7-104">A virgola mobile e interi con segno in F # possono essere associate unità di misura, che sono in genere usata per indicare la lunghezza, volume, massa, e così via.</span><span class="sxs-lookup"><span data-stu-id="088e7-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="088e7-105">Con quantità di unità, consente al compilatore di verificare che le relazioni aritmetiche dispongano di unità corretta, che consente di evitare errori di programmazione.</span><span class="sxs-lookup"><span data-stu-id="088e7-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>


## <a name="syntax"></a><span data-ttu-id="088e7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="088e7-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="088e7-107">Note</span><span class="sxs-lookup"><span data-stu-id="088e7-107">Remarks</span></span>
<span data-ttu-id="088e7-108">Definisce la sintassi precedente *-nome dell'unità* come un'unità di misura.</span><span class="sxs-lookup"><span data-stu-id="088e7-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="088e7-109">La parte facoltativa viene utilizzata per definire una nuova misura in termini di unità definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="088e7-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="088e7-110">Ad esempio, la riga seguente definisce la misura `cm` (centimetri).</span><span class="sxs-lookup"><span data-stu-id="088e7-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="088e7-111">La riga seguente definisce la misura `ml` (millimetro) come un centimetro (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="088e7-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="088e7-112">Nella sintassi precedente, *misura* è una formula che vengono utilizzate unità.</span><span class="sxs-lookup"><span data-stu-id="088e7-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="088e7-113">Nelle formule che comportano l'unità, sono supportate le potenze integrali (positive e negative), gli spazi tra le unità indicano un prodotto di due unità, `*` indica un prodotto di unità, e `/` indica un quoziente di unità.</span><span class="sxs-lookup"><span data-stu-id="088e7-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="088e7-114">Per un'unità reciproca, è possibile utilizzare una potenza intera negativa o `/` che indica una separazione tra il numeratore e un denominatore di una formula di unità.</span><span class="sxs-lookup"><span data-stu-id="088e7-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="088e7-115">Più unità nel denominatore devono essere racchiusi tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="088e7-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="088e7-116">Unità di misura separati da spazi dopo un `/` vengono interpretati come parte del denominatore, ma qualsiasi unità che segue un `*` vengono interpretati come parte del numeratore.</span><span class="sxs-lookup"><span data-stu-id="088e7-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="088e7-117">È possibile utilizzare 1 nelle espressioni di unità, da solo per indicare una quantità, senza o con altre unità, ad esempio nel numeratore.</span><span class="sxs-lookup"><span data-stu-id="088e7-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="088e7-118">Ad esempio, le unità per una velocità verrebbero scritto come `1/s`, dove `s` indica i secondi.</span><span class="sxs-lookup"><span data-stu-id="088e7-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="088e7-119">Parentesi non vengono utilizzate nelle formule di unità.</span><span class="sxs-lookup"><span data-stu-id="088e7-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="088e7-120">Non si specifica le costanti di conversione numerica nelle formule di unità; Tuttavia, è possibile definire le costanti di conversione con unità separatamente e utilizzarle nei calcoli unità controllata.</span><span class="sxs-lookup"><span data-stu-id="088e7-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="088e7-121">Le formule di unità con lo stesso significato possono essere scritti in diversi modi equivalenti.</span><span class="sxs-lookup"><span data-stu-id="088e7-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="088e7-122">Pertanto, il compilatore converte le formule di unità in un formato coerente, che converte potenze negative in reciproci, unità di gruppi in un unico numeratore e un denominatore e dispone in ordine alfabetico le unità in cui il numeratore e il denominatore.</span><span class="sxs-lookup"><span data-stu-id="088e7-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="088e7-123">Ad esempio, le formule di unità `kg m s^-2` e `m /s s * kg` vengono convertiti in `kg m/s^2`.</span><span class="sxs-lookup"><span data-stu-id="088e7-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="088e7-124">Si utilizzano unità di misura in espressioni a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="088e7-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="088e7-125">Utilizzando i numeri a virgola mobile insieme associate unità di misura consente di aggiungere un altro livello dell'indipendenza dai tipi e aiuta a evitare gli errori di mancata corrispondenza di unità che possono verificarsi nelle formule, quando si utilizzano tipizzazione numeri a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="088e7-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="088e7-126">Se si scrivono mobile espressione punto che utilizza le unità, le unità nell'espressione devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="088e7-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="088e7-127">È possibile annotare i valori letterali con una formula di unità tra parentesi quadre, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="088e7-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="088e7-128">Non inserire uno spazio tra il numero e la parentesi angolare; Tuttavia, è possibile includere un suffisso letterale, ad esempio `f`, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="088e7-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="088e7-129">Tale annotazione modifica il tipo del valore letterale di tipo primitivo (ad esempio `float`) a un tipo con dimensioni, ad esempio `float<cm>` o, in questo caso, `float<miles/hour>`.</span><span class="sxs-lookup"><span data-stu-id="088e7-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="088e7-130">Un'annotazione di unità di `<1>` indica una quantità senza e il relativo tipo è equivalente al tipo primitivo senza un parametro di unità.</span><span class="sxs-lookup"><span data-stu-id="088e7-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="088e7-131">Il tipo di un'unità di misura è una virgola mobile o un tipo integrale con un'annotazione di unità aggiuntive, indicata tra parentesi quadre firmato.</span><span class="sxs-lookup"><span data-stu-id="088e7-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="088e7-132">Pertanto, quando si scrive il tipo di una conversione da `g` (g) per `kg` (kg), si descrivono i tipi, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="088e7-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="088e7-133">Unità di misura vengono utilizzate per il controllo dell'unità in fase di compilazione, ma non vengono rese persistenti nell'ambiente di runtime.</span><span class="sxs-lookup"><span data-stu-id="088e7-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="088e7-134">Pertanto, non influiscono sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="088e7-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="088e7-135">Unità di misura può essere applicata a qualsiasi tipo, non solo tipi a virgola mobile; Tuttavia, solo tipi a virgola mobile, firma tipi integrali e tipi decimali supporto dimensionata quantità.</span><span class="sxs-lookup"><span data-stu-id="088e7-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="088e7-136">Pertanto, è solo logico utilizzare unità di misura su tipi primitivi e le aggregazioni che contengono questi tipi primitivi.</span><span class="sxs-lookup"><span data-stu-id="088e7-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="088e7-137">Nell'esempio seguente viene illustrato l'utilizzo di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="088e7-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
<span data-ttu-id="088e7-138">Esempio di codice seguente viene illustrato come convertire un numero a virgola mobile senza un valore a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="088e7-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="088e7-139">Sufficiente moltiplicare per 1,0, applicare le dimensioni di 1.0.</span><span class="sxs-lookup"><span data-stu-id="088e7-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="088e7-140">È possibile astrarre questo in una funzione come `degreesFahrenheit`.</span><span class="sxs-lookup"><span data-stu-id="088e7-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="088e7-141">Inoltre, quando si passano valori con dimensioni a funzioni che prevedono numeri a virgola mobile senza dimensioni, è necessario eliminare le unità o eseguire il cast a `float` utilizzando il `float` operatore.</span><span class="sxs-lookup"><span data-stu-id="088e7-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="088e7-142">In questo esempio, si divide per `1.0<degC>` per gli argomenti di `printf` perché `printf` prevede quantità senza dimensioni.</span><span class="sxs-lookup"><span data-stu-id="088e7-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="088e7-143">La sessione di esempio seguente viene illustrato l'output da e gli input per questo codice.</span><span class="sxs-lookup"><span data-stu-id="088e7-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="088e7-144">Utilizzo di unità generiche</span><span class="sxs-lookup"><span data-stu-id="088e7-144">Using Generic Units</span></span>
<span data-ttu-id="088e7-145">È possibile scrivere funzioni generiche che operano sui dati che sono associata un'unità di misura.</span><span class="sxs-lookup"><span data-stu-id="088e7-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="088e7-146">Eseguire questa operazione specificando un tipo di insieme a un'unità generico come un parametro di tipo, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="088e7-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="088e7-147">Creazione di tipi di aggregazione con unità generiche</span><span class="sxs-lookup"><span data-stu-id="088e7-147">Creating Aggregate Types with Generic Units</span></span>
<span data-ttu-id="088e7-148">Il codice seguente viene illustrato come creare un tipo di aggregazione che è costituito da singoli valori a virgola mobile con unità generiche.</span><span class="sxs-lookup"><span data-stu-id="088e7-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="088e7-149">In questo modo un unico tipo da creare che funziona con un'ampia gamma di unità.</span><span class="sxs-lookup"><span data-stu-id="088e7-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="088e7-150">Inoltre, le unità generiche mantengono indipendenza dai tipi assicurando che un tipo generico che ha un set di unità è un tipo diverso rispetto al tipo generico stesso con un set diverso di unità.</span><span class="sxs-lookup"><span data-stu-id="088e7-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="088e7-151">Questa tecnica è che il `Measure` attributo può essere applicato al parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="088e7-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a><span data-ttu-id="088e7-152">Unità in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="088e7-152">Units at Runtime</span></span>
<span data-ttu-id="088e7-153">Unità di misura vengono utilizzate per il controllo dei tipi statici.</span><span class="sxs-lookup"><span data-stu-id="088e7-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="088e7-154">Se i valori a virgola mobile vengono compilati, vengono eliminate le unità di misura, quindi le unità vengono perse in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="088e7-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="088e7-155">Pertanto, qualsiasi tentativo di implementare funzionalità che dipende dalla verifica le unità in fase di esecuzione non è possibile.</span><span class="sxs-lookup"><span data-stu-id="088e7-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="088e7-156">Ad esempio possibile implementare un `ToString` funzione per stampare le unità non è possibile.</span><span class="sxs-lookup"><span data-stu-id="088e7-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>


## <a name="conversions"></a><span data-ttu-id="088e7-157">Conversioni</span><span class="sxs-lookup"><span data-stu-id="088e7-157">Conversions</span></span>
<span data-ttu-id="088e7-158">Per convertire un tipo che dispone di unità (ad esempio, `float<'u>`) a un tipo che non dispone di unità, è possibile utilizzare la funzione di conversione standard.</span><span class="sxs-lookup"><span data-stu-id="088e7-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="088e7-159">Ad esempio, è possibile utilizzare `float` per convertire un `float` valore che non dispone di unità, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="088e7-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="088e7-160">Per convertire un valore senza unità in un valore che dispone di unità, è possibile moltiplicare per un valore di 1 o 1,0 annotato con le unità appropriate.</span><span class="sxs-lookup"><span data-stu-id="088e7-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="088e7-161">Tuttavia, per la scrittura di livelli di interoperabilità, esistono anche alcune funzioni esplicite che è possibile utilizzare per convertire i valori senza unità in valori con unità di misura.</span><span class="sxs-lookup"><span data-stu-id="088e7-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="088e7-162">Si tratta nel [LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) modulo.</span><span class="sxs-lookup"><span data-stu-id="088e7-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="088e7-163">Ad esempio, per eseguire la conversione da un valore `float` per un `float<cm>`, utilizzare [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="088e7-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a><span data-ttu-id="088e7-164">Unità di misura in F # Power Pack</span><span class="sxs-lookup"><span data-stu-id="088e7-164">Units of Measure in the F# Power Pack</span></span>
<span data-ttu-id="088e7-165">Una raccolta di unità è disponibile in PowerPacks F #.</span><span class="sxs-lookup"><span data-stu-id="088e7-165">A unit library is available in the F# PowerPack.</span></span> <span data-ttu-id="088e7-166">La libreria di unità include unità SI e costanti fisiche.</span><span class="sxs-lookup"><span data-stu-id="088e7-166">The unit library includes SI units and physical constants.</span></span>


## <a name="see-also"></a><span data-ttu-id="088e7-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="088e7-167">See Also</span></span>
[<span data-ttu-id="088e7-168">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="088e7-168">F# Language Reference</span></span>](index.md)
