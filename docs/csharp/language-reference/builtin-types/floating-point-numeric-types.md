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
ms.openlocfilehash: 0d97b3ffd587e8398e5572706a47937716a6e709
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236052"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="534a8-103">Tipi numerici a virgola mobile (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="534a8-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="534a8-104">I **tipi numerici a virgola mobile** sono un subset dei **tipi semplici** e possono essere inizializzati con [*valori letterali*](#floating-point-literals).</span><span class="sxs-lookup"><span data-stu-id="534a8-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="534a8-105">Tutti i tipi a virgola mobile sono anche tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="534a8-105">All floating-point types are also value types.</span></span> <span data-ttu-id="534a8-106">Tutti i tipi numerici a virgola mobile supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), [di confronto e di uguaglianza](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="534a8-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="534a8-107">Caratteristiche dei tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="534a8-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="534a8-108">C# supporta i tipi a virgola mobile predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="534a8-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="534a8-109">Tipo/parola chiave C#</span><span class="sxs-lookup"><span data-stu-id="534a8-109">C# type/keyword</span></span>|<span data-ttu-id="534a8-110">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="534a8-110">Approximate range</span></span>|<span data-ttu-id="534a8-111">Precisione</span><span class="sxs-lookup"><span data-stu-id="534a8-111">Precision</span></span>|<span data-ttu-id="534a8-112">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="534a8-112">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|
|`float`|<span data-ttu-id="534a8-113">Compreso tra ±1.5 x 10<sup>−45</sup> e ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="534a8-113">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="534a8-114">~6-9 cifre</span><span class="sxs-lookup"><span data-stu-id="534a8-114">~6-9 digits</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="534a8-115">Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="534a8-115">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="534a8-116">~15-17 cifre</span><span class="sxs-lookup"><span data-stu-id="534a8-116">~15-17 digits</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="534a8-117">Compreso tra ±1.0 x 10<sup>-28</sup> e ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="534a8-117">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="534a8-118">28-29 cifre</span><span class="sxs-lookup"><span data-stu-id="534a8-118">28-29 digits</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="534a8-119">Nella tabella precedente ogni tipo/parola chiave C# nella colonna più a sinistra è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="534a8-119">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="534a8-120">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="534a8-120">They are interchangeable.</span></span> <span data-ttu-id="534a8-121">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="534a8-121">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="534a8-122">Il valore predefinito di ogni tipo a virgola mobile è zero `0`.</span><span class="sxs-lookup"><span data-stu-id="534a8-122">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="534a8-123">Ogni tipo a virgola mobile ha costanti `MinValue` e `MaxValue` che specificano il valore finito minimo e massimo del tipo.</span><span class="sxs-lookup"><span data-stu-id="534a8-123">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="534a8-124">I tipi `float` e `double` forniscono anche costanti che rappresentano valori Not-a-Number (NaN) e infiniti.</span><span class="sxs-lookup"><span data-stu-id="534a8-124">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="534a8-125">Ad esempio, il tipo `double` fornisce le costanti seguenti: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> e <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="534a8-125">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="534a8-126">Dato che il tipo `decimal` è caratterizzato da una maggiore precisione e da un intervallo più piccolo rispetto a `float` e `double`, è appropriato per calcoli finanziari e monetari.</span><span class="sxs-lookup"><span data-stu-id="534a8-126">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="534a8-127">In un'espressione è possibile combinare tipi [integrali](integral-numeric-types.md) e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="534a8-127">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="534a8-128">In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="534a8-128">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="534a8-129">La valutazione dell'espressione viene eseguita in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="534a8-129">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="534a8-130">Se uno dei tipi a virgola mobile è `double`, l'espressione restituirà un valore `double` o [bool](../keywords/bool.md) nei confronti relazionali o nei confronti per l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="534a8-130">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="534a8-131">Se l'espressione non contiene un tipo `double`, restituirà un valore `float` o [bool](../keywords/bool.md) nei confronti relazionali o nei confronti per l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="534a8-131">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="534a8-132">Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="534a8-132">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="534a8-133">Zero positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="534a8-133">Positive and negative zero</span></span>
- <span data-ttu-id="534a8-134">Infinito positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="534a8-134">Positive and negative infinity</span></span>
- <span data-ttu-id="534a8-135">Non un numero</span><span class="sxs-lookup"><span data-stu-id="534a8-135">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="534a8-136">Insieme finito di valori diversi da zero</span><span class="sxs-lookup"><span data-stu-id="534a8-136">The finite set of nonzero values</span></span>

<span data-ttu-id="534a8-137">Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="534a8-137">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="534a8-138">È possibile usare [stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md) oppure [stringhe di formato numerico personalizzato](../../../standard/base-types/custom-numeric-format-strings.md) per formattare un valore a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="534a8-138">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="534a8-139">Valori letterali a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="534a8-139">Floating-point literals</span></span>

<span data-ttu-id="534a8-140">Per impostazione predefinita, un valore letterale numerico a virgola mobile a destra dell'operatore di assegnazione viene gestito come tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="534a8-140">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="534a8-141">È possibile usare suffissi per convertire un valore letterale a virgola mobile o integrale in un tipo specifico:</span><span class="sxs-lookup"><span data-stu-id="534a8-141">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="534a8-142">Il suffisso `d` o `D` converte un valore letterale in un tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="534a8-142">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="534a8-143">Il suffisso `f` o `F` converte un valore letterale in un tipo `float`.</span><span class="sxs-lookup"><span data-stu-id="534a8-143">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="534a8-144">Il suffisso `m` o `M` converte un valore letterale in un tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="534a8-144">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="534a8-145">Negli esempi riportati di seguito viene illustrato ogni suffisso:</span><span class="sxs-lookup"><span data-stu-id="534a8-145">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="534a8-146">Conversioni</span><span class="sxs-lookup"><span data-stu-id="534a8-146">Conversions</span></span>

<span data-ttu-id="534a8-147">La conversione è implicita (denominata *conversione verso un tipo di dati più grande*) da `float` in `double` perché l'intervallo di valori `float` è un subset corretto di `double` e non si perde precisione da `float` in `double`.</span><span class="sxs-lookup"><span data-stu-id="534a8-147">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="534a8-148">È necessario usare un cast esplicito per convertire un tipo a virgola mobile in un altro tipo a virgola mobile quando non è definita una conversione implicita dal tipo di origine nel tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="534a8-148">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="534a8-149">Questa operazione è definita *conversione verso un tipo di dati più piccolo*.</span><span class="sxs-lookup"><span data-stu-id="534a8-149">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="534a8-150">Il caso esplicito è necessario perché la conversione può comportare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="534a8-150">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="534a8-151">La conversione non è implicita tra altri tipi a virgola mobile e il tipo `decimal` perché il tipo `decimal` ha una maggiore precisione rispetto a `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="534a8-151">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="534a8-152">Per altre informazioni sulle conversioni numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="534a8-152">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="534a8-153">Per altre informazioni sulle conversioni numeriche esplicite, vedere [Tabella delle conversioni numeriche esplicite](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="534a8-153">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="534a8-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="534a8-154">See also</span></span>

- [<span data-ttu-id="534a8-155">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="534a8-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="534a8-156">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="534a8-156">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="534a8-157">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="534a8-157">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="534a8-158">Dati numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="534a8-158">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="534a8-159">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="534a8-159">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="534a8-160">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="534a8-160">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="534a8-161">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="534a8-161">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="534a8-162">Tabella di formattazione dei risultati numerici</span><span class="sxs-lookup"><span data-stu-id="534a8-162">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="534a8-163">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="534a8-163">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
