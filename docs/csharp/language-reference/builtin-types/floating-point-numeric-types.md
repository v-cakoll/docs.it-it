---
title: Tipi numerici a virgola mobile - Riferimenti per C#
description: Panoramica dei tipi a virgola mobile incorporati di C#
ms.date: 10/22/2019
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
ms.openlocfilehash: 9c8b11f9337ee9de90f2d4d96b5be162713bfcbd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093214"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="cd634-103">Tipi numerici a virgola mobile (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cd634-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="cd634-104">I *tipi numerici a virgola mobile* rappresentano i numeri reali.</span><span class="sxs-lookup"><span data-stu-id="cd634-104">The *floating-point numeric types* represent real numbers.</span></span> <span data-ttu-id="cd634-105">Tutti i tipi numerici a virgola mobile sono [tipi di valore](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="cd634-105">All floating-point numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="cd634-106">Sono anche [tipi semplici](value-types.md#built-in-value-types) e possono essere inizializzati con [valori letterali](#real-literals).</span><span class="sxs-lookup"><span data-stu-id="cd634-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#real-literals).</span></span> <span data-ttu-id="cd634-107">Tutti i tipi numerici a virgola mobile supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), di [confronto](../operators/comparison-operators.md)e di [uguaglianza](../operators/equality-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="cd634-107">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="cd634-108">Caratteristiche dei tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="cd634-108">Characteristics of the floating-point types</span></span>

<span data-ttu-id="cd634-109">C# supporta i tipi a virgola mobile predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd634-109">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="cd634-110">Tipo/parola chiave C#</span><span class="sxs-lookup"><span data-stu-id="cd634-110">C# type/keyword</span></span>|<span data-ttu-id="cd634-111">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="cd634-111">Approximate range</span></span>|<span data-ttu-id="cd634-112">Precision</span><span class="sxs-lookup"><span data-stu-id="cd634-112">Precision</span></span>|<span data-ttu-id="cd634-113">Dimensione</span><span class="sxs-lookup"><span data-stu-id="cd634-113">Size</span></span>|<span data-ttu-id="cd634-114">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="cd634-114">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="cd634-115">Compreso tra ±1.5 x 10<sup>−45</sup> e ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="cd634-115">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="cd634-116">~6-9 cifre</span><span class="sxs-lookup"><span data-stu-id="cd634-116">~6-9 digits</span></span>|<span data-ttu-id="cd634-117">4 byte</span><span class="sxs-lookup"><span data-stu-id="cd634-117">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="cd634-118">Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="cd634-118">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="cd634-119">~15-17 cifre</span><span class="sxs-lookup"><span data-stu-id="cd634-119">~15-17 digits</span></span>|<span data-ttu-id="cd634-120">8 byte</span><span class="sxs-lookup"><span data-stu-id="cd634-120">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="cd634-121">Compreso tra ±1.0 x 10<sup>-28</sup> e ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="cd634-121">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="cd634-122">28-29 cifre</span><span class="sxs-lookup"><span data-stu-id="cd634-122">28-29 digits</span></span>|<span data-ttu-id="cd634-123">16 byte</span><span class="sxs-lookup"><span data-stu-id="cd634-123">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="cd634-124">Nella tabella precedente ogni tipo/parola chiave C# nella colonna più a sinistra è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="cd634-124">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="cd634-125">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="cd634-125">They are interchangeable.</span></span> <span data-ttu-id="cd634-126">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="cd634-126">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="cd634-127">Il valore predefinito di ogni tipo a virgola mobile è zero `0`.</span><span class="sxs-lookup"><span data-stu-id="cd634-127">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="cd634-128">Ogni tipo a virgola mobile ha costanti `MinValue` e `MaxValue` che specificano il valore finito minimo e massimo del tipo.</span><span class="sxs-lookup"><span data-stu-id="cd634-128">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="cd634-129">I tipi `float` e `double` forniscono anche costanti che rappresentano valori Not-a-Number (NaN) e infiniti.</span><span class="sxs-lookup"><span data-stu-id="cd634-129">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="cd634-130">Ad esempio, il tipo `double` fornisce le costanti seguenti: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> e <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd634-130">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="cd634-131">Dato che il tipo `decimal` è caratterizzato da una maggiore precisione e da un intervallo più piccolo rispetto a `float` e `double`, è appropriato per calcoli finanziari e monetari.</span><span class="sxs-lookup"><span data-stu-id="cd634-131">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="cd634-132">In un'espressione è possibile combinare tipi [integrali](integral-numeric-types.md) e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="cd634-132">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="cd634-133">In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="cd634-133">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="cd634-134">La valutazione dell'espressione viene eseguita in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd634-134">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="cd634-135">Se uno dei tipi a virgola mobile è `double`, l'espressione restituisce `double`o a [bool](bool.md) nei confronti relazionali e di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="cd634-135">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="cd634-136">Se non è presente alcun tipo di `double` nell'espressione, l'espressione restituisce `float`o a [bool](bool.md) nei confronti relazionali e di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="cd634-136">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="cd634-137">Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd634-137">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="cd634-138">Zero positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="cd634-138">Positive and negative zero</span></span>
- <span data-ttu-id="cd634-139">Infinito positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="cd634-139">Positive and negative infinity</span></span>
- <span data-ttu-id="cd634-140">Non un numero</span><span class="sxs-lookup"><span data-stu-id="cd634-140">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="cd634-141">Insieme finito di valori diversi da zero</span><span class="sxs-lookup"><span data-stu-id="cd634-141">The finite set of nonzero values</span></span>

<span data-ttu-id="cd634-142">Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="cd634-142">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="cd634-143">È possibile usare [stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md) oppure [stringhe di formato numerico personalizzato](../../../standard/base-types/custom-numeric-format-strings.md) per formattare un valore a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="cd634-143">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="cd634-144">Valori letterali reali</span><span class="sxs-lookup"><span data-stu-id="cd634-144">Real literals</span></span>

<span data-ttu-id="cd634-145">Il tipo di un valore letterale reale è determinato dal suffisso, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cd634-145">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="cd634-146">Il valore letterale senza suffisso o con il suffisso `d` o `D` è di tipo `double`</span><span class="sxs-lookup"><span data-stu-id="cd634-146">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="cd634-147">Il valore letterale con il suffisso `f` o `F` è di tipo `float`</span><span class="sxs-lookup"><span data-stu-id="cd634-147">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="cd634-148">Il valore letterale con il suffisso `m` o `M` è di tipo `decimal`</span><span class="sxs-lookup"><span data-stu-id="cd634-148">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="cd634-149">Il codice seguente illustra un esempio di ogni:</span><span class="sxs-lookup"><span data-stu-id="cd634-149">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="cd634-150">Nell'esempio precedente viene inoltre illustrato l'utilizzo di `_` come *separatore di cifre*, supportato a partire C# da 7,0.</span><span class="sxs-lookup"><span data-stu-id="cd634-150">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="cd634-151">È possibile usare il separatore di cifre con tutti i tipi di valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="cd634-151">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="cd634-152">È anche possibile usare la notazione scientifica, ovvero specificare una parte dell'esponente di un valore letterale reale, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cd634-152">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="cd634-153">Conversioni</span><span class="sxs-lookup"><span data-stu-id="cd634-153">Conversions</span></span>

<span data-ttu-id="cd634-154">Esiste una sola conversione implicita tra tipi numerici a virgola mobile: da `float` a `double`.</span><span class="sxs-lookup"><span data-stu-id="cd634-154">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="cd634-155">Tuttavia, è possibile convertire qualsiasi tipo a virgola mobile in qualsiasi altro tipo a virgola mobile con il [cast esplicito](../operators/type-testing-and-cast.md#cast-operator-).</span><span class="sxs-lookup"><span data-stu-id="cd634-155">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-operator-).</span></span> <span data-ttu-id="cd634-156">Per altre informazioni, vedere [conversioni numeriche predefinite](numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="cd634-156">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="cd634-157">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cd634-157">C# language specification</span></span>

<span data-ttu-id="cd634-158">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="cd634-158">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="cd634-159">Tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="cd634-159">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="cd634-160">Tipo decimale</span><span class="sxs-lookup"><span data-stu-id="cd634-160">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="cd634-161">Valori letterali reali</span><span class="sxs-lookup"><span data-stu-id="cd634-161">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="cd634-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd634-162">See also</span></span>

- [<span data-ttu-id="cd634-163">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="cd634-163">C# reference</span></span>](../index.md)
- [<span data-ttu-id="cd634-164">Tipi di valore</span><span class="sxs-lookup"><span data-stu-id="cd634-164">Value types</span></span>](value-types.md)
- [<span data-ttu-id="cd634-165">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="cd634-165">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="cd634-166">Stringhe di formato numerico standard</span><span class="sxs-lookup"><span data-stu-id="cd634-166">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="cd634-167">Dati numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="cd634-167">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
