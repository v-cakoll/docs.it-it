---
title: Tipi numerici a virgola mobile - Riferimenti per C#
description: Panoramica dei tipi a virgola mobile incorporati di C#
ms.date: 10/18/2019
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
ms.openlocfilehash: fa6cbb869d90113414cc6f8ffe231386c3596b1d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579378"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="bd30e-103">Tipi numerici a virgola mobile (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bd30e-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="bd30e-104">I **tipi numerici a virgola mobile** sono un subset dei **tipi semplici** e possono essere inizializzati con [*valori letterali*](#real-literals).</span><span class="sxs-lookup"><span data-stu-id="bd30e-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#real-literals).</span></span> <span data-ttu-id="bd30e-105">Tutti i tipi a virgola mobile sono anche tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="bd30e-105">All floating-point types are also value types.</span></span> <span data-ttu-id="bd30e-106">Tutti i tipi numerici a virgola mobile supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), di [confronto](../operators/comparison-operators.md)e di [uguaglianza](../operators/equality-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="bd30e-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="bd30e-107">Caratteristiche dei tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="bd30e-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="bd30e-108">C# supporta i tipi a virgola mobile predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd30e-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="bd30e-109">Tipo/parola chiave C#</span><span class="sxs-lookup"><span data-stu-id="bd30e-109">C# type/keyword</span></span>|<span data-ttu-id="bd30e-110">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="bd30e-110">Approximate range</span></span>|<span data-ttu-id="bd30e-111">Precisione</span><span class="sxs-lookup"><span data-stu-id="bd30e-111">Precision</span></span>|<span data-ttu-id="bd30e-112">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="bd30e-112">Size</span></span>|<span data-ttu-id="bd30e-113">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="bd30e-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="bd30e-114">Compreso tra ±1.5 x 10<sup>−45</sup> e ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="bd30e-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="bd30e-115">~6-9 cifre</span><span class="sxs-lookup"><span data-stu-id="bd30e-115">~6-9 digits</span></span>|<span data-ttu-id="bd30e-116">4 byte</span><span class="sxs-lookup"><span data-stu-id="bd30e-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="bd30e-117">Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="bd30e-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="bd30e-118">~15-17 cifre</span><span class="sxs-lookup"><span data-stu-id="bd30e-118">~15-17 digits</span></span>|<span data-ttu-id="bd30e-119">8 byte</span><span class="sxs-lookup"><span data-stu-id="bd30e-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="bd30e-120">Compreso tra ±1.0 x 10<sup>-28</sup> e ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="bd30e-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="bd30e-121">28-29 cifre</span><span class="sxs-lookup"><span data-stu-id="bd30e-121">28-29 digits</span></span>|<span data-ttu-id="bd30e-122">16 byte</span><span class="sxs-lookup"><span data-stu-id="bd30e-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="bd30e-123">Nella tabella precedente ogni tipo/parola chiave C# nella colonna più a sinistra è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bd30e-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="bd30e-124">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="bd30e-124">They are interchangeable.</span></span> <span data-ttu-id="bd30e-125">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="bd30e-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="bd30e-126">Il valore predefinito di ogni tipo a virgola mobile è zero `0`.</span><span class="sxs-lookup"><span data-stu-id="bd30e-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="bd30e-127">Ogni tipo a virgola mobile ha costanti `MinValue` e `MaxValue` che specificano il valore finito minimo e massimo del tipo.</span><span class="sxs-lookup"><span data-stu-id="bd30e-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="bd30e-128">I tipi `float` e `double` forniscono anche costanti che rappresentano valori Not-a-Number (NaN) e infiniti.</span><span class="sxs-lookup"><span data-stu-id="bd30e-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="bd30e-129">Ad esempio, il tipo `double` fornisce le costanti seguenti: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> e <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bd30e-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="bd30e-130">Dato che il tipo `decimal` è caratterizzato da una maggiore precisione e da un intervallo più piccolo rispetto a `float` e `double`, è appropriato per calcoli finanziari e monetari.</span><span class="sxs-lookup"><span data-stu-id="bd30e-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="bd30e-131">In un'espressione è possibile combinare tipi [integrali](integral-numeric-types.md) e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="bd30e-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="bd30e-132">In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="bd30e-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="bd30e-133">La valutazione dell'espressione viene eseguita in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd30e-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="bd30e-134">Se uno dei tipi a virgola mobile è `double`, l'espressione restituisce `double` o a [bool](../keywords/bool.md) nei confronti relazionali e di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="bd30e-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="bd30e-135">Se non è presente alcun tipo di `double` nell'espressione, l'espressione restituisce `float` o a [bool](../keywords/bool.md) nei confronti relazionali e di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="bd30e-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="bd30e-136">Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd30e-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="bd30e-137">Zero positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="bd30e-137">Positive and negative zero</span></span>
- <span data-ttu-id="bd30e-138">Infinito positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="bd30e-138">Positive and negative infinity</span></span>
- <span data-ttu-id="bd30e-139">Non un numero</span><span class="sxs-lookup"><span data-stu-id="bd30e-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="bd30e-140">Insieme finito di valori diversi da zero</span><span class="sxs-lookup"><span data-stu-id="bd30e-140">The finite set of nonzero values</span></span>

<span data-ttu-id="bd30e-141">Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="bd30e-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="bd30e-142">È possibile usare [stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md) oppure [stringhe di formato numerico personalizzato](../../../standard/base-types/custom-numeric-format-strings.md) per formattare un valore a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="bd30e-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="bd30e-143">Valori letterali reali</span><span class="sxs-lookup"><span data-stu-id="bd30e-143">Real literals</span></span>

<span data-ttu-id="bd30e-144">Il tipo di un valore letterale reale è determinato dal suffisso, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bd30e-144">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="bd30e-145">Il valore letterale senza suffisso o con il suffisso `d` o `D` è di tipo `double`</span><span class="sxs-lookup"><span data-stu-id="bd30e-145">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="bd30e-146">Il valore letterale con il suffisso `f` o `F` è di tipo `float`</span><span class="sxs-lookup"><span data-stu-id="bd30e-146">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="bd30e-147">Il valore letterale con il suffisso `m` o `M` è di tipo `decimal`</span><span class="sxs-lookup"><span data-stu-id="bd30e-147">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="bd30e-148">Il codice seguente illustra un esempio di ogni:</span><span class="sxs-lookup"><span data-stu-id="bd30e-148">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="bd30e-149">Nell'esempio precedente viene inoltre illustrato l'utilizzo di `_` come *separatore di cifre*, supportato a partire C# da 7,0.</span><span class="sxs-lookup"><span data-stu-id="bd30e-149">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="bd30e-150">È possibile usare il separatore di cifre con tutti i tipi di valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="bd30e-150">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="bd30e-151">È anche possibile usare la notazione scientifica, ovvero specificare una parte dell'esponente di un valore letterale reale, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bd30e-151">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="bd30e-152">Conversioni</span><span class="sxs-lookup"><span data-stu-id="bd30e-152">Conversions</span></span>

<span data-ttu-id="bd30e-153">La conversione è implicita (denominata *conversione verso un tipo di dati più grande*) da `float` in `double` perché l'intervallo di valori `float` è un subset corretto di `double` e non si perde precisione da `float` in `double`.</span><span class="sxs-lookup"><span data-stu-id="bd30e-153">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="bd30e-154">È necessario usare un cast esplicito per convertire un tipo a virgola mobile in un altro tipo a virgola mobile quando non è definita una conversione implicita dal tipo di origine nel tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bd30e-154">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="bd30e-155">Questa operazione è definita *conversione verso un tipo di dati più piccolo*.</span><span class="sxs-lookup"><span data-stu-id="bd30e-155">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="bd30e-156">Il caso esplicito è necessario perché la conversione può comportare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="bd30e-156">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="bd30e-157">La conversione non è implicita tra altri tipi a virgola mobile e il tipo `decimal` perché il tipo `decimal` ha una maggiore precisione rispetto a `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="bd30e-157">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="bd30e-158">Per altre informazioni sulle conversioni numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="bd30e-158">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="bd30e-159">Per altre informazioni sulle conversioni numeriche esplicite, vedere [Tabella delle conversioni numeriche esplicite](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="bd30e-159">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bd30e-160">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bd30e-160">C# language specification</span></span>

<span data-ttu-id="bd30e-161">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="bd30e-161">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="bd30e-162">Tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="bd30e-162">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="bd30e-163">Tipo decimale</span><span class="sxs-lookup"><span data-stu-id="bd30e-163">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="bd30e-164">Valori letterali reali</span><span class="sxs-lookup"><span data-stu-id="bd30e-164">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="bd30e-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd30e-165">See also</span></span>

- [<span data-ttu-id="bd30e-166">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="bd30e-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bd30e-167">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="bd30e-167">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="bd30e-168">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="bd30e-168">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="bd30e-169">Dati numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="bd30e-169">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="bd30e-170">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="bd30e-170">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="bd30e-171">Tabella di formattazione dei risultati numerici</span><span class="sxs-lookup"><span data-stu-id="bd30e-171">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="bd30e-172">Stringhe di formato numerico standard</span><span class="sxs-lookup"><span data-stu-id="bd30e-172">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
