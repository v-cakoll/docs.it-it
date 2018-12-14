---
title: Parola chiave ulong (Riferimenti per C#)
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: d0c7df4ebda13a59e51e9599699f6abf4bbf1d71
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143428"
---
# <a name="ulong-c-reference"></a><span data-ttu-id="57caa-102">ulong (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="57caa-102">ulong (C# Reference)</span></span>

<span data-ttu-id="57caa-103">La parola chiave `ulong` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="57caa-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="57caa-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="57caa-104">Type</span></span>|<span data-ttu-id="57caa-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="57caa-105">Range</span></span>|<span data-ttu-id="57caa-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="57caa-106">Size</span></span>|<span data-ttu-id="57caa-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="57caa-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`ulong`|<span data-ttu-id="57caa-108">Da 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="57caa-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="57caa-109">Intero senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="57caa-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="57caa-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="57caa-110">Literals</span></span>

<span data-ttu-id="57caa-111">È possibile dichiarare e inizializzare una variabile `ulong` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="57caa-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="57caa-112">Se il valore letterale integer è esterno all'intervallo di `ulong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="57caa-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="57caa-113">Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ulong`.</span><span class="sxs-lookup"><span data-stu-id="57caa-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> <span data-ttu-id="57caa-114">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="57caa-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="57caa-115">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="57caa-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="57caa-116">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità:</span><span class="sxs-lookup"><span data-stu-id="57caa-116">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="57caa-117">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="57caa-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="57caa-118">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="57caa-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="57caa-119">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="57caa-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="57caa-120">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="57caa-120">Some examples are shown below.</span></span>

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

<span data-ttu-id="57caa-121">Valori letterali integer possono anche includere un suffisso che denota il tipo.</span><span class="sxs-lookup"><span data-stu-id="57caa-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="57caa-122">Il suffisso `UL` o `ul` identifica in modo inequivocabile un valore letterale numerico come valore `ulong`.</span><span class="sxs-lookup"><span data-stu-id="57caa-122">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="57caa-123">Il suffisso `L` indica `ulong` se il valore letterale supera <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57caa-123">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="57caa-124">Il suffisso `U` o `u` indica `ulong` se il valore letterale supera <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57caa-124">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="57caa-125">L'esempio seguente usa il suffisso `ul` per indicare un valore long integer:</span><span class="sxs-lookup"><span data-stu-id="57caa-125">The following example uses the `ul` suffix to denote a long integer:</span></span>

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

<span data-ttu-id="57caa-126">Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="57caa-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="57caa-127">int</span><span class="sxs-lookup"><span data-stu-id="57caa-127">int</span></span>](int.md)
2. [<span data-ttu-id="57caa-128">uint</span><span class="sxs-lookup"><span data-stu-id="57caa-128">uint</span></span>](uint.md)
3. [<span data-ttu-id="57caa-129">long</span><span class="sxs-lookup"><span data-stu-id="57caa-129">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="57caa-130">Risoluzione dell'overload del compilatore</span><span class="sxs-lookup"><span data-stu-id="57caa-130">Compiler overload resolution</span></span>

<span data-ttu-id="57caa-131">Il suffisso viene comunemente usato per la chiamata di metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="57caa-131">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="57caa-132">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `ulong` e [int](int.md):</span><span class="sxs-lookup"><span data-stu-id="57caa-132">Consider, for example, the following overloaded methods that use `ulong` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ulong l) {}
```

<span data-ttu-id="57caa-133">L'uso del suffisso con il parametro `ulong` garantisce che verrà chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="57caa-133">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>

```csharp
SampleMethod(5);    // Calling the method with the int parameter
SampleMethod(5UL);  // Calling the method with the ulong parameter
```

## <a name="conversions"></a><span data-ttu-id="57caa-134">Conversioni</span><span class="sxs-lookup"><span data-stu-id="57caa-134">Conversions</span></span>

<span data-ttu-id="57caa-135">Si verifica una conversione implicita predefinita da `ulong` a [float](float.md), [double](double.md) o [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="57caa-135">There is a predefined implicit conversion from `ulong` to [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="57caa-136">Non viene eseguita alcuna conversione implicita da `ulong` a qualsiasi tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="57caa-136">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="57caa-137">L'istruzione seguente, ad esempio, genera un errore di compilazione se non viene usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="57caa-137">For example, the following statement will produce a compilation error without an explicit cast:</span></span>

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

<span data-ttu-id="57caa-138">Viene eseguita una conversione implicita predefinita da [byte](byte.md), [ushort](ushort.md), [uint](uint.md) o [char](char.md) a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="57caa-138">There is a predefined implicit conversion from [byte](byte.md), [ushort](ushort.md), [uint](uint.md), or [char](char.md) to `ulong`.</span></span>

<span data-ttu-id="57caa-139">Non viene eseguita alcuna conversione implicita dai tipi a virgola mobile a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="57caa-139">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="57caa-140">Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="57caa-140">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

<span data-ttu-id="57caa-141">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](float.md) e [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="57caa-141">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="57caa-142">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="57caa-142">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="57caa-143">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="57caa-143">C# language specification</span></span>

<span data-ttu-id="57caa-144">Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="57caa-144">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="57caa-145">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="57caa-145">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="57caa-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57caa-146">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="57caa-147">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="57caa-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="57caa-148">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="57caa-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="57caa-149">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="57caa-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="57caa-150">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="57caa-150">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="57caa-151">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="57caa-151">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="57caa-152">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="57caa-152">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="57caa-153">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="57caa-153">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
