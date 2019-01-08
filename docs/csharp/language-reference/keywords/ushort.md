---
title: Parola chiave ushort - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: 934e25576a8a24c176a54ec6af984459b513fe5a
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614459"
---
# <a name="ushort-c-reference"></a><span data-ttu-id="2322b-102">ushort (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2322b-102">ushort (C# Reference)</span></span>

<span data-ttu-id="2322b-103">La parola chiave `ushort` indica un tipo di dati integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2322b-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="2322b-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="2322b-104">Type</span></span>|<span data-ttu-id="2322b-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="2322b-105">Range</span></span>|<span data-ttu-id="2322b-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="2322b-106">Size</span></span>|<span data-ttu-id="2322b-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="2322b-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`ushort`|<span data-ttu-id="2322b-108">Da 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="2322b-108">0 to 65,535</span></span>|<span data-ttu-id="2322b-109">Intero senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="2322b-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="2322b-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="2322b-110">Literals</span></span>

<span data-ttu-id="2322b-111">È possibile dichiarare e inizializzare una variabile `ushort` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="2322b-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="2322b-112">Se il valore letterale integer è esterno all'intervallo di `ushort`, vale a dire se è minore di <xref:System.UInt16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2322b-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="2322b-113">Nell'esempio seguente, i valori interi uguali a 65,034 rappresentati come valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](int.md) a valori `ushort`.</span><span class="sxs-lookup"><span data-stu-id="2322b-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](int.md) to `ushort` values.</span></span>

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]

> [!NOTE]
> <span data-ttu-id="2322b-114">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="2322b-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="2322b-115">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="2322b-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="2322b-116">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità:</span><span class="sxs-lookup"><span data-stu-id="2322b-116">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="2322b-117">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="2322b-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="2322b-118">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="2322b-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="2322b-119">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="2322b-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="2322b-120">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="2322b-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]

## <a name="compiler-overload-resolution"></a><span data-ttu-id="2322b-121">Risoluzione dell'overload del compilatore</span><span class="sxs-lookup"><span data-stu-id="2322b-121">Compiler overload resolution</span></span>

<span data-ttu-id="2322b-122">Quando si chiamano metodi di overload, è necessario usare un cast.</span><span class="sxs-lookup"><span data-stu-id="2322b-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="2322b-123">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `ushort` e [int](int.md):</span><span class="sxs-lookup"><span data-stu-id="2322b-123">Consider, for example, the following overloaded methods that use `ushort` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ushort s) {}
```

<span data-ttu-id="2322b-124">L'uso del cast `ushort` garantisce che venga chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2322b-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>

```csharp
// Calls the method with the int parameter:
SampleMethod(5);
// Calls the method with the ushort parameter:
SampleMethod((ushort)5);
```

## <a name="conversions"></a><span data-ttu-id="2322b-125">Conversioni</span><span class="sxs-lookup"><span data-stu-id="2322b-125">Conversions</span></span>

<span data-ttu-id="2322b-126">Viene eseguita una conversione implicita da `ushort` in [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) o [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="2322b-126">There is a predefined implicit conversion from `ushort` to [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="2322b-127">Viene eseguita una conversione implicita predefinita da [byte](byte.md) o [char](char.md) in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="2322b-127">There is a predefined implicit conversion from [byte](byte.md) or [char](char.md) to `ushort`.</span></span> <span data-ttu-id="2322b-128">In caso contrario è necessario usare un cast per eseguire una conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="2322b-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="2322b-129">Considerare, ad esempio, le due variabili `ushort` seguenti, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="2322b-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>

```csharp
ushort x = 5, y = 12;
```

<span data-ttu-id="2322b-130">L'istruzione di assegnazione seguente genererà un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce `int` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2322b-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>

```csharp
ushort z = x + y;   // Error: conversion from int to ushort
```

<span data-ttu-id="2322b-131">Per risolvere il problema, usare un cast:</span><span class="sxs-lookup"><span data-stu-id="2322b-131">To fix this problem, use a cast:</span></span>

```csharp
ushort z = (ushort)(x + y);   // OK: explicit conversion
```

<span data-ttu-id="2322b-132">È possibile tuttavia usare le istruzioni seguenti dove la variabile di destinazione ha la stessa dimensione di archiviazione o una dimensione maggiore:</span><span class="sxs-lookup"><span data-stu-id="2322b-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
int m = x + y;
long n = x + y;
```

<span data-ttu-id="2322b-133">Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="2322b-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="2322b-134">Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="2322b-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
ushort x = 3.0;
// OK -- explicit conversion:
ushort y = (ushort)3.0;
```

<span data-ttu-id="2322b-135">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](float.md) e [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="2322b-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="2322b-136">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="2322b-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2322b-137">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2322b-137">C# language specification</span></span>

<span data-ttu-id="2322b-138">Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="2322b-138">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="2322b-139">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="2322b-139">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="2322b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2322b-140">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="2322b-141">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2322b-141">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2322b-142">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2322b-142">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2322b-143">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="2322b-143">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2322b-144">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="2322b-144">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="2322b-145">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="2322b-145">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="2322b-146">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="2322b-146">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="2322b-147">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="2322b-147">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
