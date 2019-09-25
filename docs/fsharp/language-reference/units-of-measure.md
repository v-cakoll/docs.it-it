---
title: Unità di misura
description: Informazioni sul modo in cui i valori a virgola mobile e Signed Integer in F# possono avere unità di misura associate, che in genere vengono usate per indicare la lunghezza, il volume e la massa.
ms.date: 05/16/2016
ms.openlocfilehash: a81f7760301dc580e333d4659a72e6259d2c916b
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216683"
---
# <a name="units-of-measure"></a><span data-ttu-id="072c1-103">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="072c1-103">Units of Measure</span></span>

<span data-ttu-id="072c1-104">I valori a virgola mobile e F# Signed Integer in possono avere unità di misura associate, che in genere vengono usate per indicare lunghezza, volume, massa e così via.</span><span class="sxs-lookup"><span data-stu-id="072c1-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="072c1-105">Utilizzando quantità con unità, è possibile abilitare il compilatore per verificare che le relazioni aritmetiche dispongano delle unità corrette, evitando così errori di programmazione.</span><span class="sxs-lookup"><span data-stu-id="072c1-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="072c1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="072c1-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="072c1-107">Note</span><span class="sxs-lookup"><span data-stu-id="072c1-107">Remarks</span></span>

<span data-ttu-id="072c1-108">La sintassi precedente definisce *nome-unità* come unità di misura.</span><span class="sxs-lookup"><span data-stu-id="072c1-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="072c1-109">La parte facoltativa viene usata per definire una nuova misura in termini di unità definite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="072c1-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="072c1-110">La riga seguente, ad esempio, definisce la `cm` misura (centimetri).</span><span class="sxs-lookup"><span data-stu-id="072c1-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="072c1-111">La riga seguente definisce la misura `ml` (millilitro) come centimetro cubico (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="072c1-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="072c1-112">Nella sintassi precedente, *Measure* è una formula che include unità.</span><span class="sxs-lookup"><span data-stu-id="072c1-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="072c1-113">Nelle formule che coinvolgono unità, i poteri integrali sono supportati (positivi e negativi), spazi tra unità indicano un prodotto delle due unità, `*` indica anche un prodotto di unità e `/` indica un quoziente di unità.</span><span class="sxs-lookup"><span data-stu-id="072c1-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="072c1-114">Per un'unità reciproca, è possibile usare una potenza di tipo integer `/` negativa o un che indica una separazione tra il numeratore e il denominatore di una formula di unità.</span><span class="sxs-lookup"><span data-stu-id="072c1-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="072c1-115">Più unità nel denominatore devono essere racchiuse tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="072c1-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="072c1-116">Le unità separate da spazi dopo `/` un oggetto vengono interpretate come parte del denominatore, ma tutte le `*` unità successive a vengono interpretate come parte del numeratore.</span><span class="sxs-lookup"><span data-stu-id="072c1-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="072c1-117">È possibile usare 1 nelle espressioni Unit, solo per indicare una quantità senza dimensione o insieme ad altre unità, ad esempio nel numeratore.</span><span class="sxs-lookup"><span data-stu-id="072c1-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="072c1-118">Ad esempio, le unità per una frequenza verranno scritte come `1/s`, dove `s` indica i secondi.</span><span class="sxs-lookup"><span data-stu-id="072c1-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="072c1-119">Le parentesi non vengono utilizzate nelle formule di unità.</span><span class="sxs-lookup"><span data-stu-id="072c1-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="072c1-120">Nelle formule di unità non vengono specificate costanti di conversione numerica. Tuttavia, è possibile definire le costanti di conversione con le unità separatamente e usarle nei calcoli controllati dall'unità.</span><span class="sxs-lookup"><span data-stu-id="072c1-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="072c1-121">Le formule Unit che comportano la stessa operazione possono essere scritte in diversi modi equivalenti.</span><span class="sxs-lookup"><span data-stu-id="072c1-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="072c1-122">Pertanto, il compilatore converte le formule di unità in un formato coerente, che converte i poteri negativi in reciproci, raggruppa le unità in un numeratore singolo e un denominatore e dispone le unità nel numeratore e nel denominatore.</span><span class="sxs-lookup"><span data-stu-id="072c1-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="072c1-123">Ad esempio, le formule `kg m s^-2` unit e `m /s s * kg` sono entrambe convertite in. `kg m/s^2`</span><span class="sxs-lookup"><span data-stu-id="072c1-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="072c1-124">Le unità di misura vengono usate nelle espressioni a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="072c1-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="072c1-125">L'utilizzo di numeri a virgola mobile insieme a unità di misura associate aggiunge un altro livello di indipendenza dai tipi e consente di evitare gli errori di mancata corrispondenza tra le unità che possono verificarsi nelle formule quando si utilizzano numeri a virgola mobile con tipizzazione debole.</span><span class="sxs-lookup"><span data-stu-id="072c1-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="072c1-126">Se si scrive un'espressione a virgola mobile che usa unità, le unità nell'espressione devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="072c1-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="072c1-127">È possibile annotare i valori letterali con una formula di unità tra parentesi acute, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="072c1-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="072c1-128">Non viene inserito uno spazio tra il numero e la parentesi angolare; Tuttavia, è possibile includere un suffisso letterale `f`, ad esempio, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="072c1-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="072c1-129">Tale annotazione consente di modificare il tipo del valore letterale dal tipo primitivo (ad esempio `float`) a un tipo dimensionato, `float<cm>` ad esempio o `float<miles/hour>`, in questo caso.</span><span class="sxs-lookup"><span data-stu-id="072c1-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="072c1-130">Un'annotazione `<1>` unità di indica una quantità senza dimensione e il relativo tipo è equivalente al tipo primitivo senza un parametro di unità.</span><span class="sxs-lookup"><span data-stu-id="072c1-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="072c1-131">Il tipo di unità di misura è un tipo a virgola mobile o integrale con segno insieme a un'annotazione unità aggiuntiva, indicata tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="072c1-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="072c1-132">Pertanto, quando si scrive il tipo di una conversione da `g` (grammi) a `kg` (chilogrammi), si descrivono i tipi come segue.</span><span class="sxs-lookup"><span data-stu-id="072c1-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="072c1-133">Le unità di misura vengono utilizzate per il controllo delle unità in fase di compilazione ma non vengono rese permanente nell'ambiente di Runtime.</span><span class="sxs-lookup"><span data-stu-id="072c1-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="072c1-134">Pertanto, non influiscono sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="072c1-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="072c1-135">Le unità di misura possono essere applicate a qualsiasi tipo, non solo ai tipi a virgola mobile. Tuttavia, solo i tipi a virgola mobile, i tipi integrali con segno e i tipi decimali supportano le quantità dimensionate.</span><span class="sxs-lookup"><span data-stu-id="072c1-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="072c1-136">Pertanto, è opportuno usare unità di misura sui tipi primitivi e sulle aggregazioni che contengono questi tipi primitivi.</span><span class="sxs-lookup"><span data-stu-id="072c1-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="072c1-137">Nell'esempio seguente viene illustrato l'utilizzo di unità di misura.</span><span class="sxs-lookup"><span data-stu-id="072c1-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="072c1-138">Nell'esempio di codice riportato di seguito viene illustrato come eseguire la conversione da un numero a virgola mobile non dimensionato a un valore a virgola mobile a dimensione.</span><span class="sxs-lookup"><span data-stu-id="072c1-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="072c1-139">È sufficiente moltiplicare per 1,0, applicando le dimensioni al 1,0.</span><span class="sxs-lookup"><span data-stu-id="072c1-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="072c1-140">È possibile astrarre questo oggetto in una `degreesFahrenheit`funzione come.</span><span class="sxs-lookup"><span data-stu-id="072c1-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="072c1-141">Inoltre, quando si passano valori dimensionati a funzioni che prevedono numeri a virgola mobile senza dimensione, è necessario annullare le unità `float` o eseguire il `float` cast a utilizzando l'operatore.</span><span class="sxs-lookup"><span data-stu-id="072c1-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="072c1-142">In questo esempio si divide `1.0<degC>` per per gli argomenti in `printf` perché `printf` prevede quantità di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="072c1-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="072c1-143">Nella sessione di esempio seguente vengono mostrati gli output di e gli input di questo codice.</span><span class="sxs-lookup"><span data-stu-id="072c1-143">The following example session shows the outputs from and inputs to this code.</span></span>

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="072c1-144">Uso di unità generiche</span><span class="sxs-lookup"><span data-stu-id="072c1-144">Using Generic Units</span></span>

<span data-ttu-id="072c1-145">È possibile scrivere funzioni generiche che operano su dati a cui è associata un'unità di misura.</span><span class="sxs-lookup"><span data-stu-id="072c1-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="072c1-146">A tale scopo, specificare un tipo insieme a un'unità generica come parametro di tipo, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="072c1-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="072c1-147">Creazione di tipi aggregati con unità generiche</span><span class="sxs-lookup"><span data-stu-id="072c1-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="072c1-148">Nel codice seguente viene illustrato come creare un tipo di aggregazione costituito da singoli valori a virgola mobile con unità generiche.</span><span class="sxs-lookup"><span data-stu-id="072c1-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="072c1-149">In questo modo è possibile creare un singolo tipo che funzioni con un'ampia gamma di unità.</span><span class="sxs-lookup"><span data-stu-id="072c1-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="072c1-150">Inoltre, le unità generiche conservano l'indipendenza dai tipi assicurando che un tipo generico con un set di unità sia un tipo diverso da quello dello stesso tipo generico con un set di unità diverso.</span><span class="sxs-lookup"><span data-stu-id="072c1-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="072c1-151">La base di questa tecnica è che l' `Measure` attributo può essere applicato al parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="072c1-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="072c1-152">Unità in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="072c1-152">Units at Runtime</span></span>

<span data-ttu-id="072c1-153">Le unità di misura vengono usate per il controllo dei tipi statici.</span><span class="sxs-lookup"><span data-stu-id="072c1-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="072c1-154">Quando vengono compilati i valori a virgola mobile, le unità di misura vengono eliminate, quindi le unità vengono perse in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="072c1-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="072c1-155">Pertanto, qualsiasi tentativo di implementare le funzionalità che dipendono dal controllo delle unità in fase di esecuzione non è possibile.</span><span class="sxs-lookup"><span data-stu-id="072c1-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="072c1-156">Ad esempio, l'implementazione `ToString` di una funzione per stampare le unità non è possibile.</span><span class="sxs-lookup"><span data-stu-id="072c1-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="072c1-157">Conversioni</span><span class="sxs-lookup"><span data-stu-id="072c1-157">Conversions</span></span>

<span data-ttu-id="072c1-158">Per convertire un tipo che dispone di unità (ad esempio `float<'u>`,) in un tipo che non dispone di unità, è possibile utilizzare la funzione di conversione standard.</span><span class="sxs-lookup"><span data-stu-id="072c1-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="072c1-159">Ad esempio, è possibile usare `float` per eseguire la conversione `float` in un valore che non dispone di unità, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="072c1-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="072c1-160">Per convertire un valore senza unità in un valore con unità, è possibile moltiplicare per un valore 1 o 1,0 annotato con le unità appropriate.</span><span class="sxs-lookup"><span data-stu-id="072c1-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="072c1-161">Tuttavia, per la scrittura di livelli di interoperabilità, sono disponibili anche alcune funzioni esplicite che è possibile usare per convertire i valori senza unità in valori con unità.</span><span class="sxs-lookup"><span data-stu-id="072c1-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="072c1-162">Si trovano nel modulo [Microsoft. FSharp. Core. LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) .</span><span class="sxs-lookup"><span data-stu-id="072c1-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="072c1-163">Ad esempio, per eseguire la conversione da un `float` elemento a `float<cm>`un oggetto, usare [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="072c1-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="072c1-164">Unità di misura nella libreria F# principale</span><span class="sxs-lookup"><span data-stu-id="072c1-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="072c1-165">Una libreria di unità è disponibile nello `FSharp.Data.UnitSystems.SI` spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="072c1-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="072c1-166">Sono incluse le unità si sia nella forma dei simboli ( `m` ad esempio per il `UnitSymbols` contatore) nello spazio dei nomi, sia nel nome completo `meter` (ad esempio per il `UnitNames` contatore) nello spazio dei nomi secondario.</span><span class="sxs-lookup"><span data-stu-id="072c1-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="072c1-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="072c1-167">See also</span></span>

- [<span data-ttu-id="072c1-168">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="072c1-168">F# Language Reference</span></span>](index.md)
