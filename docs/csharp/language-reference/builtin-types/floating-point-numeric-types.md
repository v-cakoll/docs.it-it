---
title: Tipi numerici a virgola mobile - Riferimenti per C#
description: Panoramica dei tipi a virgola mobile incorporati di C#
ms.date: 06/30/2019
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 738368abd9db75fbd97d1913324cab3b6e869c56
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664191"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="35ef3-103">Tipi numerici a virgola mobile (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="35ef3-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="35ef3-104">I **tipi numerici a virgola mobile** sono un subset dei **tipi semplici** e possono essere inizializzati con [*valori letterali*](#floating-point-literals).</span><span class="sxs-lookup"><span data-stu-id="35ef3-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="35ef3-105">Tutti i tipi a virgola mobile sono anche tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="35ef3-105">All floating-point types are also value types.</span></span> <span data-ttu-id="35ef3-106">Tutti i tipi numerici a virgola mobile supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), [di confronto e di uguaglianza](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="35ef3-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md) [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

<span data-ttu-id="35ef3-107">La tabella seguente illustra la precisione e gli intervalli approssimativi per i tipi a virgola mobile:</span><span class="sxs-lookup"><span data-stu-id="35ef3-107">The following table shows the precision and approximate ranges for the floating-point types:</span></span>
  
|<span data-ttu-id="35ef3-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="35ef3-108">Type</span></span>|<span data-ttu-id="35ef3-109">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="35ef3-109">Approximate range</span></span>|<span data-ttu-id="35ef3-110">Precisione</span><span class="sxs-lookup"><span data-stu-id="35ef3-110">Precision</span></span>|  
|----------|-----------------------|---------------|  
|`float`|<span data-ttu-id="35ef3-111">Compreso tra ±1.5 x 10<sup>−45</sup> e ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="35ef3-111">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="35ef3-112">~6-9 cifre</span><span class="sxs-lookup"><span data-stu-id="35ef3-112">~6-9 digits</span></span>|  
|`double`|<span data-ttu-id="35ef3-113">Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="35ef3-113">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="35ef3-114">~15-17 cifre</span><span class="sxs-lookup"><span data-stu-id="35ef3-114">~15-17 digits</span></span>|  
|`decimal`|<span data-ttu-id="35ef3-115">Compreso tra ±1.0 x 10<sup>-28</sup> e ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="35ef3-115">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="35ef3-116">28-29 cifre</span><span class="sxs-lookup"><span data-stu-id="35ef3-116">28-29 digits</span></span>|  

<span data-ttu-id="35ef3-117">Il valore predefinito per tutti i tipi a virgola mobile è `0`.</span><span class="sxs-lookup"><span data-stu-id="35ef3-117">The default value for all floating-point types is `0`.</span></span> <span data-ttu-id="35ef3-118">Ogni tipo a virgola mobile ha costanti denominate `MinValue` e `MaxValue` per il valore minimo e massimo del tipo.</span><span class="sxs-lookup"><span data-stu-id="35ef3-118">Each of the floating-point types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span> <span data-ttu-id="35ef3-119">I tipi `float` e `double` hanno costanti aggiuntive per `PositiveInfinity`, `NegativeInfinity`, e `NaN` (per "Non un numero").</span><span class="sxs-lookup"><span data-stu-id="35ef3-119">The `float` and `double` types have additional constants for `PositiveInfinity`, `NegativeInfinity`, and `NaN` (for "Not a Number").</span></span> <span data-ttu-id="35ef3-120">Il tipo `decimal` include costanti per `Zero`, `One` e `MinusOne`.</span><span class="sxs-lookup"><span data-stu-id="35ef3-120">The `decimal` type includes constants for `Zero`, `One`, and `MinusOne`.</span></span>

<span data-ttu-id="35ef3-121">Il tipo `decimal` è caratterizzato da una maggiore precisione e da un intervallo ridotto rispetto a `float` e `double`, che lo rendono appropriato per calcoli finanziari e monetari.</span><span class="sxs-lookup"><span data-stu-id="35ef3-121">The `decimal` type has more precision and a smaller range than both `float` and `double`, which makes it appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="35ef3-122">In un'espressione è possibile combinare tipi integrali e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="35ef3-122">You can mix integral types and floating-point types in an expression.</span></span> <span data-ttu-id="35ef3-123">In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="35ef3-123">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="35ef3-124">La valutazione dell'espressione viene eseguita in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="35ef3-124">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="35ef3-125">Se uno dei tipi a virgola mobile è `double`, l'espressione restituirà un valore `double` o [bool](../keywords/bool.md) nei confronti relazionali o nei confronti per l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="35ef3-125">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="35ef3-126">Se l'espressione non contiene un tipo `double`, restituirà un valore `float` o [bool](../keywords/bool.md) nei confronti relazionali o nei confronti per l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="35ef3-126">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="35ef3-127">Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="35ef3-127">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="35ef3-128">Zero positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="35ef3-128">Positive and negative zero</span></span>
- <span data-ttu-id="35ef3-129">Infinito positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="35ef3-129">Positive and negative infinity</span></span>
- <span data-ttu-id="35ef3-130">Non un numero</span><span class="sxs-lookup"><span data-stu-id="35ef3-130">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="35ef3-131">Insieme finito di valori diversi da zero</span><span class="sxs-lookup"><span data-stu-id="35ef3-131">The finite set of nonzero values</span></span>

<span data-ttu-id="35ef3-132">Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="35ef3-132">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="35ef3-133">È possibile usare [stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md) oppure [stringhe di formato numerico personalizzato](../../../standard/base-types/custom-numeric-format-strings.md) per formattare un valore a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="35ef3-133">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="35ef3-134">Valori letterali a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="35ef3-134">Floating-point literals</span></span>

<span data-ttu-id="35ef3-135">Per impostazione predefinita, un valore letterale numerico a virgola mobile a destra dell'operatore di assegnazione viene gestito come tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="35ef3-135">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="35ef3-136">È possibile usare suffissi per convertire un valore letterale a virgola mobile o integrale in un tipo specifico:</span><span class="sxs-lookup"><span data-stu-id="35ef3-136">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="35ef3-137">Il suffisso `d` o `D` converte un valore letterale in un tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="35ef3-137">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="35ef3-138">Il suffisso `f` o `F` converte un valore letterale in un tipo `float`.</span><span class="sxs-lookup"><span data-stu-id="35ef3-138">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="35ef3-139">Il suffisso `m` o `M` converte un valore letterale in un tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="35ef3-139">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="35ef3-140">Negli esempi riportati di seguito viene illustrato ogni suffisso:</span><span class="sxs-lookup"><span data-stu-id="35ef3-140">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="35ef3-141">Conversioni</span><span class="sxs-lookup"><span data-stu-id="35ef3-141">Conversions</span></span>

<span data-ttu-id="35ef3-142">La conversione è implicita (denominata *conversione verso un tipo di dati più grande*) da `float` in `double` perché l'intervallo di valori `float` è un subset corretto di `double` e non si perde precisione da `float` in `double`.</span><span class="sxs-lookup"><span data-stu-id="35ef3-142">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span> 

<span data-ttu-id="35ef3-143">È necessario usare un cast esplicito per convertire un tipo a virgola mobile in un altro tipo a virgola mobile quando non è definita una conversione implicita dal tipo di origine nel tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="35ef3-143">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="35ef3-144">Questa operazione è definita *conversione verso un tipo di dati più piccolo*.</span><span class="sxs-lookup"><span data-stu-id="35ef3-144">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="35ef3-145">Il caso esplicito è necessario perché la conversione può comportare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="35ef3-145">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="35ef3-146">La conversione non è implicita tra altri tipi a virgola mobile e il tipo `decimal` perché il tipo `decimal` ha una maggiore precisione rispetto a `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="35ef3-146">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="35ef3-147">Per altre informazioni sulle conversioni numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="35ef3-147">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="35ef3-148">Per altre informazioni sulle conversioni numeriche esplicite, vedere [Tabella delle conversioni numeriche esplicite](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="35ef3-148">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35ef3-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35ef3-149">See also</span></span>

- [<span data-ttu-id="35ef3-150">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="35ef3-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="35ef3-151">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="35ef3-151">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="35ef3-152">Tabella dei valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="35ef3-152">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="35ef3-153">Tabella di formattazione dei risultati numerici</span><span class="sxs-lookup"><span data-stu-id="35ef3-153">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="35ef3-154">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="35ef3-154">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="35ef3-155">Dati numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="35ef3-155">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="35ef3-156">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="35ef3-156">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="35ef3-157">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="35ef3-157">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="35ef3-158">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="35ef3-158">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="35ef3-159">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="35ef3-159">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
