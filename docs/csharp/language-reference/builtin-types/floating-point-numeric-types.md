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
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 17ae154780679dd1f42f43f1ec345cdc722815d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002188"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="01d78-103">Tipi numerici a virgola mobile (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="01d78-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="01d78-104">I **tipi numerici a virgola mobile** sono un subset dei **tipi semplici** e possono essere inizializzati con [*valori letterali*](#floating-point-literals).</span><span class="sxs-lookup"><span data-stu-id="01d78-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="01d78-105">Tutti i tipi a virgola mobile sono anche tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="01d78-105">All floating-point types are also value types.</span></span> <span data-ttu-id="01d78-106">Tutti i tipi numerici a virgola mobile supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), [di confronto e di uguaglianza](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="01d78-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="01d78-107">Caratteristiche dei tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="01d78-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="01d78-108">C# supporta i tipi a virgola mobile predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="01d78-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="01d78-109">Tipo/parola chiave C#</span><span class="sxs-lookup"><span data-stu-id="01d78-109">C# type/keyword</span></span>|<span data-ttu-id="01d78-110">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="01d78-110">Approximate range</span></span>|<span data-ttu-id="01d78-111">Precisione</span><span class="sxs-lookup"><span data-stu-id="01d78-111">Precision</span></span>|<span data-ttu-id="01d78-112">Size</span><span class="sxs-lookup"><span data-stu-id="01d78-112">Size</span></span>|<span data-ttu-id="01d78-113">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="01d78-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="01d78-114">Compreso tra ±1.5 x 10<sup>−45</sup> e ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="01d78-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="01d78-115">~6-9 cifre</span><span class="sxs-lookup"><span data-stu-id="01d78-115">~6-9 digits</span></span>|<span data-ttu-id="01d78-116">4 byte</span><span class="sxs-lookup"><span data-stu-id="01d78-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="01d78-117">Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="01d78-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="01d78-118">~15-17 cifre</span><span class="sxs-lookup"><span data-stu-id="01d78-118">~15-17 digits</span></span>|<span data-ttu-id="01d78-119">8 byte</span><span class="sxs-lookup"><span data-stu-id="01d78-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="01d78-120">Compreso tra ±1.0 x 10<sup>-28</sup> e ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="01d78-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="01d78-121">28-29 cifre</span><span class="sxs-lookup"><span data-stu-id="01d78-121">28-29 digits</span></span>|<span data-ttu-id="01d78-122">16 byte</span><span class="sxs-lookup"><span data-stu-id="01d78-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="01d78-123">Nella tabella precedente ogni tipo/parola chiave C# nella colonna più a sinistra è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="01d78-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="01d78-124">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="01d78-124">They are interchangeable.</span></span> <span data-ttu-id="01d78-125">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="01d78-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="01d78-126">Il valore predefinito di ogni tipo a virgola mobile è zero `0`.</span><span class="sxs-lookup"><span data-stu-id="01d78-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="01d78-127">Ogni tipo a virgola mobile ha costanti `MinValue` e `MaxValue` che specificano il valore finito minimo e massimo del tipo.</span><span class="sxs-lookup"><span data-stu-id="01d78-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="01d78-128">I tipi `float` e `double` forniscono anche costanti che rappresentano valori Not-a-Number (NaN) e infiniti.</span><span class="sxs-lookup"><span data-stu-id="01d78-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="01d78-129">Ad esempio, il tipo `double` fornisce le costanti seguenti: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> e <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01d78-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="01d78-130">Dato che il tipo `decimal` è caratterizzato da una maggiore precisione e da un intervallo più piccolo rispetto a `float` e `double`, è appropriato per calcoli finanziari e monetari.</span><span class="sxs-lookup"><span data-stu-id="01d78-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="01d78-131">In un'espressione è possibile combinare tipi [integrali](integral-numeric-types.md) e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="01d78-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="01d78-132">In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="01d78-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="01d78-133">La valutazione dell'espressione viene eseguita in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="01d78-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="01d78-134">Se uno dei tipi a virgola mobile è `double`, l'espressione restituirà un valore `double` o [bool](../keywords/bool.md) nei confronti relazionali o nei confronti per l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="01d78-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="01d78-135">Se l'espressione non contiene un tipo `double`, restituirà un valore `float` o [bool](../keywords/bool.md) nei confronti relazionali o nei confronti per l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="01d78-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="01d78-136">Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="01d78-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="01d78-137">Zero positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="01d78-137">Positive and negative zero</span></span>
- <span data-ttu-id="01d78-138">Infinito positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="01d78-138">Positive and negative infinity</span></span>
- <span data-ttu-id="01d78-139">Non un numero</span><span class="sxs-lookup"><span data-stu-id="01d78-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="01d78-140">Insieme finito di valori diversi da zero</span><span class="sxs-lookup"><span data-stu-id="01d78-140">The finite set of nonzero values</span></span>

<span data-ttu-id="01d78-141">Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="01d78-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="01d78-142">È possibile usare [stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md) oppure [stringhe di formato numerico personalizzato](../../../standard/base-types/custom-numeric-format-strings.md) per formattare un valore a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="01d78-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="01d78-143">Valori letterali a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="01d78-143">Floating-point literals</span></span>

<span data-ttu-id="01d78-144">Per impostazione predefinita, un valore letterale numerico a virgola mobile a destra dell'operatore di assegnazione viene gestito come tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="01d78-144">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="01d78-145">È possibile usare suffissi per convertire un valore letterale a virgola mobile o integrale in un tipo specifico:</span><span class="sxs-lookup"><span data-stu-id="01d78-145">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="01d78-146">Il suffisso `d` o `D` converte un valore letterale in un tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="01d78-146">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="01d78-147">Il suffisso `f` o `F` converte un valore letterale in un tipo `float`.</span><span class="sxs-lookup"><span data-stu-id="01d78-147">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="01d78-148">Il suffisso `m` o `M` converte un valore letterale in un tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="01d78-148">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="01d78-149">Negli esempi riportati di seguito viene illustrato ogni suffisso:</span><span class="sxs-lookup"><span data-stu-id="01d78-149">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="01d78-150">Conversioni</span><span class="sxs-lookup"><span data-stu-id="01d78-150">Conversions</span></span>

<span data-ttu-id="01d78-151">La conversione è implicita (denominata *conversione verso un tipo di dati più grande*) da `float` in `double` perché l'intervallo di valori `float` è un subset corretto di `double` e non si perde precisione da `float` in `double`.</span><span class="sxs-lookup"><span data-stu-id="01d78-151">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="01d78-152">È necessario usare un cast esplicito per convertire un tipo a virgola mobile in un altro tipo a virgola mobile quando non è definita una conversione implicita dal tipo di origine nel tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="01d78-152">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="01d78-153">Questa operazione è definita *conversione verso un tipo di dati più piccolo*.</span><span class="sxs-lookup"><span data-stu-id="01d78-153">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="01d78-154">Il caso esplicito è necessario perché la conversione può comportare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="01d78-154">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="01d78-155">La conversione non è implicita tra altri tipi a virgola mobile e il tipo `decimal` perché il tipo `decimal` ha una maggiore precisione rispetto a `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="01d78-155">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="01d78-156">Per altre informazioni sulle conversioni numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="01d78-156">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="01d78-157">Per altre informazioni sulle conversioni numeriche esplicite, vedere [Tabella delle conversioni numeriche esplicite](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="01d78-157">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="01d78-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01d78-158">See also</span></span>

- [<span data-ttu-id="01d78-159">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="01d78-159">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="01d78-160">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="01d78-160">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="01d78-161">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="01d78-161">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="01d78-162">Dati numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="01d78-162">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="01d78-163">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="01d78-163">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="01d78-164">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="01d78-164">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="01d78-165">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="01d78-165">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="01d78-166">Tabella di formattazione dei risultati numerici</span><span class="sxs-lookup"><span data-stu-id="01d78-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="01d78-167">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="01d78-167">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
